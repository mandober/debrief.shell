# Bash :: Glossary

<!-- TOC -->

- [Background process](#background-process)
- [Blank](#blank)
- [Builtin](#builtin)
- [Command lookup](#command-lookup)
- [Control operator](#control-operator)
- [Exit status](#exit-status)
- [Field](#field)
- [File descriptor](#file-descriptor)
- [Filename](#filename)
- [Foreground](#foreground)
- [Job](#job)
- [Job control](#job-control)
- [Metacharacter](#metacharacter)
- [Name](#name)
- [Observability](#observability)
- [Operator](#operator)
- [POSIX](#posix)
- [Process group](#process-group)
- [Process group ID](#process-group-id)
- [Reserved word](#reserved-word)
- [Return status](#return-status)
- [Shell](#shell)
- [Shell word](#shell-word)
- [Standard file descriptor](#standard-file-descriptor)
- [stdin](#stdin)
- [stdout](#stdout)
- [stderr](#stderr)
- [Signal](#signal)
- [Special builtin](#special-builtin)
- [Token](#token)
- [Word](#word)

<!-- /TOC -->

## Background process
By default, a process executes in the foreground, meaning its FDs are connected to the current tty: therefore its stdin receives the user's keyboard input, while its stdout and stderr are free to print the process' output and possible errors messages. A program that executes in the background has its FDs dosconnected from the tty, so it cannot interact with the user. To execute a program in the background append the `&` char to its name on the command line. To send an already running process to the background, first suspend it (Ctrl + Z), then allow it to run in the background with `bg`.

## Blank
A blank is a space or tab character.

## Builtin
An internal command provided by the shell, as opposed to an external command that is an external program. The most important difference is that builtins are executed by the current shell instance in the current environment, as opposed to the external programs, whose execution is delegated (by the current shell instance) to a freshly spawned subshell. For this reason, some commands are required to be implemented as builtins (`cd`, `popd`).

## Command lookup
The command lookup procedure takes place when the shell needs to locate a shell-word which is assumed to be a command. Aliases are searched first, but this happens before the command line is fully processed, so it doesn't count as a command lookup. Only when the command line is fully processed, the command lookup procedure commences by first searching the function names, then the builtin names, and finally external executables. When bash is in POSIX mode, the special builtins are searched before functions.

## Control operator
A token that performs a control function: NL (newline), `&`, `;`, `;;`, `;&`, `;;&`, `|`, `|&`, `(`, `)`, `||`, `&&`.

## Exit status
The exit status, or the exit code, is an 8-bit integer returned by the most recently *executed command* to its caller (which may be the shell itself or another command). An exit code is always returned - if it is not explicitly controlled then it amounts to returning 0 in case of success, and 1 in case of any error. Manually controlling an exit code allows indicating different types of error that may have occurred; however, there's no standard interpretation of the various integers > 0, except that they signify some error - what error exactly is on the program's author to document.

The exit code is restricted to 8 bits, and it is used as a rudemetary machanism to indicate the status of a completed command, i.e. whether it finished successfully (an int > 0) or not (0).

The return status (code) is the same concept applied to a sourced file or a function. Generally, commands executed in a subshell have an exit code, while those executed by the current shell (in its environment) have a return code.


## Field
A unit of text that is the result of one of the shell expansions. After expansion, when executing a command, the resulting fields are used as the command name and arguments.

## File descriptor
A file descriptor (FD) is a file system abstraction, similar to a file handle. It is a communication channel that provides either an input or output channel to a process. By default, each process receives 3 standard FDs: *stdin* (for input), *stdout* (for output) and *stderr* (for printing out errors).

## Filename
A string of characters used to identify a file.

## Foreground
By default, a process executes in the foreground, so it interact with the user; its FDs are connected to the current tty: therefore its stdin receives the user's keyboard input, while its stdout and stderr are free to print the process' output and possible errors messages. A program that executes in the background has its FDs dosconnected from the tty, so it cannot interact with the user.

## Job
A set of processes comprising a pipeline, and any processes descended from it, that are all in the same process group.

## Job control
A mechanism by which users can selectively stop (suspend) and restart (resume) execution of processes.

## Metacharacter
A character that, when unquoted, separates words. A metacharacter is a `space`, `tab`, `newline`, or one of the following characters: '|', '&', ';', '(', ')', '<', or '\>'.

## Name
A `word` consisting solely of letters, numbers, and underscores, and beginning with a letter or underscore. `Name`s are used as shell variable and function names. Also referred to as an `identifier`.

## Observability
Observability is the ability to measure the internal states of a system by examining its outputs. A system is observable if the state of the system may be estimated by only examining its output (namely, sensory data). The term had originated decades ago within control theory (study of self-regulating systems), but it was used in reference to the distributed IT systems as well. In that context, observability refers to the use of telemetry data to more deeply expose the innards of a distributed system, thereby allowing a more precise insight into many aspects of its devious inner workings.

## Operator
A `control operator` or a `redirection operator`. See Redirections, for a list of redirection operators. Operators contain at least one unquoted `metacharacter`.

## POSIX
A family of open system standards based on Unix. Bash is primarily concerned with the Shell and Utilities portion of the POSIX 1003.1 standard.

## Process group
A collection of related processes each having the same process group ID.

## Process group ID
A unique identifier that represents a `process group` during its lifetime.

## Reserved word
A `word` that has a special meaning to the shell. Most reserved words introduce shell flow control constructs, such as `for` and `while`.

## Return status
The return status, or the return code, is the same concept aas the exit status, only here it applies to a sourced file, or to the called function, or sometimes also to the builtins. Generally, commands executed in a subshell have an exit code, while those executed by the current shell (in its environment) have a return code.


The exit code is restricted to 8 bits, and it is used as a rudemetary machanism to indicate the status of a completed command, i.e. whether it finished successfully (an int > 0) or not (0).

A synonym for `exit status`.

## Shell
A shell is a macro processor which allows for an interactive or non-interactive command execution.

## Shell word
A shell word is any character or a string of characters (that is, any token) that carry some meaning to the shell. Shell words are somewhat analogous to words of a natural language.

## Standard file descriptor
There are 3 standard file descriptors that each executed process is associated with: stdin, stdout and stderr. FDs may be manipulated (created, moved, closed, duplicated, etc.) by using redirection operators or the builtins (`exec`).

## stdin
stdin is one of the 3 standard FDs intended as an input channel for a process.

## stdout
stdout is one of the 3 standard FDs; stdout is intended as an output channel for a process.

## stderr
stderr is one of the 3 standard FDs. It is also an output channel like stdout, but intended only for printing out potential error messages. Such behaviour (printing "proper" output to stdout and errors to stderrr ) is not enforced but a matter of respecting the convention (by a program's author). Programs, and thus processes, that follow this convention (among other things) are said to "behave".

## Signal
A mechanism by which a process may be notified by the kernel of an event occurring in the system.

## Special builtin
A shell builtin command that has been classified as special by the POSIX standard.

## Token
A sequence of characters considered a single unit by the shell. It is either a `word` or an `operator`.

## Word
A sequence of characters treated as a unit by the shell. Words may not include unquoted `metacharacters`.
