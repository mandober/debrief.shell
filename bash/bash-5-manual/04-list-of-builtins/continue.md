 bash | man | builtins

continue

continue [n]

Resume the next iteration of the enclosing for, while, until or select loop. 
* If n is specified, resume at the nth enclosing loop. n must be ≥ 1
* If n is greater than the number of enclosing loops, the last enclosing loop (the `top-level' loop) is resumed. 
return value is 0 unless n is not greater than or equal to 1.
