# Bash :: Index :: Variables

Shell variables have
- a name, `foo=abc`
- a value, `bar=42`
- expansions
  - refer to a var (expand it): `${foo}`, `${foo}`
  - variable expansions
    - patterns ...
- attributes
  - integer `declare -n int`
  - indirection e.g. `declare -n ref=bar`
- expansions
  `${foo}`

may also be referenced by name without using the parameter expansion syntax.


* Variables
  - shell variables
  - bash variables
    - sh variables (inherited from sh shell)
  - env variables
    - exported variables
  - user variables
  - bash attributes for variables
  - parameters


- explicit pattern: `${α}`
  where `α` is an identifier, the name of variable (variable name), a label
  identifier, name, label, binding
- implicit pattern: `$α`
