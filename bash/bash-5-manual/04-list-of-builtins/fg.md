 bash | man | builtins

fg

fg [jobspec]

Resume jobspec in the foreground, and make it the current job. 
If jobspec is not present, the shell's notion of the current job is used. 
The return value is that of the command placed into the foreground, or failure if run when job control is disabled or, when run with job control enabled, if jobspec does not specify a valid job or jobspec specifies a job that was started without job control.

