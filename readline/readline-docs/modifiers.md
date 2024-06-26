 bash | manual

Modifiers

After the optional word designator, there may appear a sequence of one or more of the following modifiers, each preceded by a `:'.

h   Remove a trailing filename component, leaving only the head.
t   Remove all leading filename components, leaving the tail.
r   Remove a trailing suffix of the form .xxx, leaving the basename.
e   Remove all but the trailing suffix.
p   Print the new command but do not execute it.
q   Quote the substituted words, escaping further substitutions.
x   Quote the substituted words as with q, but break into words at blanks and newlines.

s/old/new/
Substitute new for the first occurrence of old in the event line. Any delimiter can be used in place of /. The final delimiter is optional if it
is the last character of the event line. The delimiter may be quoted in old and new with a single backslash. If & appears in new, it is replaced
by old.  A single backslash will quote the &. If old is null, it is set to the last old substituted, or, if no previous history substitutions
took place, the last string in a !?string[?] search.

&   	Repeat the previous substitution.
g   	Cause changes to be applied over the entire event line. This is used in conjunction with `:s' (e.g., `:gs/old/new/') or `:&'. 
	If used with `:s', any delimiter can be used in place of /, and the final delimiter is optional if it is the last character of the event line. 		An a may be used as a synonym for g.
G   	Apply the following `s' modifier once to each word in the event line.

