 bash | man | builtins linux

dirs

dirs [-clpv] [+n] [-n]

Without options, displays the list of currently remembered directories.
The default display is on a single line with directory names separated by spaces. 
Directories are added to the list with the pushd command; the popd command removes entries from the list.

-c   Clears the directory stack by deleting all of the entries.
-l   Produces a listing using full pathnames; the default listing format uses a tilde to denote the home directory.
-p   Print the directory stack with one entry per line.
-v   Print the directory stack with one entry per line, prefixing each entry with its index in the stack.
+n   Displays the nth entry counting from the left of the list shown by dirs when invoked without options, starting with zero.
-n   Displays the nth entry counting from the right of the list shown by dirs when invoked without options, starting with zero.

The return value is 0 unless an invalid option is supplied or n indexes beyond the end of the directory stack.





