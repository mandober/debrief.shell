# SYNOPSIS

git config [<file-option>] [--type=<type>]                                                                                                --add             <name>  <value>
git config [<file-option>] [--type=<type>] [--fixed-value] [--show-origin] [--show-scope] [-z|--null]                                                       <name> [<value> [<value-pattern>]]
git config [<file-option>] [--type=<type>] [--fixed-value]                                                                                --replace-all     <name>  <value> [<value-pattern>]
git config [<file-option>] [--type=<type>]                 [--show-origin] [--show-scope] [-z|--null] [--fixed-value]                     --get             <name>          [<value-pattern>]
git config [<file-option>] [--type=<type>]                 [--show-origin] [--show-scope] [-z|--null] [--fixed-value]                     --get-all         <name>          [<value-pattern>]
git config [<file-option>] [--type=<type>]                 [--show-origin] [--show-scope] [-z|--null] [--fixed-value] [--name-only]       --get-regexp      <name-regex>    [<value-pattern>]
git config [<file-option>] [--type=<type>]                                                [-z|--null]                                     --get-urlmatch    <name>  <URL>
git config [<file-option>] [--fixed-value]                                                                                                --unset           <name>          [<value-pattern>]
git config [<file-option>] [--fixed-value]                                                                                                --unset-all       <name>          [<value-pattern>]
git config [<file-option>]                                                                                                                --rename-section  <old-name> <new-name>
git config [<file-option>]                                                                                                                --remove-section  <name>
git config [<file-option>]                                 [--show-origin] [--show-scope] [-z|--null]                 [--name-only] -l |  --list
git config [<file-option>]                                                                                                                --get-color       <name>          [<default>]
git config [<file-option>]                                                                                                                --get-colorbool   <name>          [<stdout-is-tty>]
git config [<file-option>]                                                                                                          -e |  --edit
