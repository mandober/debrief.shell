 bash | man | builtins

bg

bg [jobspec ...]

Resume each suspended job jobspec in the background, as if it had been started with &
* If jobspec is not present, the shell's notion of the current job is used 
* bg jobspec returns 0 unless run when job control is disabled or, when run with job 
  control enabled, any specified jobspec was not found or was started without job control.
