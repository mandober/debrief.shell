 bash | man | builtins

break

break [n]

Exit from within a for, while, until, or select loop. 
* If n is specified, break n levels. 
* n must be ≥ 1. If n is greater than the number of enclosing loops, all enclosing loops are exited. 
* The return value is 0 unless n is not greater than or equal to 1.

