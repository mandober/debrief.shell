# umask

umask [-p] [-S] [mode]

The user file-creation mask is set to mode. If mode begins with a digit, it is interpreted as an octal number; otherwise it is interpreted as a
symbolic mode mask similar to that accepted by chmod(1). If mode is omitted, the current value of the mask is printed. The -S option causes the
mask to be printed in symbolic form; the default output is an octal number. If the -p option is supplied, and mode is omitted, the output is in a
form that may be reused as input. The return status is 0 if the mode was successfully changed or if no mode argument was supplied, and false otherwise.
