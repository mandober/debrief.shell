# Magic Aliases

[A Layering Loophole in the Bourne Shell - by Simon Tatham](https://www.chiark.greenend.org.uk/~sgtatham/aliases.html), original text


The Bourne shell contains two entirely different ways to define your own commands: shell functions and aliases. This article explores the differences between the two, and shows some unexpected consequences of the alias mechanism.

# Introduction

All POSIX-compliant Bourne-style shells allow definition of shell functions:

```bash
myfunc() {
  echo First argument was $1
  echo All arguments together were "$@"
}
```

The shell evaluates a command that is a function call, such as `myfunc a b c`, in much the same way it would evaluate any other command: first it does all the usual variable expansion, wildcard expansion and so on, until the command line is a list of individual words. Then it examines the first of those words, notices that it matches the name of a shell function, so it runs that function's body with the remaining command words/args available as `$1`, `$2`, etc.

This is a simple and flexible way to define new commands. The inside of a shell function can do anything that a shell script in a file can, with the additional ability to modify shell's internal state (e.g. a function can change your PWD, whereas a shell script cannot).

Bourne shells also support aliases, which are defined using the keyword alias:

```bash
alias dir='ls -l'
```

Now if you invoke this alias using a command such as dir /etc, the shell will notice that the first word on the line is the name of an alias, and it will replace that word with the definition. So the command line will become ls -l /etc, which will then be executed in the normal way.

It's not obvious why the Bourne shell bothers to support both of these mechanisms. Shell functions, of course, can do things aliases can't do: a shell function can loop through its arguments one by one, or reverse their order completely, or can use its arguments and then do something else afterwards. But the example alias shown above could just as easily have been written as a shell function:

dir() { ls -l "$@"; }

So if any alias can be rewritten as a shell function, why does the Bourne shell support aliases at all? The casual observer would be forgiven for speculating that aliases were invented first, became largely obsolete once shell functions were available, but still had to be supported for backwards compatibility. It does look very much as if aliases are a historical wart on the Bourne shell, which add no extra functionality and would have been better off being abandoned once shell functions were invented.

Well, actually, there are some things you can do with aliases which you can't do without them. In this article I explore those things.

## The Power of Aliases

The power of aliases lies in the fact that they are handled by the shell before all the usual command-line processing. At the time when the alias is expanded, the rest of the command line has not had variable or wildcard expansions done. This suggests that the alias might be able to do something to affect those expansions.

In fact, once the challenge is put like that, it's not too difficult to produce an example. Here's a very simple one, together with the shell-function which you might expect to be equivalent:

alias lsetc='cd /etc; ls -l'         # as an alias
lsetc() { cd /etc; ls -l "$@"; }     # as a shell function

If you just type lsetc, or provide some inert arguments such as lsetc passwd hosts, these two implementations will behave identically. But if you pass a wildcard as an argument (lsetc *.conf), something more interesting will happen.

The arguments passed to the shell function, and hence to ls, will be the results of expanding the wildcard *.conf in the current directory; so you'll get a list of all the .conf files in /etc which also exist in the directory you started in. However, the alias version will be converted into cd /etc; ls -l *.conf; and the shell will finish processing the cd command before expanding the wildcard in the ls. So if you do this with the alias version of the command, you will see a list of all the .conf files in /etc.

This is all very well, but it's not really very interesting. The lsetc command defined in the above example is a thoroughly useless command, because you almost certainly would not want it to leave your current directory as /etc as a side effect. An alias containing a semicolon has the power to change the shell environment so that its arguments are expanded in a different way; but that power is not very useful if it always leaves that changed environment for you to clear up afterwards.

If we combine an alias with a shell function, however, we can harness the power of aliases in a more useful fashion. Watch this example:

lsetc_helper() {
    ls -l "$@"
    cd "$originaldir"
    unset originaldir
}

alias lsetc='originaldir="$PWD"; cd /etc; lsetc_helper'


This version of the lsetc command is much closer to being useful, since it leaves you in the same directory you started in. It now behaves very much like an ordinary shell command, with the unusual property that if you give a wildcard on its command line then that wildcard is expanded in the context of /etc instead of the current directory.

This is the simplest example of what I call a magic alias: an combination of an alias and a shell function which between them cause the alias's command line to be evaluated in a different environment from the expected one. A summary of the trick is:

You have an alias which saves parts of the shell context, changes that context, and then passes the alias's arguments to a helper shell function.
The helper shell function restores the original shell context which was saved by the alias (either before or after doing something with the arguments it was given).

Thus, the arguments passed to the alias undergo variable and wildcard expansion in the altered shell context, and yet the running of the alias as a whole leaves the shell context as it was.


## Philosophy

This is, of course, a truly horrible hack, and should not be used unless you really know what you're doing.

The Bourne shell syntax is pretty weird and baroque; I doubt anyone would disagree that it's highly non-obvious in all sorts of places to a shell beginner. But after you've used it for a little while, you start to notice an underlying consistency which enables you to be confident that you don't need to worry about unexpected behaviour in many circumstances.

One important form of this consistency is that the shell expands arguments before passing them to subcommands. Under other operating systems (notably DOS), wildcards are expanded by each individual system command and program, and each one expands them in their own way. A hurriedly written program, for example, might not understand wildcards at all; at the other end of the spectrum, you could write a rename program that ‘intelligently’ parsed your command line and understood the intent behind rename *.txt *.text. Sometimes this flexibility is useful to the application author, and to the user; but it also means that the user always has to remember the subtleties of the wildcard rules for every program they use.

So the Bourne shell's strength is its absolute consistency in this regard. Because the shell expands wildcards before passing them to a command, they are guaranteed to be expanded in exactly the same way in all cases. Any wildcard which matches at least one file will arrive in the subprogram in the form of a list of valid filename arguments; so in any situation where a command expects a list of one or more filenames, it is valid to use a wildcard instead. Life is simpler for the application programmer, and there are fewer tricky special cases to remember for the user, and if a little flexibility such as the above rename example is lost in the process, that often seems a small price to pay. (In fact, I usually find my own bulk renaming needs are more complex than that syntax could easily express anyway, so I have a bulk rename utility that uses regular expressions! Much more powerful.)

Even with shell functions, this consistency is not broken. Arguments to a shell function are expanded in exactly the same way as arguments to an external command, before the function begins to run. A shell function can do more than an external command - it can alter your shell's internal state, such as variables and current directory - but there are still limits on how much it can mess with the command line you give it.

However, the magic alias trick is a loophole in the Bourne shell's otherwise unbroken consistency. It allows you to create commands which interpret their command lines at a level which by rights ought to be impossible: a command, for example, which can tell the difference between mycmd *.c and mycmd foo.c bar.c, even when the former ought to expand to the latter. Such a command would violate all the expectations a Bourne shell user has acquired about the behaviour of commands, and despite the superficial user-friendliness to a shell novice, something like this could seriously confuse an intermediate-level user.

(Also, there's a much more immediate danger in putting a semicolon inside an alias: it causes parsing of composite commands to do unexpected things. For example, you should never put & at the end of a magic alias invocation, or the shell function that restores your environment to the way it started off will be run in a context where it can't affect your original shell!)

As Tom Duff wrote about the legendary Duff's device, ‘I feel a combination of pride and revulsion at this discovery’. I began investigating this area of the Bourne shell because aliases seemed like a completely useless feature, and I was curious to find out whether there was any reason why they shouldn't simply be removed. Although I discovered that aliases do add something to the Bourne shell (i.e. they make things possible which wouldn't be possible by other means), it's possible that what I discovered forms the best possible argument for why they should be removed!

I feel strongly that magic aliases should never be used in a default shell configuration which will be given to novice users, intermediate users, or in fact any user who hasn't been explicitly warned to expect it. However, an expert user with a strong stomach might nonetheless find it useful to add one or two magic aliases to their personal shell configuration files, if they know exactly what they're letting themselves in for, and trust themselves to never forget that they've done so.

## Applications

Here's a concrete example of how magic aliases could actually be useful.

We've already seen the idea of having command-line wildcards evaluated in a different directory from the obvious one. One much more simple thing which affects wildcard expansion is just not to expand them at all. Here's a helper function and an alias which arrange this:

noglob_helper() {
    "$@"
    case "$shopts" in
        *noglob*) ;;
        *) set +f ;;
    esac
    unset shopts
}

