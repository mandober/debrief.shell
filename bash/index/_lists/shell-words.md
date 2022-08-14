# Bash :: Index :: Shell words

- shell-words
- bash-builtins
- native-builtin
- user-builtin


Builtin   | Origin     | Executable  | Alias       | Notes
----------|------------|-------------|-------------|---------------
`|`       | metachar   | 
`&`       | metachar   | 
`;`       | metachar   | 
`(`       | metachar   | 
`)`       | metachar   | 
`<`       | metachar   | 
`>`       | metachar   | 
alias     |            |             |             |
bg        |            |             |             |
bind      |            |             |             |
break     | Bourne     | function op
`:`       | Bourne     |             | true        |
`.`       | Bourne     |             | source      |
`[`       | Bourne     |             | test        | /bin/[
caller    |            | function op
builtin   |            | force calling the builtin instead of function/alias
cd        | Bourne     |             |             |
command   |            |             |             |
compgen   |            |             |             |
complete  |            |             |             |
compopt   |            |             |             |
continue  | Bourne     |             |             |
declare   |            |             |             |
dirs      |            |             |             |
disown    |            |             |             |
echo      |            |             |             |
enable    |            |             |             |
eval      | Bourne     |             |             |
exec      | Bourne     |             |             |
exit      | Bourne     |             |             |
export    | Bourne     |             |             |
false     |            |             |             |
fc        |            |             |             |
fg        |            |             |             |
getopts   | Bourne     |             |             |
hash      | Bourne     |             |             |
help      |            |             |             |
history   |            |             |             |
jobs      |            |             |             |
kill      |            |             |             |
let       |            |             |             |
local     |            |             |             |
logout    |            |             |             |
mapfile   |            |             |             |
printf    |            |             |             |
popd      |            |             |             |
pushd     |            |             |             |
pwd       | Bourne     |             |             |
read      |            |             |             |
readarray |            |             |             |
readonly  | Bourne     |             |             |
return    | Bourne     | function op
set       |            |             |             |
shift     | Bourne     | remove arg from stack
shopt     |            |             |             |
source    |            |             |             |
suspend   |            |             |             |
test      | Bourne     |             |             |
times     | Bourne     |             |             |
trap      | Bourne     |             |             |
true      |            |             |             |
type      |            |             |             |
typeset   |            | declare     |             |
ulimit    |            |             |             |
umask     | Bourne     |             |             |
unalias   |            |             |             |
unset     | Bourne     |             |             |
wait      |            |             |             |
`{`       | keyword    |             |             |
`}`       | keyword    |             |             |
`!`       | keyword    |             |             |
`[[`      | keyword    |             |             |
`]]`      | keyword    |             |             |
if        | keyword    |             |             |
then      | keyword    |             |             |
else      | keyword    |             |             |
elif      | keyword    |             |             |
fi        | keyword    |             |             |
case      | keyword    |             |             |
esac      | keyword    |             |             |
for       | keyword    |             |             |
select    | keyword    |             |             |
while     | keyword    |             |             |
until     | keyword    |             |             |
do        | keyword    |             |             |
done      | keyword    |             |             |
in        | keyword    |             |             |
function  | keyword    |             |             |
time      | keyword    |             |             |
coproc    | keyword    |             |             |

`||`      | control    |             |             |
`&`       | control    |             |             |
`&&`      | control    |             |             |
`;`       | control    |             |             |
`;;`      | control    |             |             |
`;&`      | control    |             |             |
`;;&`     | control    |             |             |
`|`       | control    | pipe        |             |
`|&`      | control    | pipe both stdout, stderr  |
`(`       | control    |             |             |
`)`       | control    |             |             |

`\n`      | control    | whitespace  |             |
`\t`      | whitespace |             |             |
_SPACE_   | whitespace |             |             |


`[n]<word`    | general format for redirecting input
`[n]>[|]word` | general format for redirecting output
`[n]>>word`   | general format for appending output
`&>word`      | redirect stdout,stderr, equiv to `>word 2>&1`, *preferred*
`>&word`      | same as above but "word" may not expand to a number or `-` ¹
`&>>word`     | appending stdout, stderr
`>>word 2>&1` | above is equivalent to this


`>&-`         | close fd
`<&-`         | close fd
`[n]<word`    | redirect input from FD n, n defaults to 0 if unspecified
`[n]>word`    | redirect output  to FD n, n defaults to 1 if unspecified
`[n]<&digit-` | move input fd
`[n]>&digit-` | move output fd
`[n]<>word`   | open for reading and writing


`>>n`      | meta       | prepend to FD n
`<n`       | meta       | input from FD n
`<<`       | meta       | heredoc
`<<<`      | meta       | herestring


`[[ word ~= pat ]]` | conditional re pattern matching, needs no quoting
`[[ … ]]`   | conditional, test
`$(( … ))`  | arithmetic expansion, alpha vars need no $, can use C constructs
`>(( … ))`  | process substitution |


`-x`          | command param | 
`-`           | command param | 
`--`          | command param | 
`--long-opt`  | command param | 

https://www.gnu.org/software/bash/manual/html_node/Redirections.html

## Heredoc

```bash
[n]<<[-]word
  here-document
delimiter
```

## Herestring

`[n]<<< word` Version of heredoc



## Tokens
* Tokens
  - shell words
  - builtins
  - reserved words
    - keywords
    - metacharacters: make part of meta operators
    - whitespace characters `$IFS`
    - operators
      - control operator
      - redirection operator


* Bash builtins (21)
  - alias
  - bind
  - builtin
  - caller
  - command
  - declare
  - echo
  - enable
  - help
  - let
  - local
  - logout
  - mapfile
  - printf
  - read
  - readarray
  - source
  - type
  - typeset
  - ulimit
  - unalias
