# Bash :: Changelog :: New in version 2.0

New in bash v.2.0 - changes since bash v.1.14.7

## New Features in Bash

- a. There is a new invocation option, -D, that dumps translatable strings in a script.
- b. The 'long' invocation options must now be prefixed with '--'.
- c. New long invocation options: `--dump-strings`, `--help`, `--verbose`
- d. The 'nolineediting' invocation option was renamed to `--noediting`.
- e. The 'nobraceexpansion' and 'quiet' long invocation options were removed.
- f. The `--help` and `--version` long options now work as the GNU coding standards specify.
- g. If invoked as `sh`, bash now enters POSIX mode after reading the startup 
     files, and reads and executes commands from the file named by `$ENV` if 
     interactive (as POSIX.2 specifies). A login shell invoked as `sh` reads 
     `$ENV` after `/etc/profile` and `~/.profile`
- h. There is a new reserved word, `time`, for timing pipelines, builtins and 
     shell functions. It uses the value of the `$TIMEFORMAT` var as a format
     string describing how to print the timing statistics.
- i. The `$'…'` quoting syntax expands ANSI-C escapes 
     and leaves the result single-quoted.
- j. The `$"…"` quoting syntax performs locale-specific translation 
     and leaves the result double-quoted.
- k. `$LINENO` now works correctly in functions.
- l. New variables: `DIRSTACK`, `PIPESTATUS`, `BASH_VERSINFO`, `HOSTNAME`, 
     `SHELLOPTS`, `MACHTYPE`. The first three are array variables.
- m. The `BASH_VERSION` and `BASH_VERSINFO` variables now include the shell's
     release status: alpha[N], beta[N], release
- n. Some variables have been removed: 
    , MAIL_WARNING
    , notify
    , history_control
    , command_oriented_history
    , glob_dot_filenames
    , allow_null_glob_expansion
    , nolinks
    , hostname_completion_file
    , noclobber
    , no_exit_on_failed_exec
    , cdable_vars
    Most of them are now implemented with the new `shopt` builtin; 
    others were already implemented by `set`.
- o. Bash now uses some new variables:
      LC_ALL
    , LC_MESSAGES
    , LC_CTYPE
    , LC_COLLATE
    , LANG
    , GLOBIGNORE
    , HISTIGNORE
- The shell now supports integer-indexed arrays of unlimited length, with a new compound assignment syntax and changes to the appropriate builtin commands (declare/typeset, read, readonly, etc.). The array index may be an arithmetic expression.
- `${!var}` indirect variable expansion, equivalent to `eval \${$var}`
- `${paramter:offset[:length]}` variable substring extraction
- `${parameter/pattern[/[/]string]}` variable pattern substitution
- `$[…]` arithmetic expansion syntax deprecated by `$((…))`
- Aliases can now be expanded in shell scripts with `shopt expand_aliases`
v.  History and history expansion can now be used in scripts with
    `set -o history` or `set -H`
w.  All builtins now return an exit status of 2 for incorrect usage.
x.  Interactive shells resend SIGHUP to all running or stopped children
    if (and only if) they exit due to a SIGHUP.

y.  New prompting expansions: \a, \e, \H, \T, \@, \v, \V

z.  Variable expansion in prompt strings is now controllable via a shell
    option, `shopt promptvars`

aa. Bash now defaults to using command-oriented history.

bb. The history file ($HISTFILE) is now truncated to $HISTFILESIZE after
    being written.

cc. The POSIX.2 conditional arithmetic evaluation syntax (expr ? expr : expr)
    has been implemented.

dd. Each builtin now accepts '--' to signify the end of the options, except
    as documented (echo, etc.).

ee. All builtins use -p to display values in a re-readable format where
    appropriate, except as documented (echo, type, etc.).

ff. The 'alias' builtin has a new -p option.

gg. Changes to the 'bind' builtin:
    o has new options: -psPSVr.
    o the '-d' option was renamed to '-p'
    o the '-v' option now dumps variables; the old '-v' is now '-P'

hh. The 'bye' synonym for 'exit' was removed.

ii. The -L and -P options to 'cd' and 'pwd' have been documented.

jj. The 'cd' builtin now does spelling correction on the directory name
    by default.  This is settable with a shell option (shopt cdspell).

kk. The 'declare' builtin has new options: -a, -F, -p.

ll. The 'dirs' builtin has new options: -c, -p, -v.

mm. The new 'disown' builtin removes jobs from the shell's jobs table
    or inhibits the resending of SIGHUP when the shell receives a
    SIGHUP.

nn. The 'echo' builtin has a new escape character: \e.

oo. The 'enable' builtin can now load new builtins dynamically from shared
    objects on systems with the dlopen/dlsym interface.  There are a number
    of examples in the examples/loadables directory.  There are also
    new options: -d, -f, -s, -p.

pp. The '-all' option to 'enable' was removed in favor of '-a'.

qq. The 'exec' builtin has new options: -l, -c, -a.

rr. The 'hash' builtin has a new option: -p.

ss. The 'history' builtin has new options: -c, -p, -s.

tt. The 'jobs' builtin has new options: -r, -s.

