 bash | man | builtins

Pushd

pushd [-n] [+n] [-n]
pushd [-n] [dir]
       
Adds a directory to the top of the directory stack, or rotates the stack, making the new top of the stack the current working directory.
With no arguments, exchanges the top two directories and returns 0, unless the directory stack is empty. 

Arguments, if supplied, have the following meanings:
-n   Suppresses the normal change of directory when adding directories to the stack, so that only the stack is manipulated.
+n   Rotates the stack so that the nth directory (counting from the left of the list shown by dirs, starting with zero) is at the top.
-n   Rotates the stack so that the nth directory (counting from the right of the list shown by dirs, starting with zero) is at the top.
dir  Adds dir to the directory stack at the top, making it the new current 
     working directory as if it had been supplied as the argument to the  cd builtin.

If the pushd command is successful, a dirs is performed as well. 
If the first form is used, pushd returns 0 unless the cd to dir fails. 
With the second form, pushd returns 0 unless the directory stack is empty, 
a non-existent directory stack element is specified, 
or the directory change to the specified new current directory fails.
