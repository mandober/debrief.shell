# Bash :: Shell artefacts

**Shell artefacts** (aka *shartefacts*) is a made-up name for generic shell entities and, generally, for any aspect and concept related to shell.

**Bourne artefacts** is a name for portable, highly compatible, shell entities and, generally, any aspect and concept related to Bourne shell.

**Bash artefacts** is a name for shell entities and, generally, any aspect and concept related to bash shell, including bash-specific idiosyncrasies (aka bashisms).


```
ancient period | evolution | modernization perdiod

csh  tcsh            ash          fish   mosh  shoe
   ↘ ↓              ↗           nu    oil   gosh   sheesh
    sh         |> bash     |>     zsh
   ↗ ↑              ↘          xonsh    pwsh    hashish
ksh  mksh            dash         elvish      wish
```


Shell features (aspects of shell functionality)
- command line editing
  - keybindings
  - modes (vi, emacs)
  - magic space
- variable expansion
  - word-splitting
  - quoting mechanics
  - tilde expansion
  - arithetic expansion
  - process substitution
- redirections
- shell builtins
- command-line completions
  - programmable completions
- maintaining directory stack
- command-line history maintenance
  - command-line history recall
  - command-line history expansion and quick substitution
- job control
- configuration (set, shopt)
- aliases
- user functions


Shell words/tokens
- Raw input
- character
- metacharacter
- punctuation
- word
- token
- shell-word
- bash-word
- command-line-input
- bash-token
- bash-reserved-word
- bash-keyword
- bash-metacharacter
- bash-punctuation
- bash-command

- Command searching
  1. alias
  2. function
  3. builtin
  4. keyword
  5. binary in PATH


- Commands
  - command
    - exit-code
  - bash-alias
  - bash-function
    - return-code
    - bash-hook
  - bash-builtin

- Builtins
  - bash-builtin
  - native-builtin
  - custom-builtin
  - enabled-builtin
  - disabled-builtin
  - enhanced-builtin (as eponymous function)

- Readline
  - key binding
  - function binding
  - key sequence
  - Readline function
  - Readline macro
  - Readline variable

- Signals
  - system-signal
  - pseudo-signal
  - keyboard signal
  - C-c
  - C-d
  - C-z
  - C-v
  - C-
  - intr = ^C
  - quit = ^\
  - erase = ^?
  - kill = ^U
  - eof = ^D
  - eol = M-^?
  - eol2 = M-^?
  - swtch = <undef>
  - start = ^Q
  - stop = ^S
  - susp = ^Z
  - rprnt = ^R
  - werase = ^W
  - lnext = ^V
  - discard = ^O


- Completions
  - bash-completion

- Prompt
  - bash-prompt
  - PS0
  - PS1
  - PS2
  - PS3
  - PS4
  - PROMPT_COMMAND
  - enclosures `\[]` (to help calc prompt line width)



- Command line
  - command-line
  - command-line parsing
  - command-line procesing
  - IFS
  - raw input line
  - command-line-editing

- Terminal
  - terminal cooked-more
  - terminal raw-more
  - stty
  - tty
  - pty


- Misc
  - sourced-script
  - executable-script
  Bash command
  shell word
  bash keyword
  bash builtin
    - sh builtin
  bash alias
  bash function
  bash metachar
  bash symbolic operator
  bash name
  * variables
    - shell variable
    - bash variable
    - sh variable
  - environment variables
    - sh envar (originated in sh)
    - bash envar
    - inherited vars (e.g. from windows in wsl)
    - set by a program, language, utility
    - custom envar, user envar
    - user pref
    - specifies a default command
    - specifies a significant dir, file
