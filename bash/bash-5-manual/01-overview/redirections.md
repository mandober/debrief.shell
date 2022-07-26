# Redirection

https://www.gnu.org/software/coreutils/manual/html_node/I_002fO-redirection.html#I_002fO-redirection


## File Descriptors

File Descriptor (FD) 
* Input
  - Standard Input, stdin, fd0
* Output
  - Standard Output, stdout, fd1
  - Standard Error, stderr, fd2


Output resirection: `cmd f> d`    
Redirect the file descriptor `f` to the destination `d`
* f may be one of the standard FDs: 0, 1, 2
* or newly created one
* By default, in this construct, it is 1 i.e. stdout


cmd 1> file
Same as `cmd > file`. 1 is the default file descriptor for stdout.



| cmd 2> file                 | Redirect the standard error (stderr) of     |
|                             | `cmd` to a file. 2 is the default file      |
|                             | descriptor for stderr.                      |
+-----------------------------'---------------------------------------------'
| cmd >> file                 | Append stdout of `cmd` to a file.           |
+-----------------------------'---------------------------------------------'
| cmd 2>> file                | Append stderr of `cmd` to a file.           |
+-----------------------------'---------------------------------------------'
| cmd &> file                 | Redirect stdout and stderr to a file.       |
+-----------------------------'---------------------------------------------'
| cmd > file 2>&1             | Another way to redirect both stdout and     |
|                             | stderr of `cmd` to a file. This *is not*    |
|                             | same as `cmd 2>&1 > file`.                  |
|                             | Redirection order matters!                  |
+-----------------------------'---------------------------------------------'
| cmd > /dev/null             | Discard stdout of `cmd`.                    |
+-----------------------------'---------------------------------------------'
| cmd 2> /dev/null            | Discard stderr of `cmd`.                    |
+-----------------------------'---------------------------------------------'
| cmd &> /dev/null            | Discard stdout and stderr.                  |
+-----------------------------'---------------------------------------------'
| cmd < file                  | Redirect the contents of the file to the    |
|                             | stdin of `cmd`.                             |
+-----------------------------'---------------------------------------------'
| cmd << EOL                  |                                             |
| foo                         | Redirect a bunch of lines to the stdin.     |
| bar                         | If 'EOL' is quoted, text is treated         |
| baz                         | literally. This is called a here-document.  |
| EOL                         |                                             |
+-----------------------------'---------------------------------------------'
| cmd <<- EOL                 |                                             |
| <tab>foo                    | Redirect a bunch of lines to the stdin.     |
| <tab><tab>bar               | The <tab>'s are ignored but not the         |
| EOL                         | whitespace. Helpful for formatting.         |
+-----------------------------'---------------------------------------------'
| cmd <<< "string"            | Redirect a single line of text to stdin.    |
|                             | This is called a here-string.               |
+-----------------------------'---------------------------------------------'
| exec 2> file                | Redirect stderr of all commands to a file   |
|                             | forever.                                    |
+-----------------------------'---------------------------------------------'
| exec 3< file                | Open a file for reading using a custom fd.  |
+-----------------------------'---------------------------------------------'
| exec 3> file                | Open a file for writing using a custom fd.  |
+-----------------------------'---------------------------------------------'
| exec 3<> file               | Open a file for reading and writing using   |
|                             | a custom file descriptor.                   |
+-----------------------------'---------------------------------------------'
| exec 3>&-                   | Close a file descriptor.                    |
+-----------------------------'---------------------------------------------'
| exec 4>&3                   | Make file descriptor 4 to be a copy of file |
|                             | descriptor 3. (Copy fd 3 to 4.)             |
+-----------------------------'---------------------------------------------'
| exec 4>&3-                  | Copy file descriptor 3 to 4 and close fd 3  |
+-----------------------------'---------------------------------------------'
| echo "foo" >&3              | Write to a custom file descriptor.          |
+-----------------------------'---------------------------------------------'
| cat <&3                     | Read from a custom file descriptor.         |
+-----------------------------'---------------------------------------------'
| (cmd1; cmd2) > file         | Redirect stdout from multiple commands to a |
|                             | file (using a sub-shell).                   |
+-----------------------------'---------------------------------------------'
| { cmd1; cmd2; } > file      | Redirect stdout from multiple commands to a |
|                             | file (faster; not using a sub-shell).       |
+-----------------------------'---------------------------------------------'
| exec 3<> /dev/tcp/host/port | Open a TCP connection to host:port.         |
+-----------------------------'---------------------------------------------'
| exec 3<> /dev/udp/host/port | Open a UDP connection to host:port.         |
+-----------------------------'---------------------------------------------'
| cmd <(cmd1)                 | Redirect stdout of `cmd1` to an anonymous   |
|                             | fifo, then pass the fifo to `cmd` as an     |
|                             | argument. Useful when `cmd` doesn't read    |
|                             | from stdin directly.                        |
+-----------------------------'---------------------------------------------'
| cmd < <(cmd1)               | Redirect stdout of `cmd1` to an anonymous   |
|                             | fifo, then redirect the fifo to stdin of    |
|                         ____' `cmd`. Best example:                        |
|                        | diff <(find /path1 | sort) <(find /path2 | sort) |
+------------------------'----.---------------------------------------------'
| cmd <(cmd1) <(cmd2)         | Redirect stdout of `cmd1` `cmd2` to two     |
|                             | anonymous fifos, then pass both fifos as    |
|                             | arguments to \verb|cmd|.                    |
+-----------------------------.---------------------------------------------'
| cmd1 >(cmd2)                | Run `cmd2` with its stdin connected to an   |
|                             | anonymous fifo, and pass the filename of    |
|                             | the pipe as an argument to `cmd1`.          |
+-----------------------------.---------------------------------------------'
| cmd1 | cmd2                 | Redirect stdout of cmd1 to stdin of `cmd2`. |
|                             | Pro-tip: This is the same as                |
|                             | `cmd1 > >(cmd2)`, same as `cmd2 < <(cmd1)`, |
|                             | same as `> >(cmd2) cmd1`, same as           |
|                             | `< <(cmd1) cmd2`.                           |
+-----------------------------'---------------------------------------------'
| cmd1 |& cmd2                | Redirect stdout and stderr of `cmd1` to     |
|                             | stdin of `cmd2` (bash 4.0+ only).           |
|                             | Use `cmd1 2>&1 | cmd2` for older bashes.    |
+-----------------------------'---------------------------------------------'
| cmd | tee file              | Redirect stdout of `cmd` to a file and      |
|                             | print it to screen.                         |
+-----------------------------'---------------------------------------------'
| exec {filew}> file          | Open a file for writing using a named file  |
|                             | descriptor called `{filew}` (bash 4.1+)     |
+-----------------------------'---------------------------------------------'
| cmd 3>&1 1>&2 2>&3          | Swap stdout and stderr of `cmd`.            |
+-----------------------------'---------------------------------------------'
| cmd > >(cmd1) 2> >(cmd2)    | Send stdout of `cmd` to `cmd1` and stderr   |
|                             | `cmd` to `cmd2`.                            |
+-----------------------------'---------------------------------------------'
| cmd1 | cmd2 | cmd3 | cmd4   | Find out the exit codes of all piped cmds.  |
| echo ${PIPESTATUS[@]}       |                                             |
+-----------------------------'---------------------------------------------'


I explained each one of these redirections in my article All About Bash Redirections:
http://www.catonmat.net/blog/bash-one-liners-explained-part-three
http://www.github.com/pkrumins/bash-redirections-cheat-sheet
