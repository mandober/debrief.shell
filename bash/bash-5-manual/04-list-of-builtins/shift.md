 bash | man | builtins

shift

shift [n]

The positional parameters from n+1 ... are renamed to $1 .... 
Parameters represented by the numbers $# down to $#-n+1 are unset.  
n must be a non-negative number less than or equal to $#. 
If n is 0, no parameters are changed. 
If n is not given, it is assumed to be 1. 
If n is greater than $#, the positional parameters are not changed. 
The return status is greater than zero if n is greater than $# or less than zero; otherwise 0.