uu. The 'kill' builtin has new options: -n signum, -l signame.

vv. The 'pushd' and 'popd' builtins have a new option: -n.

ww. The 'read' builtin has new options: -p prompt, -e, -a.

xx. The 'readonly' builtin has a new -a option, and the -n option was removed.

yy. Changes to the 'set' builtin:
    o new options: -B, -o keyword, -o onecmd, -o history
    o options removed: -l, -d, -o nohash
    o options changed: +o, -h, -o hashall
    o now displays variables in a format that can be re-read as input

zz. The new 'shopt' builtin controls shell optional behavior previously
    done by setting and unsetting certain shell variables.

aaa. The 'test' builtin has new operators: -o option, s1 == s2, s1 < s2,
     and s1 > s2, where s1 and s2 are strings.

bbb. There is a new trap, DEBUG, executed after every simple command.

ccc. The 'trap' builtin has a new -p option.

ddd. The 'ulimit' builtin has a new -l option on 4.4BSD-based systems.

eee. The PS1, PS2, PATH, and IFS variables may now be unset.

fff. The restricted shell mode has been expanded and is now documented.

ggg. Security improvements:
    o functions are not imported from the environment if running setuid
      or with -p
    o no startup files are sourced if running setuid or with -p

hhh. The documentation has been overhauled:  the texinfo manual was
     expanded, and HTML versions of the man page and texinfo manual
     are included.

iii. Changes to Posix mode:
    o Command lookup now finds special builtins before shell functions.
    o Failure of a special builtin causes a non-interactive shell to
      exit.  Failures are defined in the POSIX.2 specification.
    o If the 'cd' builtin finds a directory to change to using $CDPATH,
      the value assigned to PWD when 'cd' completes does not contain
      any symbolic links.
    o A non-interactive shell exits if a variable assignment error
      occurs when no command name follows the assignment statements.
    o A non-interactive shell exits if the interation variable in a
      'for' statement or the selection variable in a 'select' statement
      is read-only or another variable assignment error occurs.
    o The '<>' redirection operator now opens a file for both stdin and
      stdout by default, not just when in posix mode.
    o Assignment statements preceding special builtins now persist in
      the shell's environment when the builtin completes.

     Posix mode is now completely POSIX.2-compliant (modulo bugs).  When
     invoked as sh, bash should be completely POSIX.2-compliant.

jjj. The default value of PS1 is now "\s-\v\$ ".

kkk. The ksh-like ((…)) arithmetic command syntax has been implemented.
     This is exactly equivalent to 'let "…"'.

lll. Integer constants have been extended to base 64.

mmm. The 'ulimit' builtin now sets both hard and soft limits and reports the
     soft limit by default.

## New Features in Readline

a.  New variables:  enable-keypad, input-meta (new name for meta-flag),
    mark-directories, visible-stats (now documented), disable-completion,
    comment-begin.

b.  New bindable commands:  kill-region, copy-region-as-kill,
    copy-backward-word, copy-forward-word, set-mark, exchange-point-and-mark,
    character-search, character-search-backward, insert-comment,
    glob-expand-word, glob-list-expansions, dump-variables, dump-macros.

c.  New emacs keybindings:  delete-horizontal-space (M-\),
    insert-completions (M-*), possible-completions (M-=).

d.  The history-search-backward and history-search-forward commands were
    modified to be the same as previous-line and next-line if point is at
    the start of the line.

e.  More file types are available for the visible-stats mode.

## Changes of interest in the Bash implementation

- a. There is a new autoconf-based configuration mechanism.
- b. More things have been moved from POSIX mode to standard shell behavior.
- c. The trace output, `set -x`, now inserts quotes where necessary 
     so it can be reused as input.
- d. There is a (disabled by default) compile-time option for a
     *system-wide interactive shell startup file*.
- e. The YACC grammar is smaller and tighter, and all 66 shift-reduce 
     conflicts are gone. Several parsing bugs have been fixed.
- f. Builtin option parsing has been regularized, using 'internal_getopt()',
     with the exception of `echo`, `type`, and `set`.
- g. Builtins now return standard usage messages constructed from the short doc
     used by the `help` builtin.
- h. Completion now quotes using backslashes by default, 
     but honors user supplied quotes.
- i. The GNU libc malloc is available as a configure-time option.
- j. More i18n features; bash uses 'gettext' if it is available. 
     The `$"…"` translation syntax uses the current locale and 'gettext'.
- k. Better reporting of job termination when the shell is not interactive.
- l. Bash is somewhat more efficient: uses less memory, makes fewer syscalls.


## Changes of interest in the Readline implementation

- a. There is now support for readline 'callback' functions.
- b. There is now support for user-supplied input, redisplay, 
     and terminal preparation functions.
- c. Most of the shell-specific code in readline has been generalized or removed
- d. Most of the annoying redisplay bugs have been fixed, 
     notably the problems with incremental search and excessive redrawing 
     when special characters appear in the prompt string.
- e. There are new library functions and variables available to application
     writers, most having to do with completion and quoting.
- f. The NEWLINE character (^J) is now treated as a search terminator by 
     the incremental search functions.
