 bash | man | builtins

eval

eval [arg ...]
The args are read and concatenated together into a single command.
This command is then read and executed by the shell, and its exit status is returned as the value of eval. 
If there are no args, or only null arguments, eval returns 0.