alias noglob='shopts="$SHELLOPTS"; set -f; noglob_helper'
This turns wildcard expansion off completely (set -f) before evaluating the alias's arguments, and then restores it to its original state afterwards. So after doing this, you can use the new noglob prefix to avoid globbing the arguments to a particular command:

$ echo *.c
foo.c bar.c baz.c
$ noglob echo *.c
*.c

This is a fairly benign use of the technique, and also fairly unhelpful since it would have been quicker to type echo '*.c' than to bother typing the noglob prefix! If you're feeling brave, you could try defining specific aliases which apply the noglob property automatically to certain commands. One command in which wildcards almost always have to be quoted is find:

find . -name '*.[ch]' | xargs grep 'struct treenode'
So if you cover the find command with an alias much like noglob:

alias find='shopts="$SHELLOPTS"; set -f; noglob_helper find'
then you will be able to type find . -name *.[ch] without fear of premature wildcard expansion.

Other possibilities include fiddling with the finer details of the globbing options in extended shells (nocaseglob, extglob, and dotglob in bash); I've already mentioned the possibility of evaluating wildcards in a different directory (but note that this also affects I/O redirections). You could disable bash's brace expansion; you could turn on set -C to avoid clobbering existing files with output redirections. The list goes on.

Irritatingly, one thing you can't do is turn off parsing of shell comments (another bash feature) for one command only. This would be incredibly useful if you had an IRC client or utility which expected a channel name on the command line: you could redefine the utility name as an alias and arrange that ‘irc -c #foobar’ was parsed in the useful way rather than by treating everything after the hash as a comment! But unfortunately, this doesn't seem to work: comments must have already been parsed by the time the alias substitution takes place.

