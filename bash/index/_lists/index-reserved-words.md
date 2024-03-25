# Reserved words

reserved-words are shell-words that have special meaning to the shell. 
They are used to begin and end the shell's compound commands.

These names are recognized as reserved-words
- when unquoted
- when they are the first word (head-word) of an input line 

- !
- `{` … `}`
- `[[` … `]]`
- time
- coproc
- function
- if then elif else fi
- for in
- case esac
- while until select do done

- `in` is recognized as a reserved word if
   it is the 3rd word of a *case* or *select* command

- `in` and `do` are recognized as reserved words if
   they are the third word in a *for* command.


```bash
if COND; then
  …
elif
  …
else
  …
fi
```

## Index of Shell Reserved Words

- !         Pipelines
- [[        Conditional Constructs
- ]]        Conditional Constructs
- {         Command Grouping
- }         Command Grouping
- case      Conditional Constructs
- do        Looping Constructs
- done      Looping Constructs
- elif      Conditional Constructs
- else      Conditional Constructs
- esac      Conditional Constructs
- fi        Conditional Constructs
- for       Looping Constructs
- function  Shell Procedures
- if        Conditional Constructs
- in        Conditional Constructs
- select    Conditional Constructs
- then      Conditional Constructs
- time      Pipelines
- until     Looping Constructs
- while     Looping Constructs
