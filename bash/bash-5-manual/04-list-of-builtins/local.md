 bash | man | builtins

local

local [option] [name[=value] ...]
       
For each argument, a local variable named name is created, and assigned value. 
* The option can be any of the options accepted by declare.
* When local is used within a function, it causes the variable name to have a visible scope restricted to that function and its children. 
* With no operands, local writes a list of local variables to the standard output. 
* It is an error to use local when not within a function.
* The return status is 0 unless local is used outside a function, an invalid name is supplied, or name is a readonly variable.