Finally, a helpful technique for restoring sanity. As soon as you start defining aliases that modify the behaviour of existing commands, you also start wondering if you can easily turn them off when necessary. It's worth bearing in mind that you can bypass any alias definition by prefixing it with a backslash: instead of starting your command with ‘find’, use ‘\find’. This works because alias lookup happens before backslash escapes are processed, so the shell actually looks for an alias called ‘\find’, which doesn't exist.

## Related Hacks

With bash in particular, there is an even worse hack you can do which allows you to suppress all of the normal bash command-line processing. This time it works by putting a comment character at the end of the alias definition. This completely suppresses parsing of the remainder of the command line.

After you do this, you then need to recover the command line from somewhere so you can process it in your own way. The best solution I'm aware of is to recover it from the command history using bash's history builtin:

echo-literally-helper() {
    str="`history 1 | perl -pe 's/^ *[0-9]+ +[^ ]+ //'`"
    echo "$str"
}
alias echo-literally='echo-literally-helper #'
The resulting alias is a command which prints exactly what was passed on the remainder of its command line, whether that contains single quotes, double quotes, theoretically insignificant variations in whitespace, redirections, wildcards, trailing backslashes or even other comment characters:

$ echo-literally a; b; c
a; b; c
$ echo-literally    a
   a
$ echo-literally hello, world > thingy
hello, world > thingy
$ echo-literally ooh # this is a comment
ooh # this is a comment
$ echo-literally `rm -rf $HOME`
`rm -rf $HOME`

Of course, this hack is even more unstable than the magic alias hack: it won't work if run from a script, or as part of a complex command. It only works properly if typed on the interactive shell command line. That said, it might conceivably have uses (such as, for example, passing a verbatim command line through a remote-execution utility such as ssh), if you're brave enough to keep it lying around your shell configuration...


## Summary

I've presented a Bourne shell trick I call ‘magic aliases’: a fusion of aliases with shell functions, allowing the alias to affect the rules under which its own command line is evaluated. I've strongly advised extreme caution if this trick is actually used, but suggested a range of ways that it might nonetheless be useful to a user who knows exactly what they're doing.

I've also mentioned an even less stable (but correspondingly more powerful) trick along similar lines which only works with bash. I'm not sure I advise using that one at all!



---

Copyright © 2003,2004 Simon Tatham.
This document is OpenContent.
You may copy and use the text under the terms of the OpenContent Licence.
Please send comments and criticism on this article to anakin@pobox.com.
