 bash | man | builtins

kill

kill [-s sigspec | -n signum | -sigspec] [pid | jobspec] ...
kill -l [sigspec | exit_status]
       
Send the signal named by sigspec or signum to the processes named by pid or jobspec. 

sigspec is either a case-insensitive signal name such as SIGKILL (with or without the SIG prefix) or a signal number; 
signum is a signal number. 

If sigspec is not present, then SIGTERM is assumed.
An argument of -l lists the signal names.
If any arguments are supplied when -l is given, the names of the signals 
corresponding to the arguments are listed, and the return status is 0. 


EXIT STATUS
argument to -l is a number specifying either a signal number 
or the exit status of a process terminated by a signal. 

kill returns true if at least one signal was successfully sent, 
or false if an error occurs or an invalid option is encountered.
