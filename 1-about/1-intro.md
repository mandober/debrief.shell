# Shell

As the title suggests, this section deals with the various aspects of *textual interface*, primarily as pertaining to Unix / Linux / Debian-based operating systems.

However, besides the subject in the title, this section also covers all the surrounding aspects of the shell, like terminals, consoles, text interface, command-line editing, different linux shells, shell builtins, linux commands and utilities, and command-line environment in general.

Major topics
- Shell
- Environment
- Command-line
- Keyboard
- Terminal


**Terminal** - the topic of terminals includes terms like console, terminal emulators, pseudo terminals, terminal multiplexers, etc. It describes the history of terminals, expecially the things that are still encountered today. Even though terminals are ancient aspects of telecommunication, today's software that provides text interface to a computer is still based on these hiostorical hardware devices, even though todfay it is software that emulates the hardware - called terminal emulators.

**Environment**
Terminal environment, OS environment, shell environment, bash environment, application environment, subshell environment, process environment, child process, leader process, leader process group, signals, traps, shell variables, bash variables, user variables, exported variables, one-time subprocess variables, file descriptors (FD), open FDs, user limits (ulimits), user mask (umask), *locale*, XDG conventions, FS organization, home directory, dotfiles, and simialr topics.

**Command-line**
Command-line is the location intended for user to type commands. Kinds of commands, the first word on the command line, prefix comamnds (sudo, time), command-line interface (CLI), text interface, POSIX standard, command, command arguments, command operands, command parameters, command short and long options, command line editing, key sequances, key bindings/mappings, etc.

**Keyboard**
The keyboard as the means of input, with monitor as the means of output. Entering characters, editing typed characters, keyboard combinations, modifiers keys, metafication of keys and similar topics.

**Terminal**
Cinsoles and terminals in the past, terminal emulators of today, terminal multiplexers. In the past, terminals were hardware deveice (consoles). For a time, a terminal consisted of a teletype writer (used for user input) that was connected to a printer (used for output). The next advent was the introduction of monitors, and then the merger of input (typewriter) and output (monitor) into a single device, often called console. At the time of the mainframes, which were the actual, highly expensive computers, the use of *dumb terminals* was popular. They acted as *thin clients*, possessing only the minimal capabilities required to send the user's input to the mainframe, where it was processed, and to receive and display the returned results - this justified the term "terminal" since a terminal device was really at the end of the line. A single mainframe computer could service many dumb terminals, shared processing time among them.

Some of the popular terminal devices of the past, like the DEC VT100 and DEC52, have later, with the advent of modern computers, served as prototypes for the development of *terminal emulators* - which is an application aiming to emulate the behaviour of a terminal in software. This attempt to emulate the hardware of a past era meant that terminal emulators were widely different, each supporting the set of features of a particular hardware terminal device. Thus, the incompatibilities of the past hardware have continued to manifest as the incompatibilities of the software. The `termcap` utility was an attempt to index all the different features of terminals and to make a database that would associate a particular terminal emulator with the terminal hardware device it was trying to emulate. The successor of this effort is the `terminfo` utility.

Any Linux distribution, when used in text mode is probably the purest form today of a terminal emulator with the minimized intermediate layers. Usually terminal emulators run in GUI OS, sometimes inside a emulation layer (e.g. WSL on Windows), inside a parent terminal application (e.g. `conemu` on Windows) that hosts the proper terminal (e.g. `mintty`). All these layers complicate the interaction with the applciations that runs in the terminal (like running `vim` installed in Ubuntu WSL - Linux subsystem for Windows - in the `mintty` terminal emulator that is hosted as a child window inside `conemu`, which is slightly modified by `cmder`, all runnning in Windows).
