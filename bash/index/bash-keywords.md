# Bash :: Keywords

# List of bash keywords

- {
- }
- !
- [[
- ]]
- if
- then
- else
- elif
- fi
- case
- esac
- for
- select
- while
- until
- do
- done
- in
- function
- time
- coproc

## Grouped bash keywords

- !
- { … }
- [[ … ]]
- if … then … else … elif … fi
- case … esac
- for … in
- select … in
- while/until … do … done
- function
- time
- coproc


## Generating a list of bash keywords

```bash
# compgen [-abcdefgjksuv]

compgen -a # list of aliases
compgen -b # list of bash builtins
compgen -c # list of commands (aliases, functions, keywords, builtins, binaries)
compgen -k # list of bash keywords
compgen -u # list of users
compgen -g # list of groups
```
