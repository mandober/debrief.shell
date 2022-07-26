# Expansions

When a simple command is read, bash begins processing it in several stages. The first stage is splitting the line into tokens, followed by the expansions.

There are 7 kinds of expansions:
- BE Brace expansion
- TE, Tilde expansion
- FE, Filename expansion
- PE, Parameter expansion
- AE, Arithmetic expansion
- WS, Word splitting (again, on newly obtained words)
- CS, Command substitution
- PS, Process substitution


## EXPANSIONS

Expansion is performed on the command line after it has been split into words. 
There are seven kinds of expansion performed (in order): 

brace expansion → tilde expansion → parameter and variable expansion → arithmetic expansion → process substitution → command substitution → word splitting → pathname expansion

On systems that can support it, there is an additional expansion available: process substitution. This is performed at the same time as tilde, parameter, variable, and arithmetic expansion and command substitution.

* Only brace expansion, word splitting, and pathname 
  expansion can change the number of words of the expansion; 
  other expansions expand a single word to a single word. 
  The only exceptions to this are the expansions of "$@" and "${name[@]}"


o brace expansion: tele{gram,visor}s
o tilde expansion: cd ~/john   #> cd /home/john
o parameter expansion: 	par=$1
o variable expansion:	echo $USER -> ivan   "$USER" -> "ivan"
o arithmetic expansion: ((4+3))
o command expansion: 	$(date)
o quote removal:     $a="this is"; echo $a -> echo this is -> echo this; echo is
o word splitting:	echo is this it -> echo is; echo this; echo it
o pathname expansion:	ls ./*.jpg
