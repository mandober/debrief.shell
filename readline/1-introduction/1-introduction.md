# Readline :: Introduction


"Readline" is the name of library that provides *command-line editing* support. The current version `readline v8.2` (sep-2022) comes with `bash v5.2`. Readline is an integral part of the bash shell, but then it broke off into a standalone package, although it is still developed alongside the bash shell (so the minor version numbers of both coincide).



mainly for the bash shell, but it may be integrated and used with the other software as well.



command line editing interface. 


Command line editing is enabled by default when using an interactive shell, unless the --noediting option is supplied at shell invocation. 

Line editing is also used when using the -e option to the read builtin command (see Bash Builtin Commands). 

By default, the line editing commands are similar to those of Emacs. A vi-style line editing interface is also available. 

Line editing can be enabled at any time using the -o emacs or -o vi options to the set builtin command (see The Set Builtin), or disabled using the +o emacs or +o vi options to set.
