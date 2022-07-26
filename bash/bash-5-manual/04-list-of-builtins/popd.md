 bash | man | builtins

popd

popd [-n] [+n] [-n]
       
Removes entries from the directory stack. 
With no arguments, removes the top directory from the stack, and performs a cd to the new top directory. 

Arguments, if supplied, have the following meanings:
-n   Suppresses the normal change of directory when removing 
     directories from the stack, so that only the stack is manipulated.

+n   Removes the nth entry counting from the left of the list shown by dirs, starting with zero. 
     For example: `popd +0' removes the first directory, `popd +1' the second.

-n   Removes the nth entry counting from the right of the list shown by dirs, starting with zero. 
     For example: `popd -0' removes the last directory, `popd -1' the next to last.

If the popd command is successful, a dirs is performed as well, and the return status is 0. 
popd returns false if an invalid option is encountered, the directory stack is empty, 
a non-existent directory stack entry is specified, or the directory change fails.
