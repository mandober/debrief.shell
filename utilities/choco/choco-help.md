# choco

Chocolatey v0.10.11
Please run 'choco -?' or 'choco <command> -?' for help menu.

`choco -?`
This is a listing of all of the different things you can pass to choco.

## Commands

* list      - lists remote or local packages
* search    - searches remote or local packages (alias for list)
* install   - installs packages from various sources
* uninstall - uninstalls a package
* upgrade   - upgrades packages from various sources
* config    - Retrieve and configure config file settings

* feature   - view and configure choco features
* info      - retrieves package info. Same as: `choco search pkgname --exact --verbose`
* source    - view and configure default sources
* pin       - suppress upgrades for a package
* outdated  - retrieves packages that are outdated. Similar to upgrade all --noop
* pack      - packages up a nuspec to a compiled nupkg
* push      - pushes a compiled nupkg
* new       - generates files necessary for a chocolatey package from a template
* setapikey - retrieves or saves an apikey for a particular source (alias for apikey)
* apikey    - retrieves or saves an apikey for a particular source
* unpackself- have chocolatey set itself up

* update  - [DEPRECATED] RESERVED for future use (see upgrade)
* version - [DEPRECATED] will be removed in v1 - use `choco outdated` or `cup <pkg|all> -whatif` instead

Please run chocolatey with `choco command -help` for specific help on each command.



## How To Pass Options and Switches

You can pass options and switches in the following ways:

* Unless stated otherwise, an option/switch should only be passed one time.
  Otherwise you may find weird/non-supported behavior.

* `-`, `/`, or `--` (one character switches should not use `--`)

* **Compound Options**
  One character switches can be bundled. 
  e.g. `-d` (debug), `-f` (force), `-v` (verbose), and `-y`
  (confirm yes) can be bundled as `-dfvy`.

* NOTE: If `debug` or `verbose` are bundled with local options
  (not the global ones above), some logging may not show up until after
  the local options are parsed.

* **Optional Equals**
  equals sign `=` between options and values is optional.

* **Quote Values**
  When you need to quote an entire argument, such as when using spaces,
  use a combination of dquotes and squotes, "'value'"
  In cmd.exe you can just use dquotes, "value" but
  in powershell.exe you should use backticks, `"value"` or  s-quotes, 'value'
  Using the combination allows for both shells to work without issue, except 
  for when the next section applies.

* **Periods in PowerShell**
  If you need to pass a period as part of a value or a path, PowerShell doesn't 
  always handle it well. Please quote those values using "Quote Values" (above).

* **Pass quotes in arguments**
  When you need to pass quoted values to to something like a native installer,
  you are in for a world of fun.
  In cmd.exe pass it like this: `-ia "/yo=""Spaces spaces"""`
  In PowerShell.exe pass it like this: `-ia '/yo=""Spaces spaces""'`
  No other combination will work.
  In PowerShell.exe if you are on version v3+, you can try `--%` before `-ia` 
  to just pass the args through as is, which means it should not require any 
  special workarounds.

* Options and switches apply to all items passed, so if you are installing 
  multiple packages, and you use `--version=1.0.0`, choco is going to look 
  for and try to install version 1.0.0 of every package passed. So please 
  split out multiple package calls when wanting to pass specific options.


## Default Options and Switches

`-y, --yes, --confirm`
Chooses affirmative answer instead of prompting. Implies `--accept-license`

`-r, --limitoutput, --limit-output`
LimitOutput. Limit the output to essential information


`-?, --help, -h`
Prints out the help menu.

`-f, --force`
Force the behavior. Do not use force during normal operation; it subverts 
some of the smart behavior for commands.

`-v, --verbose` Verbose
Show verbose messaging. Very verbose messaging, avoid using normally.


`--noop, --whatif, --what-if`
NoOp. Don't actually do anything, just print as if.

`-c, --cache, --cachelocation, --cache-location=VALUE`
CacheLocation for download cache, defaults to %TEMP% or value in `chocolatey.config` file.

`--timeout, --execution-timeout=VALUE`
CommandExecutionTimeout (in seconds)
The time to allow a command to finish before timing out.
Overrides the default execution timeout in the configuration of 2700 seconds.
'0' for infinite starting in 0.10.4.

`--use-system-powershell`
UseSystemPowerShell. Execute PowerShell using an external process instead of 
the built-in PowerShell host. Should only be used when internal host is failing.
Available in 0.9.10+.

`-d, --debug` Debug
Show debug messaging.

`--trace` Trace
Show trace messaging. Very, very verbose trace messaging.
Avoid except when needing super low-level .NET Framework debugging.
Available in 0.10.4+.

`--nocolor, --no-color` No Color
Do not show colorization in logging output.
This overrides the feature `logWithoutColor`.
Available in 0.10.9+.

`--acceptlicense, --accept-license`
AcceptLicense dialogs automatically. Reserved for future use.

`--failstderr, --failonstderr, --fail-on-stderr`
`--fail-on-standard-error, --fail-on-error-output`
FailOnStandardError. 
Fail on standard error output (stderr), typically received when running external 
commands during install providers. This overrides the feature `failOnStandardError`

`--no-progress`
Do Not Show Progress. Do not show download progress percentages.
Available in 0.10.4+.

`--log-file=VALUE`
Log File to output to in addition to regular loggers. Available in 0.1-0.8+.

`--allowunofficial, --allow-unofficial`,
`--allowunofficialbuild, --allow-unofficial-build`
When not using the official build you must set
this flag for choco to continue.





`--proxy=VALUE`
Proxy Location. Explicit proxy location. Overrides the default proxy
location of ''. Available for config settings in 0.9.9.9+, this CLI
option available in 0.10.4+.

`--proxy-user=VALUE`
Proxy User Name - Explicit proxy user (optional). Requires explicity
proxy (`--proxy` or config setting). Overrides the default proxy user of
''. Available for config settings in 0.9.9.9+, this CLI option available
in 0.10.4+.

`--proxy-password=VALUE`
Proxy Password - Explicit proxy password (optional) to be used with
username. Requires explicity proxy (`--proxy` or config setting) and
user name.  Overrides the default proxy password (encrypted in settings
if set). Available for config settings in 0.9.9.9+, this CLI option
available in 0.10.4+.

`--proxy-bypass-list=VALUE`
ProxyBypassList - Comma separated list of regex locations to bypass on
proxy. Requires explicity proxy (`--proxy` or config setting). Overrides
the default proxy bypass list of ''. Available in 0.10.4+.

`--proxy-bypass-on-local`
Proxy Bypass On Local - Bypass proxy for local connections. Requires
explicity proxy (`--proxy` or config setting). Overrides the default
proxy bypass on local setting of 'True'. Available in 0.10.4+.

