---
downloaded:       2021-12-04
page-url:         https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreautocrlf
page-title:       Git - git-config Documentation
article-title:    Git - git-config Documentation
---
# Git - git-config Documentation

Note that this list is non-comprehensive and not necessarily complete.
For command-specific variables, you will find a more detailed description
in the appropriate manual page.
Note that this list is non-comprehensive and not necessarily complete. For command-specific variables, you will find a more detailed description in the appropriate manual page.

Other git-related tools may and do use their own variables. When inventing new variables for use in your own tool, make sure their names do not conflict with those that are used by Git itself and other popular tools, and describe them in your documentation.

[][1]advice.\*

These variables control various optional help messages designed to aid new users. All *advice.\** variables default to *true*, and you can tell Git that you do not need help by setting these to *false*:

[][2]fetchShowForcedUpdates

Advice shown when [git-fetch\[1\]][3] takes a long time to calculate forced updates after ref updates, or to warn that the check is disabled.

[][4]pushUpdateRejected

Set this variable to *false* if you want to disable *pushNonFFCurrent*, *pushNonFFMatching*, *pushAlreadyExists*, *pushFetchFirst*, *pushNeedsForce*, and *pushRefNeedsUpdate* simultaneously.

[][5]pushNonFFCurrent

Advice shown when [git-push\[1\]][6] fails due to a non-fast-forward update to the current branch.

[][7]pushNonFFMatching

Advice shown when you ran [git-push\[1\]][8] and pushed *matching refs* explicitly (i.e. you used *:*, or specified a refspec that isn’t your current branch) and it resulted in a non-fast-forward error.

[][9]pushAlreadyExists

Shown when [git-push\[1\]][10] rejects an update that does not qualify for fast-forwarding (e.g., a tag.)

[][11]pushFetchFirst

Shown when [git-push\[1\]][12] rejects an update that tries to overwrite a remote ref that points at an object we do not have.

[][13]pushNeedsForce

Shown when [git-push\[1\]][14] rejects an update that tries to overwrite a remote ref that points at an object that is not a commit-ish, or make the remote ref point at an object that is not a commit-ish.

[][15]pushUnqualifiedRefname

Shown when [git-push\[1\]][16] gives up trying to guess based on the source and destination refs what remote ref namespace the source belongs in, but where we can still suggest that the user push to either refs/heads/\* or refs/tags/\* based on the type of the source object.

[][17]pushRefNeedsUpdate

Shown when [git-push\[1\]][18] rejects a forced update of a branch when its remote-tracking ref has updates that we do not have locally.

[][19]skippedCherryPicks

Shown when [git-rebase\[1\]][20] skips a commit that has already been cherry-picked onto the upstream branch.

[][21]statusAheadBehind

Shown when [git-status\[1\]][22] computes the ahead/behind counts for a local ref compared to its remote tracking ref, and that calculation takes longer than expected. Will not appear if `status.aheadBehind` is false or the option `--no-ahead-behind` is given.

[][23]statusHints

Show directions on how to proceed from the current state in the output of [git-status\[1\]][24], in the template shown when writing commit messages in [git-commit\[1\]][25], and in the help message shown by [git-switch\[1\]][26] or [git-checkout\[1\]][27] when switching branch.

[][28]statusUoption

Advise to consider using the `-u` option to [git-status\[1\]][29] when the command takes more than 2 seconds to enumerate untracked files.

[][30]commitBeforeMerge

Advice shown when [git-merge\[1\]][31] refuses to merge to avoid overwriting local changes.

[][32]resetQuiet

Advice to consider using the `--quiet` option to [git-reset\[1\]][33] when the command takes more than 2 seconds to enumerate unstaged changes after reset.

[][34]resolveConflict

Advice shown by various commands when conflicts prevent the operation from being performed.

[][35]sequencerInUse

Advice shown when a sequencer command is already in progress.

[][36]implicitIdentity

Advice on how to set your identity configuration when your information is guessed from the system username and domain name.

[][37]detachedHead

Advice shown when you used [git-switch\[1\]][38] or [git-checkout\[1\]][39] to move to the detach HEAD state, to instruct how to create a local branch after the fact.

[][40]checkoutAmbiguousRemoteBranchName

Advice shown when the argument to [git-checkout\[1\]][41] and [git-switch\[1\]][42] ambiguously resolves to a remote tracking branch on more than one remote in situations where an unambiguous argument would have otherwise caused a remote-tracking branch to be checked out. See the `checkout.defaultRemote` configuration variable for how to set a given remote to used by default in some situations where this advice would be printed.

[][43]amWorkDir

Advice that shows the location of the patch file when [git-am\[1\]][44] fails to apply it.

[][45]rmHints

In case of failure in the output of [git-rm\[1\]][46], show directions on how to proceed from the current state.

[][47]addEmbeddedRepo

Advice on what to do when you’ve accidentally added one git repo inside of another.

[][48]ignoredHook

Advice shown if a hook is ignored because the hook is not set as executable.

[][49]waitingForEditor

Print a message to the terminal whenever Git is waiting for editor input from the user.

[][50]nestedTag

Advice shown if a user attempts to recursively tag a tag object.

[][51]submoduleAlternateErrorStrategyDie

Advice shown when a submodule.alternateErrorStrategy option configured to "die" causes a fatal error.

[][52]addIgnoredFile

Advice shown if a user attempts to add an ignored file to the index.

[][53]addEmptyPathspec

Advice shown if a user runs the add command without providing the pathspec parameter.

[][54]updateSparsePath

Advice shown when either [git-add\[1\]][55] or [git-rm\[1\]][56] is asked to update index entries outside the current sparse checkout.

[][57]core.fileMode

Tells Git if the executable bit of files in the working tree is to be honored.

Some filesystems lose the executable bit when a file that is marked as executable is checked out, or checks out a non-executable file with executable bit on. [git-clone\[1\]][58] or [git-init\[1\]][59] probe the filesystem to see if it handles the executable bit correctly and this variable is automatically set as necessary.

A repository, however, may be on a filesystem that handles the filemode correctly, and this variable is set to *true* when created, but later may be made accessible from another environment that loses the filemode (e.g. exporting ext4 via CIFS mount, visiting a Cygwin created repository with Git for Windows or Eclipse). In such a case it may be necessary to set this variable to *false*. See [git-update-index\[1\]][60].

The default is true (when core.filemode is not specified in the config file).

[][61]core.hideDotFiles

(Windows-only) If true, mark newly-created directories and files whose name starts with a dot as hidden. If *dotGitOnly*, only the `.git/` directory is hidden, but no other files starting with a dot. The default mode is *dotGitOnly*.

[][62]core.ignoreCase

Internal variable which enables various workarounds to enable Git to work better on filesystems that are not case sensitive, like APFS, HFS+, FAT, NTFS, etc. For example, if a directory listing finds "makefile" when Git expects "Makefile", Git will assume it is really the same file, and continue to remember it as "Makefile".

The default is false, except [git-clone\[1\]][63] or [git-init\[1\]][64] will probe and set core.ignoreCase true if appropriate when the repository is created.

Git relies on the proper configuration of this variable for your operating and file system. Modifying this value may result in unexpected behavior.

[][65]core.precomposeUnicode

This option is only used by Mac OS implementation of Git. When core.precomposeUnicode=true, Git reverts the unicode decomposition of filenames done by Mac OS. This is useful when sharing a repository between Mac OS and Linux or Windows. (Git for Windows 1.7.10 or higher is needed, or Git under cygwin 1.7). When false, file names are handled fully transparent by Git, which is backward compatible with older versions of Git.

[][66]core.protectHFS

If set to true, do not allow checkout of paths that would be considered equivalent to `.git` on an HFS+ filesystem. Defaults to `true` on Mac OS, and `false` elsewhere.

[][67]core.protectNTFS

If set to true, do not allow checkout of paths that would cause problems with the NTFS filesystem, e.g. conflict with 8.3 "short" names. Defaults to `true` on Windows, and `false` elsewhere.

[][68]core.fsmonitor

If set, the value of this variable is used as a command which will identify all files that may have changed since the requested date/time. This information is used to speed up git by avoiding unnecessary processing of files that have not changed. See the "fsmonitor-watchman" section of [githooks\[5\]][69].

[][70]core.fsmonitorHookVersion

Sets the version of hook that is to be used when calling fsmonitor. There are currently versions 1 and 2. When this is not set, version 2 will be tried first and if it fails then version 1 will be tried. Version 1 uses a timestamp as input to determine which files have changes since that time but some monitors like watchman have race conditions when used with a timestamp. Version 2 uses an opaque string so that the monitor can return something that can be used to determine what files have changed without race conditions.

[][71]core.trustctime

If false, the ctime differences between the index and the working tree are ignored; useful when the inode change time is regularly modified by something outside Git (file system crawlers and some backup systems). See [git-update-index\[1\]][72]. True by default.

[][73]core.splitIndex

If true, the split-index feature of the index will be used. See [git-update-index\[1\]][74]. False by default.

[][75]core.untrackedCache

Determines what to do about the untracked cache feature of the index. It will be kept, if this variable is unset or set to `keep`. It will automatically be added if set to `true`. And it will automatically be removed, if set to `false`. Before setting it to `true`, you should check that mtime is working properly on your system. See [git-update-index\[1\]][76]. `keep` by default, unless `feature.manyFiles` is enabled which sets this setting to `true` by default.

[][77]core.checkStat

When missing or is set to `default`, many fields in the stat structure are checked to detect if a file has been modified since Git looked at it. When this configuration variable is set to `minimal`, sub-second part of mtime and ctime, the uid and gid of the owner of the file, the inode number (and the device number, if Git was compiled to use it), are excluded from the check among these fields, leaving only the whole-second part of mtime (and ctime, if `core.trustCtime` is set) and the filesize to be checked.

There are implementations of Git that do not leave usable values in some fields (e.g. JGit); by excluding these fields from the comparison, the `minimal` mode may help interoperability when the same repository is used by these other systems at the same time.

[][78]core.quotePath

Commands that output paths (e.g. *ls-files*, *diff*), will quote "unusual" characters in the pathname by enclosing the pathname in double-quotes and escaping those characters with backslashes in the same way C escapes control characters (e.g. `\t` for TAB, `\n` for LF, `\\` for backslash) or bytes with values larger than 0x80 (e.g. octal `\302\265` for "micro" in UTF-8). If this variable is set to false, bytes higher than 0x80 are not considered "unusual" any more. Double-quotes, backslash and control characters are always escaped regardless of the setting of this variable. A simple space character is not considered "unusual". Many commands can output pathnames completely verbatim using the `-z` option. The default value is true.

[][79]core.eol

Sets the line ending type to use in the working directory for files that are marked as text (either by having the `text` attribute set, or by having `text=auto` and Git auto-detecting the contents as text). Alternatives are *lf*, *crlf* and *native*, which uses the platform’s native line ending. The default value is `native`. See [gitattributes\[5\]][80] for more information on end-of-line conversion. Note that this value is ignored if `core.autocrlf` is set to `true` or `input`.

[][81]core.safecrlf

If true, makes Git check if converting `CRLF` is reversible when end-of-line conversion is active. Git will verify if a command modifies a file in the work tree either directly or indirectly. For example, committing a file followed by checking out the same file should yield the original file in the work tree. If this is not the case for the current setting of `core.autocrlf`, Git will reject the file. The variable can be set to "warn", in which case Git will only warn about an irreversible conversion but continue the operation.

CRLF conversion bears a slight chance of corrupting data. When it is enabled, Git will convert CRLF to LF during commit and LF to CRLF during checkout. A file that contains a mixture of LF and CRLF before the commit cannot be recreated by Git. For text files this is the right thing to do: it corrects line endings such that we have only LF line endings in the repository. But for binary files that are accidentally classified as text the conversion can corrupt data.

If you recognize such corruption early you can easily fix it by setting the conversion type explicitly in .gitattributes. Right after committing you still have the original file in your work tree and this file is not yet corrupted. You can explicitly tell Git that this file is binary and Git will handle the file appropriately.

Unfortunately, the desired effect of cleaning up text files with mixed line endings and the undesired effect of corrupting binary files cannot be distinguished. In both cases CRLFs are removed in an irreversible way. For text files this is the right thing to do because CRLFs are line endings, while for binary files converting CRLFs corrupts data.

Note, this safety check does not mean that a checkout will generate a file identical to the original file for a different setting of `core.eol` and `core.autocrlf`, but only for the current one. For example, a text file with `LF` would be accepted with `core.eol=lf` and could later be checked out with `core.eol=crlf`, in which case the resulting file would contain `CRLF`, although the original file contained `LF`. However, in both work trees the line endings would be consistent, that is either all `LF` or all `CRLF`, but never mixed. A file with mixed line endings would be reported by the `core.safecrlf` mechanism.

[][82]core.autocrlf

Setting this variable to "true" is the same as setting the `text` attribute to "auto" on all files and core.eol to "crlf". Set to true if you want to have `CRLF` line endings in your working directory and the repository has LF line endings. This variable can be set to *input*, in which case no output conversion is performed.

[][83]core.checkRoundtripEncoding

A comma and/or whitespace separated list of encodings that Git performs UTF-8 round trip checks on if they are used in an `working-tree-encoding` attribute (see [gitattributes\[5\]][84]). The default value is `SHIFT-JIS`.

[][85]core.symlinks

If false, symbolic links are checked out as small plain files that contain the link text. [git-update-index\[1\]][86] and [git-add\[1\]][87] will not change the recorded type to regular file. Useful on filesystems like FAT that do not support symbolic links.

The default is true, except [git-clone\[1\]][88] or [git-init\[1\]][89] will probe and set core.symlinks false if appropriate when the repository is created.

[][90]core.gitProxy

A "proxy command" to execute (as *command host port*) instead of establishing direct connection to the remote server when using the Git protocol for fetching. If the variable value is in the "COMMAND for DOMAIN" format, the command is applied only on hostnames ending with the specified domain string. This variable may be set multiple times and is matched in the given order; the first match wins.

Can be overridden by the `GIT_PROXY_COMMAND` environment variable (which always applies universally, without the special "for" handling).

The special string `none` can be used as the proxy command to specify that no proxy be used for a given domain pattern. This is useful for excluding servers inside a firewall from proxy use, while defaulting to a common proxy for external domains.

[][91]core.sshCommand

If this variable is set, `git fetch` and `git push` will use the specified command instead of `ssh` when they need to connect to a remote system. The command is in the same form as the `GIT_SSH_COMMAND` environment variable and is overridden when the environment variable is set.

[][92]core.ignoreStat

If true, Git will avoid using lstat() calls to detect if files have changed by setting the "assume-unchanged" bit for those tracked files which it has updated identically in both the index and working tree.

When files are modified outside of Git, the user will need to stage the modified files explicitly (e.g. see *Examples* section in [git-update-index\[1\]][93]). Git will not normally detect changes to those files.

This is useful on systems where lstat() calls are very slow, such as CIFS/Microsoft Windows.

False by default.

[][94]core.preferSymlinkRefs

Instead of the default "symref" format for HEAD and other symbolic reference files, use symbolic links. This is sometimes needed to work with old scripts that expect HEAD to be a symbolic link.

[][95]core.alternateRefsCommand

When advertising tips of available history from an alternate, use the shell to execute the specified command instead of [git-for-each-ref\[1\]][96]. The first argument is the absolute path of the alternate. Output must contain one hex object id per line (i.e., the same as produced by `git for-each-ref --format='%(objectname)'`).

Note that you cannot generally put `git for-each-ref` directly into the config value, as it does not take a repository path as an argument (but you can wrap the command above in a shell script).

[][97]core.alternateRefsPrefixes

When listing references from an alternate, list only references that begin with the given prefix. Prefixes match as if they were given as arguments to [git-for-each-ref\[1\]][98]. To list multiple prefixes, separate them with whitespace. If `core.alternateRefsCommand` is set, setting `core.alternateRefsPrefixes` has no effect.

[][99]core.bare

If true this repository is assumed to be *bare* and has no working directory associated with it. If this is the case a number of commands that require a working directory will be disabled, such as [git-add\[1\]][100] or [git-merge\[1\]][101].

This setting is automatically guessed by [git-clone\[1\]][102] or [git-init\[1\]][103] when the repository was created. By default a repository that ends in "/.git" is assumed to be not bare (bare = false), while all other repositories are assumed to be bare (bare = true).

[][104]core.worktree

Set the path to the root of the working tree. If `GIT_COMMON_DIR` environment variable is set, core.worktree is ignored and not used for determining the root of working tree. This can be overridden by the `GIT_WORK_TREE` environment variable and the `--work-tree` command-line option. The value can be an absolute path or relative to the path to the .git directory, which is either specified by --git-dir or GIT\_DIR, or automatically discovered. If --git-dir or GIT\_DIR is specified but none of --work-tree, GIT\_WORK\_TREE and core.worktree is specified, the current working directory is regarded as the top level of your working tree.

Note that this variable is honored even when set in a configuration file in a ".git" subdirectory of a directory and its value differs from the latter directory (e.g. "/path/to/.git/config" has core.worktree set to "/different/path"), which is most likely a misconfiguration. Running Git commands in the "/path/to" directory will still use "/different/path" as the root of the work tree and can cause confusion unless you know what you are doing (e.g. you are creating a read-only snapshot of the same index to a location different from the repository’s usual working tree).

[][105]core.logAllRefUpdates

Enable the reflog. Updates to a ref <ref> is logged to the file "`$GIT_DIR/logs/<ref>`", by appending the new and old SHA-1, the date/time and the reason of the update, but only when the file exists. If this configuration variable is set to `true`, missing "`$GIT_DIR/logs/<ref>`" file is automatically created for branch heads (i.e. under `refs/heads/`), remote refs (i.e. under `refs/remotes/`), note refs (i.e. under `refs/notes/`), and the symbolic ref `HEAD`. If it is set to `always`, then a missing reflog is automatically created for any ref under `refs/`.

This information can be used to determine what commit was the tip of a branch "2 days ago".

This value is true by default in a repository that has a working directory associated with it, and false by default in a bare repository.

[][106]core.repositoryFormatVersion

Internal variable identifying the repository format and layout version.

[][107]core.sharedRepository

When *group* (or *true*), the repository is made shareable between several users in a group (making sure all the files and objects are group-writable). When *all* (or *world* or *everybody*), the repository will be readable by all users, additionally to being group-shareable. When *umask* (or *false*), Git will use permissions reported by umask(2). When *0xxx*, where *0xxx* is an octal number, files in the repository will have this mode value. *0xxx* will override user’s umask value (whereas the other options will only override requested parts of the user’s umask value). Examples: *0660* will make the repo read/write-able for the owner and group, but inaccessible to others (equivalent to *group* unless umask is e.g. *0022*). *0640* is a repository that is group-readable but not group-writable. See [git-init\[1\]][108]. False by default.

[][109]core.warnAmbiguousRefs

If true, Git will warn you if the ref name you passed it is ambiguous and might match multiple refs in the repository. True by default.

[][110]core.compression

An integer -1..9, indicating a default compression level. -1 is the zlib default. 0 means no compression, and 1..9 are various speed/size tradeoffs, 9 being slowest. If set, this provides a default to other compression variables, such as `core.looseCompression` and `pack.compression`.

[][111]core.looseCompression

An integer -1..9, indicating the compression level for objects that are not in a pack file. -1 is the zlib default. 0 means no compression, and 1..9 are various speed/size tradeoffs, 9 being slowest. If not set, defaults to core.compression. If that is not set, defaults to 1 (best speed).

[][112]core.packedGitWindowSize

Number of bytes of a pack file to map into memory in a single mapping operation. Larger window sizes may allow your system to process a smaller number of large pack files more quickly. Smaller window sizes will negatively affect performance due to increased calls to the operating system’s memory manager, but may improve performance when accessing a large number of large pack files.

Default is 1 MiB if NO\_MMAP was set at compile time, otherwise 32 MiB on 32 bit platforms and 1 GiB on 64 bit platforms. This should be reasonable for all users/operating systems. You probably do not need to adjust this value.

Common unit suffixes of *k*, *m*, or *g* are supported.

[][113]core.packedGitLimit

Maximum number of bytes to map simultaneously into memory from pack files. If Git needs to access more than this many bytes at once to complete an operation it will unmap existing regions to reclaim virtual address space within the process.

Default is 256 MiB on 32 bit platforms and 32 TiB (effectively unlimited) on 64 bit platforms. This should be reasonable for all users/operating systems, except on the largest projects. You probably do not need to adjust this value.

Common unit suffixes of *k*, *m*, or *g* are supported.

[][114]core.deltaBaseCacheLimit

Maximum number of bytes per thread to reserve for caching base objects that may be referenced by multiple deltified objects. By storing the entire decompressed base objects in a cache Git is able to avoid unpacking and decompressing frequently used base objects multiple times.

Default is 96 MiB on all platforms. This should be reasonable for all users/operating systems, except on the largest projects. You probably do not need to adjust this value.

Common unit suffixes of *k*, *m*, or *g* are supported.

[][115]core.bigFileThreshold

Files larger than this size are stored deflated, without attempting delta compression. Storing large files without delta compression avoids excessive memory usage, at the slight expense of increased disk usage. Additionally files larger than this size are always treated as binary.

Default is 512 MiB on all platforms. This should be reasonable for most projects as source code and other text files can still be delta compressed, but larger binary media files won’t be.

Common unit suffixes of *k*, *m*, or *g* are supported.

[][116]core.excludesFile

Specifies the pathname to the file that contains patterns to describe paths that are not meant to be tracked, in addition to `.gitignore` (per-directory) and `.git/info/exclude`. Defaults to `$XDG_CONFIG_HOME/git/ignore`. If `$XDG_CONFIG_HOME` is either not set or empty, `$HOME/.config/git/ignore` is used instead. See [gitignore\[5\]][117].

[][118]core.askPass

Some commands (e.g. svn and http interfaces) that interactively ask for a password can be told to use an external program given via the value of this variable. Can be overridden by the `GIT_ASKPASS` environment variable. If not set, fall back to the value of the `SSH_ASKPASS` environment variable or, failing that, a simple password prompt. The external program shall be given a suitable prompt as command-line argument and write the password on its STDOUT.

[][119]core.attributesFile

In addition to `.gitattributes` (per-directory) and `.git/info/attributes`, Git looks into this file for attributes (see [gitattributes\[5\]][120]). Path expansions are made the same way as for `core.excludesFile`. Its default value is `$XDG_CONFIG_HOME/git/attributes`. If `$XDG_CONFIG_HOME` is either not set or empty, `$HOME/.config/git/attributes` is used instead.

[][121]core.hooksPath

By default Git will look for your hooks in the `$GIT_DIR/hooks` directory. Set this to different path, e.g. `/etc/git/hooks`, and Git will try to find your hooks in that directory, e.g. `/etc/git/hooks/pre-receive` instead of in `$GIT_DIR/hooks/pre-receive`.

The path can be either absolute or relative. A relative path is taken as relative to the directory where the hooks are run (see the "DESCRIPTION" section of [githooks\[5\]][122]).

This configuration variable is useful in cases where you’d like to centrally configure your Git hooks instead of configuring them on a per-repository basis, or as a more flexible and centralized alternative to having an `init.templateDir` where you’ve changed default hooks.

[][123]core.editor

Commands such as `commit` and `tag` that let you edit messages by launching an editor use the value of this variable when it is set, and the environment variable `GIT_EDITOR` is not set. See [git-var\[1\]][124].

Commands such as `commit` and `tag` that let you edit messages consider a line that begins with this character commented, and removes them after the editor returns (default *#*).

If set to "auto", `git-commit` would select a character that is not the beginning character of any line in existing commit messages.

[][125]core.filesRefLockTimeout

The length of time, in milliseconds, to retry when trying to lock an individual reference. Value 0 means not to retry at all; -1 means to try indefinitely. Default is 100 (i.e., retry for 100ms).

[][126]core.packedRefsTimeout

The length of time, in milliseconds, to retry when trying to lock the `packed-refs` file. Value 0 means not to retry at all; -1 means to try indefinitely. Default is 1000 (i.e., retry for 1 second).

Text viewer for use by Git commands (e.g., *less*). The value is meant to be interpreted by the shell. The order of preference is the `$GIT_PAGER` environment variable, then `core.pager` configuration, then `$PAGER`, and then the default chosen at compile time (usually *less*).

When the `LESS` environment variable is unset, Git sets it to `FRX` (if `LESS` environment variable is set, Git does not change it at all). If you want to selectively override Git’s default setting for `LESS`, you can set `core.pager` to e.g. `less -S`. This will be passed to the shell by Git, which will translate the final command to `LESS=FRX less -S`. The environment does not set the `S` option but the command line does, instructing less to truncate long lines. Similarly, setting `core.pager` to `less -+F` will deactivate the `F` option specified by the environment from the command-line, deactivating the "quit if one screen" behavior of `less`. One can specifically activate some flags for particular commands: for example, setting `pager.blame` to `less -S` enables line truncation only for `git blame`.

Likewise, when the `LV` environment variable is unset, Git sets it to `-c`. You can override this setting by exporting `LV` with another value or setting `core.pager` to `lv +c`.

[][127]core.whitespace

A comma separated list of common whitespace problems to notice. *git diff* will use `color.diff.whitespace` to highlight them, and *git apply --whitespace=error* will consider them as errors. You can prefix `-` to disable any of them (e.g. `-trailing-space`):

-   `blank-at-eol` treats trailing whitespaces at the end of the line as an error (enabled by default).
    
-   `space-before-tab` treats a space character that appears immediately before a tab character in the initial indent part of the line as an error (enabled by default).
    
-   `indent-with-non-tab` treats a line that is indented with space characters instead of the equivalent tabs as an error (not enabled by default).
    
-   `tab-in-indent` treats a tab character in the initial indent part of the line as an error (not enabled by default).
    
-   `blank-at-eof` treats blank lines added at the end of file as an error (enabled by default).
    
-   `trailing-space` is a short-hand to cover both `blank-at-eol` and `blank-at-eof`.
    
-   `cr-at-eol` treats a carriage-return at the end of line as part of the line terminator, i.e. with it, `trailing-space` does not trigger if the character before such a carriage-return is not a whitespace (not enabled by default).
    
-   `tabwidth=<n>` tells how many character positions a tab occupies; this is relevant for `indent-with-non-tab` and when Git fixes `tab-in-indent` errors. The default tab width is 8. Allowed values are 1 to 63.
    

[][128]core.fsyncObjectFiles

This boolean will enable *fsync()* when writing object files.

This is a total waste of time and effort on a filesystem that orders data writes properly, but can be useful for filesystems that do not use journalling (traditional UNIX filesystems) or that only journal metadata and not file contents (OS X’s HFS+, or Linux ext3 with "data=writeback").

[][129]core.preloadIndex

Enable parallel index preload for operations like *git diff*

This can speed up operations like *git diff* and *git status* especially on filesystems like NFS that have weak caching semantics and thus relatively high IO latencies. When enabled, Git will do the index comparison to the filesystem data in parallel, allowing overlapping IO’s. Defaults to true.

[][130]core.unsetenvvars

Windows-only: comma-separated list of environment variables' names that need to be unset before spawning any other process. Defaults to `PERL5LIB` to account for the fact that Git for Windows insists on using its own Perl interpreter.

[][131]core.restrictinheritedhandles

Windows-only: override whether spawned processes inherit only standard file handles (`stdin`, `stdout` and `stderr`) or all handles. Can be `auto`, `true` or `false`. Defaults to `auto`, which means `true` on Windows 7 and later, and `false` on older Windows versions.

[][132]core.createObject

You can set this to *link*, in which case a hardlink followed by a delete of the source are used to make sure that object creation will not overwrite existing objects.

On some file system/operating system combinations, this is unreliable. Set this config setting to *rename* there; However, This will remove the check that makes sure that existing object files will not get overwritten.

[][133]core.notesRef

When showing commit messages, also show notes which are stored in the given ref. The ref must be fully qualified. If the given ref does not exist, it is not an error but means that no notes should be printed.

This setting defaults to "refs/notes/commits", and it can be overridden by the `GIT_NOTES_REF` environment variable. See [git-notes\[1\]][134].

[][135]core.commitGraph

If true, then git will read the commit-graph file (if it exists) to parse the graph structure of commits. Defaults to true. See [git-commit-graph\[1\]][136] for more information.

[][137]core.useReplaceRefs

If set to `false`, behave as if the `--no-replace-objects` option was given on the command line. See [git\[1\]][138] and [git-replace\[1\]][139] for more information.

[][140]core.multiPackIndex

Use the multi-pack-index file to track multiple packfiles using a single index. See [git-multi-pack-index\[1\]][141] for more information. Defaults to true.

[][142]core.sparseCheckout

Enable "sparse checkout" feature. See [git-sparse-checkout\[1\]][143] for more information.

[][144]core.sparseCheckoutCone

Enables the "cone mode" of the sparse checkout feature. When the sparse-checkout file contains a limited set of patterns, then this mode provides significant performance advantages. See [git-sparse-checkout\[1\]][145] for more information.

[][146]core.abbrev

Set the length object names are abbreviated to. If unspecified or set to "auto", an appropriate value is computed based on the approximate number of packed objects in your repository, which hopefully is enough for abbreviated object names to stay unique for some time. If set to "no", no abbreviation is made and the object names are shown in their full length. The minimum length is 4.

[][147]add.ignoreErrors

[][148]add.ignore-errors (deprecated)

Tells *git add* to continue adding files when some files cannot be added due to indexing errors. Equivalent to the `--ignore-errors` option of [git-add\[1\]][149]. `add.ignore-errors` is deprecated, as it does not follow the usual naming convention for configuration variables.

[][150]add.interactive.useBuiltin

\[EXPERIMENTAL\] Set to `true` to use the experimental built-in implementation of the interactive version of [git-add\[1\]][151] instead of the Perl script version. Is `false` by default.

[][152]alias.\*

Command aliases for the [git\[1\]][153] command wrapper - e.g. after defining `alias.last = cat-file commit HEAD`, the invocation `git last` is equivalent to `git cat-file commit HEAD`. To avoid confusion and troubles with script usage, aliases that hide existing Git commands are ignored. Arguments are split by spaces, the usual shell quoting and escaping is supported. A quote pair or a backslash can be used to quote them.

Note that the first word of an alias does not necessarily have to be a command. It can be a command-line option that will be passed into the invocation of `git`. In particular, this is useful when used with `-c` to pass in one-time configurations or `-p` to force pagination. For example, `loud-rebase = -c commit.verbose=true rebase` can be defined such that running `git loud-rebase` would be equivalent to `git -c commit.verbose=true rebase`. Also, `ps = -p status` would be a helpful alias since `git ps` would paginate the output of `git status` where the original command does not.

If the alias expansion is prefixed with an exclamation point, it will be treated as a shell command. For example, defining `alias.new = !gitk --all --not ORIG_HEAD`, the invocation `git new` is equivalent to running the shell command `gitk --all --not ORIG_HEAD`. Note that shell commands will be executed from the top-level directory of a repository, which may not necessarily be the current directory. `GIT_PREFIX` is set as returned by running `git rev-parse --show-prefix` from the original current directory. See [git-rev-parse\[1\]][154].

[][155]am.keepcr

If true, git-am will call git-mailsplit for patches in mbox format with parameter `--keep-cr`. In this case git-mailsplit will not remove `\r` from lines ending with `\r\n`. Can be overridden by giving `--no-keep-cr` from the command line. See [git-am\[1\]][156], [git-mailsplit\[1\]][157].

[][158]am.threeWay

By default, `git am` will fail if the patch does not apply cleanly. When set to true, this setting tells `git am` to fall back on 3-way merge if the patch records the identity of blobs it is supposed to apply to and we have those blobs available locally (equivalent to giving the `--3way` option from the command line). Defaults to `false`. See [git-am\[1\]][159].

[][160]apply.ignoreWhitespace

When set to *change*, tells *git apply* to ignore changes in whitespace, in the same way as the `--ignore-space-change` option. When set to one of: no, none, never, false tells *git apply* to respect all whitespace differences. See [git-apply\[1\]][161].

[][162]apply.whitespace

Tells *git apply* how to handle whitespaces, in the same way as the `--whitespace` option. See [git-apply\[1\]][163].

[][164]blame.blankBoundary

Show blank commit object name for boundary commits in [git-blame\[1\]][165]. This option defaults to false.

[][166]blame.coloring

This determines the coloring scheme to be applied to blame output. It can be *repeatedLines*, *highlightRecent*, or *none* which is the default.

[][167]blame.date

Specifies the format used to output dates in [git-blame\[1\]][168]. If unset the iso format is used. For supported values, see the discussion of the `--date` option at [git-log\[1\]][169].

[][170]blame.showEmail

Show the author email instead of author name in [git-blame\[1\]][171]. This option defaults to false.

[][172]blame.showRoot

Do not treat root commits as boundaries in [git-blame\[1\]][173]. This option defaults to false.

[][174]blame.ignoreRevsFile

Ignore revisions listed in the file, one unabbreviated object name per line, in [git-blame\[1\]][175]. Whitespace and comments beginning with `#` are ignored. This option may be repeated multiple times. Empty file names will reset the list of ignored revisions. This option will be handled before the command line option `--ignore-revs-file`.

[][176]blame.markUnblamableLines

Mark lines that were changed by an ignored revision that we could not attribute to another commit with a *\** in the output of [git-blame\[1\]][177].

[][178]blame.markIgnoredLines

Mark lines that were changed by an ignored revision that we attributed to another commit with a *?* in the output of [git-blame\[1\]][179].

[][180]branch.autoSetupMerge

Tells *git branch*, *git switch* and *git checkout* to set up new branches so that [git-pull\[1\]][181] will appropriately merge from the starting point branch. Note that even if this option is not set, this behavior can be chosen per-branch using the `--track` and `--no-track` options. The valid settings are: `false` — no automatic setup is done; `true` — automatic setup is done when the starting point is a remote-tracking branch; `always` — automatic setup is done when the starting point is either a local branch or remote-tracking branch. This option defaults to true.

[][182]branch.autoSetupRebase

When a new branch is created with *git branch*, *git switch* or *git checkout* that tracks another branch, this variable tells Git to set up pull to rebase instead of merge (see "branch.<name>.rebase"). When `never`, rebase is never automatically set to true. When `local`, rebase is set to true for tracked branches of other local branches. When `remote`, rebase is set to true for tracked branches of remote-tracking branches. When `always`, rebase will be set to true for all tracking branches. See "branch.autoSetupMerge" for details on how to set up a branch to track another branch. This option defaults to never.

[][183]branch.sort

This variable controls the sort ordering of branches when displayed by [git-branch\[1\]][184]. Without the "--sort=<value>" option provided, the value of this variable will be used as the default. See [git-for-each-ref\[1\]][185] field names for valid values.

[][186]branch.<name>.remote

When on branch <name>, it tells *git fetch* and *git push* which remote to fetch from/push to. The remote to push to may be overridden with `remote.pushDefault` (for all branches). The remote to push to, for the current branch, may be further overridden by `branch.<name>.pushRemote`. If no remote is configured, or if you are not on any branch, it defaults to `origin` for fetching and `remote.pushDefault` for pushing. Additionally, `.` (a period) is the current local repository (a dot-repository), see `branch.<name>.merge`'s final note below.

[][187]branch.<name>.pushRemote

When on branch <name>, it overrides `branch.<name>.remote` for pushing. It also overrides `remote.pushDefault` for pushing from branch <name>. When you pull from one place (e.g. your upstream) and push to another place (e.g. your own publishing repository), you would want to set `remote.pushDefault` to specify the remote to push to for all branches, and use this option to override it for a specific branch.

[][188]branch.<name>.merge

Defines, together with branch.<name>.remote, the upstream branch for the given branch. It tells *git fetch*/*git pull*/*git rebase* which branch to merge and can also affect *git push* (see push.default). When in branch <name>, it tells *git fetch* the default refspec to be marked for merging in FETCH\_HEAD. The value is handled like the remote part of a refspec, and must match a ref which is fetched from the remote given by "branch.<name>.remote". The merge information is used by *git pull* (which at first calls *git fetch*) to lookup the default branch for merging. Without this option, *git pull* defaults to merge the first refspec fetched. Specify multiple values to get an octopus merge. If you wish to setup *git pull* so that it merges into <name> from another branch in the local repository, you can point branch.<name>.merge to the desired branch, and use the relative path setting `.` (a period) for branch.<name>.remote.

[][189]branch.<name>.mergeOptions

Sets default options for merging into branch <name>. The syntax and supported options are the same as those of [git-merge\[1\]][190], but option values containing whitespace characters are currently not supported.

[][191]branch.<name>.rebase

When true, rebase the branch <name> on top of the fetched branch, instead of merging the default branch from the default remote when "git pull" is run. See "pull.rebase" for doing this in a non branch-specific manner.

When `merges` (or just *m*), pass the `--rebase-merges` option to *git rebase* so that the local merge commits are included in the rebase (see [git-rebase\[1\]][192] for details).

When the value is `interactive` (or just *i*), the rebase is run in interactive mode.

__NOTE__: this is a possibly dangerous operation; do __not__ use it unless you understand the implications (see [git-rebase\[1\]][193] for details).

[][194]branch.<name>.description

Branch description, can be edited with `git branch --edit-description`. Branch description is automatically added in the format-patch cover letter or request-pull summary.

[][195]browser.<tool>.cmd

Specify the command to invoke the specified browser. The specified command is evaluated in shell with the URLs passed as arguments. (See [git-web--browse\[1\]][196].)

[][197]browser.<tool>.path

Override the path for the given tool that may be used to browse HTML help (see `-w` option in [git-help\[1\]][198]) or a working repository in gitweb (see [git-instaweb\[1\]][199]).

[][200]checkout.defaultRemote

When you run `git checkout <something>` or `git switch <something>` and only have one remote, it may implicitly fall back on checking out and tracking e.g. `origin/<something>`. This stops working as soon as you have more than one remote with a `<something>` reference. This setting allows for setting the name of a preferred remote that should always win when it comes to disambiguation. The typical use-case is to set this to `origin`.

Currently this is used by [git-switch\[1\]][201] and [git-checkout\[1\]][202] when `git checkout <something>` or `git switch <something>` will checkout the `<something>` branch on another remote, and by [git-worktree\[1\]][203] when `git worktree add` refers to a remote branch. This setting might be used for other checkout-like commands or functionality in the future.

[][204]checkout.guess

Provides the default value for the `--guess` or `--no-guess` option in `git checkout` and `git switch`. See [git-switch\[1\]][205] and [git-checkout\[1\]][206].

[][207]checkout.workers

The number of parallel workers to use when updating the working tree. The default is one, i.e. sequential execution. If set to a value less than one, Git will use as many workers as the number of logical cores available. This setting and `checkout.thresholdForParallelism` affect all commands that perform checkout. E.g. checkout, clone, reset, sparse-checkout, etc.

Note: parallel checkout usually delivers better performance for repositories located on SSDs or over NFS. For repositories on spinning disks and/or machines with a small number of cores, the default sequential checkout often performs better. The size and compression level of a repository might also influence how well the parallel version performs.

[][208]checkout.thresholdForParallelism

When running parallel checkout with a small number of files, the cost of subprocess spawning and inter-process communication might outweigh the parallelization gains. This setting allows to define the minimum number of files for which parallel checkout should be attempted. The default is 100.

[][209]clean.requireForce

A boolean to make git-clean do nothing unless given -f, -i or -n. Defaults to true.

[][210]clone.defaultRemoteName

The name of the remote to create when cloning a repository. Defaults to `origin`, and can be overridden by passing the `--origin` command-line option to [git-clone\[1\]][211].

[][212]clone.rejectShallow

Reject to clone a repository if it is a shallow one, can be overridden by passing option `--reject-shallow` in command line. See [git-clone\[1\]][213]

[][214]color.advice

A boolean to enable/disable color in hints (e.g. when a push failed, see `advice.*` for a list). May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the error output goes to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][215]color.advice.hint

Use customized color for hints.

[][216]color.blame.highlightRecent

Specify the line annotation color for `git blame --color-by-age` depending upon the age of the line.

This setting should be set to a comma-separated list of color and date settings, starting and ending with a color, the dates should be set from oldest to newest. The metadata will be colored with the specified colors if the line was introduced before the given timestamp, overwriting older timestamped colors.

Instead of an absolute timestamp relative timestamps work as well, e.g. `2.weeks.ago` is valid to address anything older than 2 weeks.

It defaults to `blue,12 month ago,white,1 month ago,red`, which colors everything older than one year blue, recent changes between one month and one year old are kept white, and lines introduced within the last month are colored red.

[][217]color.blame.repeatedLines

Use the specified color to colorize line annotations for `git blame --color-lines`, if they come from the same commit as the preceding line. Defaults to cyan.

[][218]color.branch

A boolean to enable/disable color in the output of [git-branch\[1\]][219]. May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the output is to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][220]color.branch.<slot>

Use customized color for branch coloration. `<slot>` is one of `current` (the current branch), `local` (a local branch), `remote` (a remote-tracking branch in refs/remotes/), `upstream` (upstream tracking branch), `plain` (other refs).

[][221]color.diff

Whether to use ANSI escape sequences to add color to patches. If this is set to `always`, [git-diff\[1\]][222], [git-log\[1\]][223], and [git-show\[1\]][224] will use color for all patches. If it is set to `true` or `auto`, those commands will only use color when output is to the terminal. If unset, then the value of `color.ui` is used (`auto` by default).

This does not affect [git-format-patch\[1\]][225] or the *git-diff-\** plumbing commands. Can be overridden on the command line with the `--color[=<when>]` option.

[][226]color.diff.<slot>

Use customized color for diff colorization. `<slot>` specifies which part of the patch to use the specified color, and is one of `context` (context text - `plain` is a historical synonym), `meta` (metainformation), `frag` (hunk header), *func* (function in hunk header), `old` (removed lines), `new` (added lines), `commit` (commit headers), `whitespace` (highlighting whitespace errors), `oldMoved` (deleted lines), `newMoved` (added lines), `oldMovedDimmed`, `oldMovedAlternative`, `oldMovedAlternativeDimmed`, `newMovedDimmed`, `newMovedAlternative` `newMovedAlternativeDimmed` (See the *<mode>* setting of *\--color-moved* in [git-diff\[1\]][227] for details), `contextDimmed`, `oldDimmed`, `newDimmed`, `contextBold`, `oldBold`, and `newBold` (see [git-range-diff\[1\]][228] for details).

[][229]color.decorate.<slot>

Use customized color for *git log --decorate* output. `<slot>` is one of `branch`, `remoteBranch`, `tag`, `stash` or `HEAD` for local branches, remote-tracking branches, tags, stash and HEAD, respectively and `grafted` for grafted commits.

[][230]color.grep

When set to `always`, always highlight matches. When `false` (or `never`), never. When set to `true` or `auto`, use color only when the output is written to the terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][231]color.grep.<slot>

Use customized color for grep colorization. `<slot>` specifies which part of the line to use the specified color, and is one of

[][232]`context`

non-matching text in context lines (when using `-A`, `-B`, or `-C`)

[][233]`filename`

filename prefix (when not using `-h`)

[][234]`function`

function name lines (when using `-p`)

[][235]`lineNumber`

line number prefix (when using `-n`)

[][236]`column`

column number prefix (when using `--column`)

[][237]`match`

matching text (same as setting `matchContext` and `matchSelected`)

[][238]`matchContext`

matching text in context lines

[][239]`matchSelected`

matching text in selected lines. Also, used to customize the following [git-log\[1\]][240] subcommands: `--grep`, `--author` and `--committer`.

[][241]`selected`

non-matching text in selected lines. Also, used to customize the following [git-log\[1\]][242] subcommands: `--grep`, `--author` and `--committer`.

[][243]`separator`

separators between fields on a line (`:`, `-`, and `=`) and between hunks (`--`)

[][244]color.interactive

When set to `always`, always use colors for interactive prompts and displays (such as those used by "git-add --interactive" and "git-clean --interactive"). When false (or `never`), never. When set to `true` or `auto`, use colors only when the output is to the terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][245]color.interactive.<slot>

Use customized color for *git add --interactive* and *git clean --interactive* output. `<slot>` may be `prompt`, `header`, `help` or `error`, for four distinct types of normal output from interactive commands.

A boolean to specify whether `auto` color modes should colorize output going to the pager. Defaults to true; set this to false if your pager does not understand ANSI color codes.

[][246]color.push

A boolean to enable/disable color in push errors. May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the error output goes to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][247]color.push.error

Use customized color for push errors.

[][248]color.remote

If set, keywords at the start of the line are highlighted. The keywords are "error", "warning", "hint" and "success", and are matched case-insensitively. May be set to `always`, `false` (or `never`) or `auto` (or `true`). If unset, then the value of `color.ui` is used (`auto` by default).

[][249]color.remote.<slot>

Use customized color for each remote keyword. `<slot>` may be `hint`, `warning`, `success` or `error` which match the corresponding keyword.

[][250]color.showBranch

A boolean to enable/disable color in the output of [git-show-branch\[1\]][251]. May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the output is to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][252]color.status

A boolean to enable/disable color in the output of [git-status\[1\]][253]. May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the output is to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][254]color.status.<slot>

Use customized color for status colorization. `<slot>` is one of `header` (the header text of the status message), `added` or `updated` (files which are added but not committed), `changed` (files which are changed but not added in the index), `untracked` (files which are not tracked by Git), `branch` (the current branch), `nobranch` (the color the *no branch* warning is shown in, defaulting to red), `localBranch` or `remoteBranch` (the local and remote branch names, respectively, when branch and tracking information is displayed in the status short-format), or `unmerged` (files which have unmerged changes).

[][255]color.transport

A boolean to enable/disable color when pushes are rejected. May be set to `always`, `false` (or `never`) or `auto` (or `true`), in which case colors are used only when the error output goes to a terminal. If unset, then the value of `color.ui` is used (`auto` by default).

[][256]color.transport.rejected

Use customized color when a push was rejected.

[][257]color.ui

This variable determines the default value for variables such as `color.diff` and `color.grep` that control the use of color per command family. Its scope will expand as more commands learn configuration to set a default for the `--color` option. Set it to `false` or `never` if you prefer Git commands not to use color unless enabled explicitly with some other configuration or the `--color` option. Set it to `always` if you want all output not intended for machine consumption to use color, to `true` or `auto` (this is the default since Git 1.8.4) if you want such output to use color when written to the terminal.

[][258]column.ui

Specify whether supported commands should output in columns. This variable consists of a list of tokens separated by spaces or commas:

These options control when the feature should be enabled (defaults to *never*):

[][259]`always`

always show in columns

[][260]`never`

never show in columns

[][261]`auto`

show in columns if the output is to the terminal

These options control layout (defaults to *column*). Setting any of these implies *always* if none of *always*, *never*, or *auto* are specified.

[][262]`column`

fill columns before rows

[][263]`row`

fill rows before columns

[][264]`plain`

show in one column

Finally, these options can be combined with a layout option (defaults to *nodense*):

[][265]`dense`

make unequal size columns to utilize more space

[][266]`nodense`

make equal size columns

[][267]column.branch

Specify whether to output branch listing in `git branch` in columns. See `column.ui` for details.

[][268]column.clean

Specify the layout when list items in `git clean -i`, which always shows files and directories in columns. See `column.ui` for details.

[][269]column.status

Specify whether to output untracked files in `git status` in columns. See `column.ui` for details.

[][270]column.tag

Specify whether to output tag listing in `git tag` in columns. See `column.ui` for details.

[][271]commit.cleanup

This setting overrides the default of the `--cleanup` option in `git commit`. See [git-commit\[1\]][272] for details. Changing the default can be useful when you always want to keep lines that begin with comment character `#` in your log message, in which case you would do `git config commit.cleanup whitespace` (note that you will have to remove the help lines that begin with `#` in the commit log template yourself, if you do this).

[][273]commit.gpgSign

A boolean to specify whether all commits should be GPG signed. Use of this option when doing operations such as rebase can result in a large number of commits being signed. It may be convenient to use an agent to avoid typing your GPG passphrase several times.

[][274]commit.status

A boolean to enable/disable inclusion of status information in the commit message template when using an editor to prepare the commit message. Defaults to true.

[][275]commit.template

Specify the pathname of a file to use as the template for new commit messages.

[][276]commit.verbose

A boolean or int to specify the level of verbose with `git commit`. See [git-commit\[1\]][277].

[][278]commitGraph.generationVersion

Specifies the type of generation number version to use when writing or reading the commit-graph file. If version 1 is specified, then the corrected commit dates will not be written or read. Defaults to 2.

[][279]commitGraph.maxNewFilters

Specifies the default value for the `--max-new-filters` option of `git commit-graph write` (c.f., [git-commit-graph\[1\]][280]).

[][281]commitGraph.readChangedPaths

If true, then git will use the changed-path Bloom filters in the commit-graph file (if it exists, and they are present). Defaults to true. See [git-commit-graph\[1\]][282] for more information.

[][283]credential.helper

Specify an external helper to be called when a username or password credential is needed; the helper may consult external storage to avoid prompting the user for the credentials. This is normally the name of a credential helper with possible arguments, but may also be an absolute path with arguments or, if preceded by `!`, shell commands.

Note that multiple helpers may be defined. See [gitcredentials\[7\]][284] for details and examples.

[][285]credential.useHttpPath

When acquiring credentials, consider the "path" component of an http or https URL to be important. Defaults to false. See [gitcredentials\[7\]][286] for more information.

[][287]credential.username

If no username is set for a network authentication, use this username by default. See credential.<context>.\* below, and [gitcredentials\[7\]][288].

[][289]credential.<url>.\*

Any of the credential.\* options above can be applied selectively to some credentials. For example "credential.https://example.com.username" would set the default username only for https connections to example.com. See [gitcredentials\[7\]][290] for details on how URLs are matched.

[][291]credentialCache.ignoreSIGHUP

Tell git-credential-cache—daemon to ignore SIGHUP, instead of quitting.

[][292]credentialStore.lockTimeoutMS

The length of time, in milliseconds, for git-credential-store to retry when trying to lock the credentials file. Value 0 means not to retry at all; -1 means to try indefinitely. Default is 1000 (i.e., retry for 1s).

[][293]completion.commands

This is only used by git-completion.bash to add or remove commands from the list of completed commands. Normally only porcelain commands and a few select others are completed. You can add more commands, separated by space, in this variable. Prefixing the command with *\-* will remove it from the existing list.

[][294]diff.autoRefreshIndex

When using *git diff* to compare with work tree files, do not consider stat-only change as changed. Instead, silently run `git update-index --refresh` to update the cached stat information for paths whose contents in the work tree match the contents in the index. This option defaults to true. Note that this affects only *git diff* Porcelain, and not lower level *diff* commands such as *git diff-files*.

[][295]diff.dirstat

A comma separated list of `--dirstat` parameters specifying the default behavior of the `--dirstat` option to [git-diff\[1\]][296] and friends. The defaults can be overridden on the command line (using `--dirstat=<param1,param2,...>`). The fallback defaults (when not changed by `diff.dirstat`) are `changes,noncumulative,3`. The following parameters are available:

[][297]`changes`

Compute the dirstat numbers by counting the lines that have been removed from the source, or added to the destination. This ignores the amount of pure code movements within a file. In other words, rearranging lines in a file is not counted as much as other changes. This is the default behavior when no parameter is given.

[][298]`lines`

Compute the dirstat numbers by doing the regular line-based diff analysis, and summing the removed/added line counts. (For binary files, count 64-byte chunks instead, since binary files have no natural concept of lines). This is a more expensive `--dirstat` behavior than the `changes` behavior, but it does count rearranged lines within a file as much as other changes. The resulting output is consistent with what you get from the other `--*stat` options.

[][299]`files`

Compute the dirstat numbers by counting the number of files changed. Each changed file counts equally in the dirstat analysis. This is the computationally cheapest `--dirstat` behavior, since it does not have to look at the file contents at all.

[][300]`cumulative`

Count changes in a child directory for the parent directory as well. Note that when using `cumulative`, the sum of the percentages reported may exceed 100%. The default (non-cumulative) behavior can be specified with the `noncumulative` parameter.

[][301]<limit>

An integer parameter specifies a cut-off percent (3% by default). Directories contributing less than this percentage of the changes are not shown in the output.

Example: The following will count changed files, while ignoring directories with less than 10% of the total amount of changed files, and accumulating child directory counts in the parent directories: `files,10,cumulative`.

[][302]diff.statGraphWidth

Limit the width of the graph part in --stat output. If set, applies to all commands generating --stat output except format-patch.

[][303]diff.context

Generate diffs with <n> lines of context instead of the default of 3. This value is overridden by the -U option.

[][304]diff.interHunkContext

Show the context between diff hunks, up to the specified number of lines, thereby fusing the hunks that are close to each other. This value serves as the default for the `--inter-hunk-context` command line option.

[][305]diff.external

If this config variable is set, diff generation is not performed using the internal diff machinery, but using the given command. Can be overridden with the ‘GIT\_EXTERNAL\_DIFF’ environment variable. The command is called with parameters as described under "git Diffs" in [git\[1\]][306]. Note: if you want to use an external diff program only on a subset of your files, you might want to use [gitattributes\[5\]][307] instead.

[][308]diff.ignoreSubmodules

Sets the default value of --ignore-submodules. Note that this affects only *git diff* Porcelain, and not lower level *diff* commands such as *git diff-files*. *git checkout* and *git switch* also honor this setting when reporting uncommitted changes. Setting it to *all* disables the submodule summary normally shown by *git commit* and *git status* when `status.submoduleSummary` is set unless it is overridden by using the --ignore-submodules command-line option. The *git submodule* commands are not affected by this setting. By default this is set to untracked so that any untracked submodules are ignored.

[][309]diff.mnemonicPrefix

If set, *git diff* uses a prefix pair that is different from the standard "a/" and "b/" depending on what is being compared. When this configuration is in effect, reverse diff output also swaps the order of the prefixes:

[][310]`git diff`

compares the (i)ndex and the (w)ork tree;

[][311]`git diff HEAD`

compares a (c)ommit and the (w)ork tree;

[][312]`git diff --cached`

compares a (c)ommit and the (i)ndex;

[][313]`git diff HEAD:file1 file2`

compares an (o)bject and a (w)ork tree entity;

[][314]`git diff --no-index a b`

compares two non-git things (1) and (2).

[][315]diff.noprefix

If set, *git diff* does not show any source or destination prefix.

[][316]diff.relative

If set to *true*, *git diff* does not show changes outside of the directory and show pathnames relative to the current directory.

[][317]diff.orderFile

File indicating how to order files within a diff. See the *\-O* option to [git-diff\[1\]][318] for details. If `diff.orderFile` is a relative pathname, it is treated as relative to the top of the working tree.

[][319]diff.renameLimit

The number of files to consider in the exhaustive portion of copy/rename detection; equivalent to the *git diff* option `-l`. If not set, the default value is currently 1000. This setting has no effect if rename detection is turned off.

[][320]diff.renames

Whether and how Git detects renames. If set to "false", rename detection is disabled. If set to "true", basic rename detection is enabled. If set to "copies" or "copy", Git will detect copies, as well. Defaults to true. Note that this affects only *git diff* Porcelain like [git-diff\[1\]][321] and [git-log\[1\]][322], and not lower level commands such as [git-diff-files\[1\]][323].

[][324]diff.suppressBlankEmpty

A boolean to inhibit the standard behavior of printing a space before each empty output line. Defaults to false.

[][325]diff.submodule

Specify the format in which differences in submodules are shown. The "short" format just shows the names of the commits at the beginning and end of the range. The "log" format lists the commits in the range like [git-submodule\[1\]][326] `summary` does. The "diff" format shows an inline diff of the changed contents of the submodule. Defaults to "short".

[][327]diff.wordRegex

A POSIX Extended Regular Expression used to determine what is a "word" when performing word-by-word difference calculations. Character sequences that match the regular expression are "words", all other characters are __ignorable__ whitespace.

[][328]diff.<driver>.command

The custom diff driver command. See [gitattributes\[5\]][329] for details.

[][330]diff.<driver>.xfuncname

The regular expression that the diff driver should use to recognize the hunk header. A built-in pattern may also be used. See [gitattributes\[5\]][331] for details.

[][332]diff.<driver>.binary

Set this option to true to make the diff driver treat files as binary. See [gitattributes\[5\]][333] for details.

[][334]diff.<driver>.textconv

The command that the diff driver should call to generate the text-converted version of a file. The result of the conversion is used to generate a human-readable diff. See [gitattributes\[5\]][335] for details.

[][336]diff.<driver>.wordRegex

The regular expression that the diff driver should use to split words in a line. See [gitattributes\[5\]][337] for details.

[][338]diff.<driver>.cachetextconv

Set this option to true to make the diff driver cache the text conversion outputs. See [gitattributes\[5\]][339] for details.

[][340]diff.tool

Controls which diff tool is used by [git-difftool\[1\]][341]. This variable overrides the value configured in `merge.tool`. The list below shows the valid built-in values. Any other value is treated as a custom diff tool and requires that a corresponding difftool.<tool>.cmd variable is defined.

[][342]diff.guitool

Controls which diff tool is used by [git-difftool\[1\]][343] when the -g/--gui flag is specified. This variable overrides the value configured in `merge.guitool`. The list below shows the valid built-in values. Any other value is treated as a custom diff tool and requires that a corresponding difftool.<guitool>.cmd variable is defined.

-   araxis
    
-   bc
    
-   codecompare
    
-   deltawalker
    
-   diffmerge
    
-   diffuse
    
-   ecmerge
    
-   emerge
    
-   examdiff
    
-   guiffy
    
-   gvimdiff
    
-   kdiff3
    
-   kompare
    
-   meld
    
-   nvimdiff
    
-   opendiff
    
-   p4merge
    
-   smerge
    
-   tkdiff
    
-   vimdiff
    
-   winmerge
    
-   xxdiff
    

[][344]diff.indentHeuristic

Set this option to `false` to disable the default heuristics that shift diff hunk boundaries to make patches easier to read.

[][345]diff.algorithm

Choose a diff algorithm. The variants are as follows:

[][346]`default`, `myers`

The basic greedy diff algorithm. Currently, this is the default.

[][347]`minimal`

Spend extra time to make sure the smallest possible diff is produced.

[][348]`patience`

Use "patience diff" algorithm when generating patches.

[][349]`histogram`

This algorithm extends the patience algorithm to "support low-occurrence common elements".

[][350]diff.wsErrorHighlight

Highlight whitespace errors in the `context`, `old` or `new` lines of the diff. Multiple values are separated by comma, `none` resets previous values, `default` reset the list to `new` and `all` is a shorthand for `old,new,context`. The whitespace errors are colored with `color.diff.whitespace`. The command line option `--ws-error-highlight=<kind>` overrides this setting.

[][351]diff.colorMoved

If set to either a valid `<mode>` or a true value, moved lines in a diff are colored differently, for details of valid modes see *\--color-moved* in [git-diff\[1\]][352]. If simply set to true the default color mode will be used. When set to false, moved lines are not colored.

[][353]diff.colorMovedWS

When moved lines are colored using e.g. the `diff.colorMoved` setting, this option controls the `<mode>` how spaces are treated for details of valid modes see *\--color-moved-ws* in [git-diff\[1\]][354].

[][355]difftool.<tool>.path

Override the path for the given tool. This is useful in case your tool is not in the PATH.

[][356]difftool.<tool>.cmd

Specify the command to invoke the specified diff tool. The specified command is evaluated in shell with the following variables available: *LOCAL* is set to the name of the temporary file containing the contents of the diff pre-image and *REMOTE* is set to the name of the temporary file containing the contents of the diff post-image.

[][357]difftool.prompt

Prompt before each invocation of the diff tool.

[][358]extensions.objectFormat

Specify the hash algorithm to use. The acceptable values are `sha1` and `sha256`. If not specified, `sha1` is assumed. It is an error to specify this key unless `core.repositoryFormatVersion` is 1.

Note that this setting should only be set by [git-init\[1\]][359] or [git-clone\[1\]][360]. Trying to change it after initialization will not work and will produce hard-to-diagnose issues.

[][361]fastimport.unpackLimit

If the number of objects imported by [git-fast-import\[1\]][362] is below this limit, then the objects will be unpacked into loose object files. However if the number of imported objects equals or exceeds this limit then the pack will be stored as a pack. Storing the pack from a fast-import can make the import operation complete faster, especially on slow filesystems. If not set, the value of `transfer.unpackLimit` is used instead.

[][363]feature.\*

The config settings that start with `feature.` modify the defaults of a group of other config settings. These groups are created by the Git developer community as recommended defaults and are subject to change. In particular, new config options may be added with different defaults.

[][364]feature.experimental

Enable config options that are new to Git, and are being considered for future defaults. Config settings included here may be added or removed with each release, including minor version updates. These settings may have unintended interactions since they are so new. Please enable this setting if you are interested in providing feedback on experimental features. The new default values are:

-   `fetch.negotiationAlgorithm=skipping` may improve fetch negotiation times by skipping more commits at a time, reducing the number of round trips.
    

[][365]feature.manyFiles

Enable config options that optimize for repos with many files in the working directory. With many files, commands such as `git status` and `git checkout` may be slow and these new defaults improve performance:

-   `index.version=4` enables path-prefix compression in the index.
    
-   `core.untrackedCache=true` enables the untracked cache. This setting assumes that mtime is working on your machine.
    

[][366]fetch.recurseSubmodules

This option controls whether `git fetch` (and the underlying fetch in `git pull`) will recursively fetch into populated submodules. This option can be set either to a boolean value or to *on-demand*. Setting it to a boolean changes the behavior of fetch and pull to recurse unconditionally into submodules when set to true or to not recurse at all when set to false. When set to *on-demand*, fetch and pull will only recurse into a populated submodule when its superproject retrieves a commit that updates the submodule’s reference. Defaults to *on-demand*, or to the value of *submodule.recurse* if set.

[][367]fetch.fsckObjects

If it is set to true, git-fetch-pack will check all fetched objects. See `transfer.fsckObjects` for what’s checked. Defaults to false. If not set, the value of `transfer.fsckObjects` is used instead.

[][368]fetch.fsck.<msg-id>

Acts like `fsck.<msg-id>`, but is used by [git-fetch-pack\[1\]][369] instead of [git-fsck\[1\]][370]. See the `fsck.<msg-id>` documentation for details.

[][371]fetch.fsck.skipList

Acts like `fsck.skipList`, but is used by [git-fetch-pack\[1\]][372] instead of [git-fsck\[1\]][373]. See the `fsck.skipList` documentation for details.

[][374]fetch.unpackLimit

If the number of objects fetched over the Git native transfer is below this limit, then the objects will be unpacked into loose object files. However if the number of received objects equals or exceeds this limit then the received pack will be stored as a pack, after adding any missing delta bases. Storing the pack from a push can make the push operation complete faster, especially on slow filesystems. If not set, the value of `transfer.unpackLimit` is used instead.

[][375]fetch.prune

If true, fetch will automatically behave as if the `--prune` option was given on the command line. See also `remote.<name>.prune` and the PRUNING section of [git-fetch\[1\]][376].

[][377]fetch.pruneTags

If true, fetch will automatically behave as if the `refs/tags/*:refs/tags/*` refspec was provided when pruning, if not set already. This allows for setting both this option and `fetch.prune` to maintain a 1=1 mapping to upstream refs. See also `remote.<name>.pruneTags` and the PRUNING section of [git-fetch\[1\]][378].

[][379]fetch.output

Control how ref update status is printed. Valid values are `full` and `compact`. Default value is `full`. See section OUTPUT in [git-fetch\[1\]][380] for detail.

[][381]fetch.negotiationAlgorithm

Control how information about the commits in the local repository is sent when negotiating the contents of the packfile to be sent by the server. Set to "skipping" to use an algorithm that skips commits in an effort to converge faster, but may result in a larger-than-necessary packfile; or set to "noop" to not send any information at all, which will almost certainly result in a larger-than-necessary packfile, but will skip the negotiation step. The default is "default" which instructs Git to use the default algorithm that never skips commits (unless the server has acknowledged it or one of its descendants). If `feature.experimental` is enabled, then this setting defaults to "skipping". Unknown values will cause *git fetch* to error out.

See also the `--negotiate-only` and `--negotiation-tip` options to [git-fetch\[1\]][382].

[][383]fetch.showForcedUpdates

Set to false to enable `--no-show-forced-updates` in [git-fetch\[1\]][384] and [git-pull\[1\]][385] commands. Defaults to true.

[][386]fetch.parallel

Specifies the maximal number of fetch operations to be run in parallel at a time (submodules, or remotes when the `--multiple` option of [git-fetch\[1\]][387] is in effect).

A value of 0 will give some reasonable default. If unset, it defaults to 1.

For submodules, this setting can be overridden using the `submodule.fetchJobs` config setting.

[][388]fetch.writeCommitGraph

Set to true to write a commit-graph after every `git fetch` command that downloads a pack-file from a remote. Using the `--split` option, most executions will create a very small commit-graph file on top of the existing commit-graph file(s). Occasionally, these files will merge and the write may take longer. Having an updated commit-graph file helps performance of many Git commands, including `git merge-base`, `git push -f`, and `git log --graph`. Defaults to false.

[][389]format.attach

Enable multipart/mixed attachments as the default for *format-patch*. The value can also be a double quoted string which will enable attachments as the default and set the value as the boundary. See the --attach option in [git-format-patch\[1\]][390].

[][391]format.from

Provides the default value for the `--from` option to format-patch. Accepts a boolean value, or a name and email address. If false, format-patch defaults to `--no-from`, using commit authors directly in the "From:" field of patch mails. If true, format-patch defaults to `--from`, using your committer identity in the "From:" field of patch mails and including a "From:" field in the body of the patch mail if different. If set to a non-boolean value, format-patch uses that value instead of your committer identity. Defaults to false.

[][392]format.numbered

A boolean which can enable or disable sequence numbers in patch subjects. It defaults to "auto" which enables it only if there is more than one patch. It can be enabled or disabled for all messages by setting it to "true" or "false". See --numbered option in [git-format-patch\[1\]][393].

Additional email headers to include in a patch to be submitted by mail. See [git-format-patch\[1\]][394].

[][395]format.to

[][396]format.cc

Additional recipients to include in a patch to be submitted by mail. See the --to and --cc options in [git-format-patch\[1\]][397].

[][398]format.subjectPrefix

The default for format-patch is to output files with the *\[PATCH\]* subject prefix. Use this variable to change that prefix.

[][399]format.coverFromDescription

The default mode for format-patch to determine which parts of the cover letter will be populated using the branch’s description. See the `--cover-from-description` option in [git-format-patch\[1\]][400].

[][401]format.signature

The default for format-patch is to output a signature containing the Git version number. Use this variable to change that default. Set this variable to the empty string ("") to suppress signature generation.

[][402]format.signatureFile

Works just like format.signature except the contents of the file specified by this variable will be used as the signature.

[][403]format.suffix

The default for format-patch is to output files with the suffix `.patch`. Use this variable to change that suffix (make sure to include the dot if you want it).

Encode email headers that have non-ASCII characters with "Q-encoding" (described in RFC 2047) for email transmission. Defaults to true.

[][404]format.pretty

The default pretty format for log/show/whatchanged command, See [git-log\[1\]][405], [git-show\[1\]][406], [git-whatchanged\[1\]][407].

[][408]format.thread

The default threading style for *git format-patch*. Can be a boolean value, or `shallow` or `deep`. `shallow` threading makes every mail a reply to the head of the series, where the head is chosen from the cover letter, the `--in-reply-to`, and the first patch mail, in this order. `deep` threading makes every mail a reply to the previous one. A true boolean value is the same as `shallow`, and a false value disables threading.

[][409]format.signOff

A boolean value which lets you enable the `-s/--signoff` option of format-patch by default. __Note:__ Adding the `Signed-off-by` trailer to a patch should be a conscious act and means that you certify you have the rights to submit this work under the same open source license. Please see the *SubmittingPatches* document for further discussion.

[][410]format.coverLetter

A boolean that controls whether to generate a cover-letter when format-patch is invoked, but in addition can be set to "auto", to generate a cover-letter only when there’s more than one patch. Default is false.

[][411]format.outputDirectory

Set a custom directory to store the resulting files instead of the current working directory. All directory components will be created.

[][412]format.filenameMaxLength

The maximum length of the output filenames generated by the `format-patch` command; defaults to 64. Can be overridden by the `--filename-max-length=<n>` command line option.

[][413]format.useAutoBase

A boolean value which lets you enable the `--base=auto` option of format-patch by default. Can also be set to "whenAble" to allow enabling `--base=auto` if a suitable base is available, but to skip adding base info otherwise without the format dying.

[][414]format.notes

Provides the default value for the `--notes` option to format-patch. Accepts a boolean value, or a ref which specifies where to get notes. If false, format-patch defaults to `--no-notes`. If true, format-patch defaults to `--notes`. If set to a non-boolean value, format-patch defaults to `--notes=<ref>`, where `ref` is the non-boolean value. Defaults to false.

If one wishes to use the ref `ref/notes/true`, please use that literal instead.

This configuration can be specified multiple times in order to allow multiple notes refs to be included. In that case, it will behave similarly to multiple `--[no-]notes[=]` options passed in. That is, a value of `true` will show the default notes, a value of `<ref>` will also show notes from that notes ref and a value of `false` will negate previous configurations and not show notes.

For example,

\[format\]
notes = true
notes = foo
notes = false
notes = bar

will only show notes from `refs/notes/bar`.

[][415]filter.<driver>.clean

The command which is used to convert the content of a worktree file to a blob upon checkin. See [gitattributes\[5\]][416] for details.

[][417]filter.<driver>.smudge

The command which is used to convert the content of a blob object to a worktree file upon checkout. See [gitattributes\[5\]][418] for details.

[][419]fsck.<msg-id>

During fsck git may find issues with legacy data which wouldn’t be generated by current versions of git, and which wouldn’t be sent over the wire if `transfer.fsckObjects` was set. This feature is intended to support working with legacy repositories containing such data.

Setting `fsck.<msg-id>` will be picked up by [git-fsck\[1\]][420], but to accept pushes of such data set `receive.fsck.<msg-id>` instead, or to clone or fetch it set `fetch.fsck.<msg-id>`.

The rest of the documentation discusses `fsck.*` for brevity, but the same applies for the corresponding `receive.fsck.*` and `fetch.<msg-id>.*`. variables.

Unlike variables like `color.ui` and `core.editor` the `receive.fsck.<msg-id>` and `fetch.fsck.<msg-id>` variables will not fall back on the `fsck.<msg-id>` configuration if they aren’t set. To uniformly configure the same fsck settings in different circumstances all three of them they must all set to the same values.

When `fsck.<msg-id>` is set, errors can be switched to warnings and vice versa by configuring the `fsck.<msg-id>` setting where the `<msg-id>` is the fsck message ID and the value is one of `error`, `warn` or `ignore`. For convenience, fsck prefixes the error/warning with the message ID, e.g. "missingEmail: invalid author/committer line - missing email" means that setting `fsck.missingEmail = ignore` will hide that issue.

In general, it is better to enumerate existing objects with problems with `fsck.skipList`, instead of listing the kind of breakages these problematic objects share to be ignored, as doing the latter will allow new instances of the same breakages go unnoticed.

Setting an unknown `fsck.<msg-id>` value will cause fsck to die, but doing the same for `receive.fsck.<msg-id>` and `fetch.fsck.<msg-id>` will only cause git to warn.

[][421]fsck.skipList

The path to a list of object names (i.e. one unabbreviated SHA-1 per line) that are known to be broken in a non-fatal way and should be ignored. On versions of Git 2.20 and later comments (*#*), empty lines, and any leading and trailing whitespace is ignored. Everything but a SHA-1 per line will error out on older versions.

This feature is useful when an established project should be accepted despite early commits containing errors that can be safely ignored such as invalid committer email addresses. Note: corrupt objects cannot be skipped with this setting.

Like `fsck.<msg-id>` this variable has corresponding `receive.fsck.skipList` and `fetch.fsck.skipList` variants.

Unlike variables like `color.ui` and `core.editor` the `receive.fsck.skipList` and `fetch.fsck.skipList` variables will not fall back on the `fsck.skipList` configuration if they aren’t set. To uniformly configure the same fsck settings in different circumstances all three of them they must all set to the same values.

Older versions of Git (before 2.20) documented that the object names list should be sorted. This was never a requirement, the object names could appear in any order, but when reading the list we tracked whether the list was sorted for the purposes of an internal binary search implementation, which could save itself some work with an already sorted list. Unless you had a humongous list there was no reason to go out of your way to pre-sort the list. After Git version 2.20 a hash implementation is used instead, so there’s now no reason to pre-sort the list.

[][422]gc.aggressiveDepth

The depth parameter used in the delta compression algorithm used by *git gc --aggressive*. This defaults to 50, which is the default for the `--depth` option when `--aggressive` isn’t in use.

See the documentation for the `--depth` option in [git-repack\[1\]][423] for more details.

[][424]gc.aggressiveWindow

The window size parameter used in the delta compression algorithm used by *git gc --aggressive*. This defaults to 250, which is a much more aggressive window size than the default `--window` of 10.

See the documentation for the `--window` option in [git-repack\[1\]][425] for more details.

[][426]gc.auto

When there are approximately more than this many loose objects in the repository, `git gc --auto` will pack them. Some Porcelain commands use this command to perform a light-weight garbage collection from time to time. The default value is 6700.

Setting this to 0 disables not only automatic packing based on the number of loose objects, but any other heuristic `git gc --auto` will otherwise use to determine if there’s work to do, such as `gc.autoPackLimit`.

[][427]gc.autoPackLimit

When there are more than this many packs that are not marked with `*.keep` file in the repository, `git gc --auto` consolidates them into one larger pack. The default value is 50. Setting this to 0 disables it. Setting `gc.auto` to 0 will also disable this.

See the `gc.bigPackThreshold` configuration variable below. When in use, it’ll affect how the auto pack limit works.

[][428]gc.autoDetach

Make `git gc --auto` return immediately and run in background if the system supports it. Default is true.

[][429]gc.bigPackThreshold

If non-zero, all packs larger than this limit are kept when `git gc` is run. This is very similar to `--keep-largest-pack` except that all packs that meet the threshold are kept, not just the largest pack. Defaults to zero. Common unit suffixes of *k*, *m*, or *g* are supported.

Note that if the number of kept packs is more than gc.autoPackLimit, this configuration variable is ignored, all packs except the base pack will be repacked. After this the number of packs should go below gc.autoPackLimit and gc.bigPackThreshold should be respected again.

If the amount of memory estimated for `git repack` to run smoothly is not available and `gc.bigPackThreshold` is not set, the largest pack will also be excluded (this is the equivalent of running `git gc` with `--keep-largest-pack`).

[][430]gc.writeCommitGraph

If true, then gc will rewrite the commit-graph file when [git-gc\[1\]][431] is run. When using `git gc --auto` the commit-graph will be updated if housekeeping is required. Default is true. See [git-commit-graph\[1\]][432] for details.

[][433]gc.logExpiry

If the file gc.log exists, then `git gc --auto` will print its content and exit with status zero instead of running unless that file is more than *gc.logExpiry* old. Default is "1.day". See `gc.pruneExpire` for more ways to specify its value.

[][434]gc.packRefs

Running `git pack-refs` in a repository renders it unclonable by Git versions prior to 1.5.1.2 over dumb transports such as HTTP. This variable determines whether *git gc* runs `git pack-refs`. This can be set to `notbare` to enable it within all non-bare repos or it can be set to a boolean value. The default is `true`.

[][435]gc.pruneExpire

When *git gc* is run, it will call *prune --expire 2.weeks.ago*. Override the grace period with this config variable. The value "now" may be used to disable this grace period and always prune unreachable objects immediately, or "never" may be used to suppress pruning. This feature helps prevent corruption when *git gc* runs concurrently with another process writing to the repository; see the "NOTES" section of [git-gc\[1\]][436].

[][437]gc.worktreePruneExpire

When *git gc* is run, it calls *git worktree prune --expire 3.months.ago*. This config variable can be used to set a different grace period. The value "now" may be used to disable the grace period and prune `$GIT_DIR/worktrees` immediately, or "never" may be used to suppress pruning.

[][438]gc.reflogExpire

[][439]gc.<pattern>.reflogExpire

*git reflog expire* removes reflog entries older than this time; defaults to 90 days. The value "now" expires all entries immediately, and "never" suppresses expiration altogether. With "<pattern>" (e.g. "refs/stash") in the middle the setting applies only to the refs that match the <pattern>.

[][440]gc.reflogExpireUnreachable

[][441]gc.<pattern>.reflogExpireUnreachable

*git reflog expire* removes reflog entries older than this time and are not reachable from the current tip; defaults to 30 days. The value "now" expires all entries immediately, and "never" suppresses expiration altogether. With "<pattern>" (e.g. "refs/stash") in the middle, the setting applies only to the refs that match the <pattern>.

These types of entries are generally created as a result of using `git commit --amend` or `git rebase` and are the commits prior to the amend or rebase occurring. Since these changes are not part of the current project most users will want to expire them sooner, which is why the default is more aggressive than `gc.reflogExpire`.

[][442]gc.rerereResolved

Records of conflicted merge you resolved earlier are kept for this many days when *git rerere gc* is run. You can also use more human-readable "1.month.ago", etc. The default is 60 days. See [git-rerere\[1\]][443].

[][444]gc.rerereUnresolved

Records of conflicted merge you have not resolved are kept for this many days when *git rerere gc* is run. You can also use more human-readable "1.month.ago", etc. The default is 15 days. See [git-rerere\[1\]][445].

[][446]gitcvs.commitMsgAnnotation

Append this string to each commit message. Set to empty string to disable this feature. Defaults to "via git-CVS emulator".

[][447]gitcvs.enabled

Whether the CVS server interface is enabled for this repository. See [git-cvsserver\[1\]][448].

[][449]gitcvs.logFile

Path to a log file where the CVS server interface well… logs various stuff. See [git-cvsserver\[1\]][450].

[][451]gitcvs.usecrlfattr

If true, the server will look up the end-of-line conversion attributes for files to determine the `-k` modes to use. If the attributes force Git to treat a file as text, the `-k` mode will be left blank so CVS clients will treat it as text. If they suppress text conversion, the file will be set with *\-kb* mode, which suppresses any newline munging the client might otherwise do. If the attributes do not allow the file type to be determined, then `gitcvs.allBinary` is used. See [gitattributes\[5\]][452].

[][453]gitcvs.allBinary

This is used if `gitcvs.usecrlfattr` does not resolve the correct *\-kb* mode to use. If true, all unresolved files are sent to the client in mode *\-kb*. This causes the client to treat them as binary files, which suppresses any newline munging it otherwise might do. Alternatively, if it is set to "guess", then the contents of the file are examined to decide if it is binary, similar to `core.autocrlf`.

[][454]gitcvs.dbName

Database used by git-cvsserver to cache revision information derived from the Git repository. The exact meaning depends on the used database driver, for SQLite (which is the default driver) this is a filename. Supports variable substitution (see [git-cvsserver\[1\]][455] for details). May not contain semicolons (`;`). Default: *%Ggitcvs.%m.sqlite*

[][456]gitcvs.dbDriver

Used Perl DBI driver. You can specify any available driver for this here, but it might not work. git-cvsserver is tested with *DBD::SQLite*, reported to work with *DBD::Pg*, and reported __not__ to work with *DBD::mysql*. Experimental feature. May not contain double colons (`:`). Default: *SQLite*. See [git-cvsserver\[1\]][457].

[][458]gitcvs.dbUser, gitcvs.dbPass

Database user and password. Only useful if setting `gitcvs.dbDriver`, since SQLite has no concept of database users and/or passwords. *gitcvs.dbUser* supports variable substitution (see [git-cvsserver\[1\]][459] for details).

[][460]gitcvs.dbTableNamePrefix

Database table name prefix. Prepended to the names of any database tables used, allowing a single database to be used for several repositories. Supports variable substitution (see [git-cvsserver\[1\]][461] for details). Any non-alphabetic characters will be replaced with underscores.

All gitcvs variables except for `gitcvs.usecrlfattr` and `gitcvs.allBinary` can also be specified as *gitcvs.<access\_method>.<varname>* (where *access\_method* is one of "ext" and "pserver") to make them apply only for the given access method.

[][462]gitweb.category

[][463]gitweb.description

[][464]gitweb.owner

[][465]gitweb.url

See [gitweb\[1\]][466] for description.

[][467]gitweb.avatar

[][468]gitweb.blame

[][469]gitweb.grep

[][470]gitweb.highlight

[][471]gitweb.patches

[][472]gitweb.pickaxe

[][473]gitweb.remote\_heads

[][474]gitweb.showSizes

[][475]gitweb.snapshot

See [gitweb.conf\[5\]][476] for description.

[][477]grep.lineNumber

If set to true, enable `-n` option by default.

[][478]grep.column

If set to true, enable the `--column` option by default.

[][479]grep.patternType

Set the default matching behavior. Using a value of *basic*, *extended*, *fixed*, or *perl* will enable the `--basic-regexp`, `--extended-regexp`, `--fixed-strings`, or `--perl-regexp` option accordingly, while the value *default* will return to the default matching behavior.

[][480]grep.extendedRegexp

If set to true, enable `--extended-regexp` option by default. This option is ignored when the `grep.patternType` option is set to a value other than *default*.

[][481]grep.threads

Number of grep worker threads to use. See `grep.threads` in [git-grep\[1\]][482] for more information.

[][483]grep.fallbackToNoIndex

If set to true, fall back to git grep --no-index if git grep is executed outside of a git repository. Defaults to false.

[][484]gpg.program

Use this custom program instead of "`gpg`" found on `$PATH` when making or verifying a PGP signature. The program must support the same command-line interface as GPG, namely, to verify a detached signature, "`gpg --verify $signature - <$file`" is run, and the program is expected to signal a good signature by exiting with code 0, and to generate an ASCII-armored detached signature, the standard input of "`gpg -bsau $key`" is fed with the contents to be signed, and the program is expected to send the result to its standard output.

[][485]gpg.format

Specifies which key format to use when signing with `--gpg-sign`. Default is "openpgp". Other possible values are "x509", "ssh".

[][486]gpg.<format>.program

Use this to customize the program used for the signing format you chose. (see `gpg.program` and `gpg.format`) `gpg.program` can still be used as a legacy synonym for `gpg.openpgp.program`. The default value for `gpg.x509.program` is "gpgsm" and `gpg.ssh.program` is "ssh-keygen".

[][487]gpg.minTrustLevel

Specifies a minimum trust level for signature verification. If this option is unset, then signature verification for merge operations require a key with at least `marginal` trust. Other operations that perform signature verification require a key with at least `undefined` trust. Setting this option overrides the required trust-level for all operations. Supported values, in increasing order of significance:

-   `undefined`
    
-   `never`
    
-   `marginal`
    
-   `fully`
    
-   `ultimate`
    

gpg.ssh.defaultKeyCommand: This command that will be run when user.signingkey is not set and a ssh signature is requested. On successful exit a valid ssh public key is expected in the first line of its output. To automatically use the first available key from your ssh-agent set this to "ssh-add -L".

[][488]gpg.ssh.allowedSignersFile

A file containing ssh public keys which you are willing to trust. The file consists of one or more lines of principals followed by an ssh public key. e.g.: [user1@example.com][489],[user2@example.com][490] ssh-rsa AAAAX1… See ssh-keygen(1) "ALLOWED SIGNERS" for details. The principal is only used to identify the key and is available when verifying a signature.

SSH has no concept of trust levels like gpg does. To be able to differentiate between valid signatures and trusted signatures the trust level of a signature verification is set to `fully` when the public key is present in the allowedSignersFile. Otherwise the trust level is `undefined` and git verify-commit/tag will fail.

This file can be set to a location outside of the repository and every developer maintains their own trust store. A central repository server could generate this file automatically from ssh keys with push access to verify the code against. In a corporate setting this file is probably generated at a global location from automation that already handles developer ssh keys.

A repository that only allows signed commits can store the file in the repository itself using a path relative to the top-level of the working tree. This way only committers with an already valid key can add or change keys in the keyring.

Using a SSH CA key with the cert-authority option (see ssh-keygen(1) "CERTIFICATES") is also valid.

[][491]gpg.ssh.revocationFile

Either a SSH KRL or a list of revoked public keys (without the principal prefix). See ssh-keygen(1) for details. If a public key is found in this file then it will always be treated as having trust level "never" and signatures will show as invalid.

[][492]gui.commitMsgWidth

Defines how wide the commit message window is in the [git-gui\[1\]][493]. "75" is the default.

[][494]gui.diffContext

Specifies how many context lines should be used in calls to diff made by the [git-gui\[1\]][495]. The default is "5".

[][496]gui.displayUntracked

Determines if [git-gui\[1\]][497] shows untracked files in the file list. The default is "true".

[][498]gui.encoding

Specifies the default character encoding to use for displaying of file contents in [git-gui\[1\]][499] and [gitk\[1\]][500]. It can be overridden by setting the *encoding* attribute for relevant files (see [gitattributes\[5\]][501]). If this option is not set, the tools default to the locale encoding.

[][502]gui.matchTrackingBranch

Determines if new branches created with [git-gui\[1\]][503] should default to tracking remote branches with matching names or not. Default: "false".

[][504]gui.newBranchTemplate

Is used as suggested name when creating new branches using the [git-gui\[1\]][505].

[][506]gui.pruneDuringFetch

"true" if [git-gui\[1\]][507] should prune remote-tracking branches when performing a fetch. The default value is "false".

[][508]gui.trustmtime

Determines if [git-gui\[1\]][509] should trust the file modification timestamp or not. By default the timestamps are not trusted.

[][510]gui.spellingDictionary

Specifies the dictionary used for spell checking commit messages in the [git-gui\[1\]][511]. When set to "none" spell checking is turned off.

[][512]gui.fastCopyBlame

If true, *git gui blame* uses `-C` instead of `-C -C` for original location detection. It makes blame significantly faster on huge repositories at the expense of less thorough copy detection.

[][513]gui.copyBlameThreshold

Specifies the threshold to use in *git gui blame* original location detection, measured in alphanumeric characters. See the [git-blame\[1\]][514] manual for more information on copy detection.

[][515]gui.blamehistoryctx

Specifies the radius of history context in days to show in [gitk\[1\]][516] for the selected commit, when the `Show History Context` menu item is invoked from *git gui blame*. If this variable is set to zero, the whole history is shown.

[][517]guitool.<name>.cmd

Specifies the shell command line to execute when the corresponding item of the [git-gui\[1\]][518] `Tools` menu is invoked. This option is mandatory for every tool. The command is executed from the root of the working directory, and in the environment it receives the name of the tool as `GIT_GUITOOL`, the name of the currently selected file as *FILENAME*, and the name of the current branch as *CUR\_BRANCH* (if the head is detached, *CUR\_BRANCH* is empty).

[][519]guitool.<name>.needsFile

Run the tool only if a diff is selected in the GUI. It guarantees that *FILENAME* is not empty.

[][520]guitool.<name>.noConsole

Run the command silently, without creating a window to display its output.

[][521]guitool.<name>.noRescan

Don’t rescan the working directory for changes after the tool finishes execution.

[][522]guitool.<name>.confirm

Show a confirmation dialog before actually running the tool.

[][523]guitool.<name>.argPrompt

Request a string argument from the user, and pass it to the tool through the `ARGS` environment variable. Since requesting an argument implies confirmation, the *confirm* option has no effect if this is enabled. If the option is set to *true*, *yes*, or *1*, the dialog uses a built-in generic prompt; otherwise the exact value of the variable is used.

[][524]guitool.<name>.revPrompt

Request a single valid revision from the user, and set the `REVISION` environment variable. In other aspects this option is similar to *argPrompt*, and can be used together with it.

[][525]guitool.<name>.revUnmerged

Show only unmerged branches in the *revPrompt* subdialog. This is useful for tools similar to merge or rebase, but not for things like checkout or reset.

[][526]guitool.<name>.title

Specifies the title to use for the prompt dialog. The default is the tool name.

[][527]guitool.<name>.prompt

Specifies the general prompt string to display at the top of the dialog, before subsections for *argPrompt* and *revPrompt*. The default value includes the actual command.

[][528]help.browser

Specify the browser that will be used to display help in the *web* format. See [git-help\[1\]][529].

[][530]help.format

Override the default help format used by [git-help\[1\]][531]. Values *man*, *info*, *web* and *html* are supported. *man* is the default. *web* and *html* are the same.

[][532]help.autoCorrect

If git detects typos and can identify exactly one valid command similar to the error, git will try to suggest the correct command or even run the suggestion automatically. Possible config values are:

-   0 (default): show the suggested command.
    
-   positive number: run the suggested command after specified deciseconds (0.1 sec).
    
-   "immediate": run the suggested command immediately.
    
-   "prompt": show the suggestion and prompt for confirmation to run the command.
    
-   "never": don’t run or show any suggested command.
    

[][533]help.htmlPath

Specify the path where the HTML documentation resides. File system paths and URLs are supported. HTML pages will be prefixed with this path when help is displayed in the *web* format. This defaults to the documentation path of your Git installation.

[][534]http.proxy

Override the HTTP proxy, normally configured using the *http\_proxy*, *https\_proxy*, and *all\_proxy* environment variables (see `curl(1)`). In addition to the syntax understood by curl, it is possible to specify a proxy string with a user name but no password, in which case git will attempt to acquire one in the same way it does for other credentials. See [gitcredentials\[7\]][535] for more information. The syntax thus is *\[protocol://\]\[user\[:password\]@\]proxyhost\[:port\]*. This can be overridden on a per-remote basis; see remote.<name>.proxy

[][536]http.proxyAuthMethod

Set the method with which to authenticate against the HTTP proxy. This only takes effect if the configured proxy string contains a user name part (i.e. is of the form *user@host* or *user@host:port*). This can be overridden on a per-remote basis; see `remote.<name>.proxyAuthMethod`. Both can be overridden by the `GIT_HTTP_PROXY_AUTHMETHOD` environment variable. Possible values are:

-   `anyauth` - Automatically pick a suitable authentication method. It is assumed that the proxy answers an unauthenticated request with a 407 status code and one or more Proxy-authenticate headers with supported authentication methods. This is the default.
    
-   `basic` - HTTP Basic authentication
    
-   `digest` - HTTP Digest authentication; this prevents the password from being transmitted to the proxy in clear text
    
-   `negotiate` - GSS-Negotiate authentication (compare the --negotiate option of `curl(1)`)
    
-   `ntlm` - NTLM authentication (compare the --ntlm option of `curl(1)`)
    

[][537]http.proxySSLCert

The pathname of a file that stores a client certificate to use to authenticate with an HTTPS proxy. Can be overridden by the `GIT_PROXY_SSL_CERT` environment variable.

[][538]http.proxySSLKey

The pathname of a file that stores a private key to use to authenticate with an HTTPS proxy. Can be overridden by the `GIT_PROXY_SSL_KEY` environment variable.

[][539]http.proxySSLCertPasswordProtected

Enable Git’s password prompt for the proxy SSL certificate. Otherwise OpenSSL will prompt the user, possibly many times, if the certificate or private key is encrypted. Can be overridden by the `GIT_PROXY_SSL_CERT_PASSWORD_PROTECTED` environment variable.

[][540]http.proxySSLCAInfo

Pathname to the file containing the certificate bundle that should be used to verify the proxy with when using an HTTPS proxy. Can be overridden by the `GIT_PROXY_SSL_CAINFO` environment variable.

[][541]http.emptyAuth

Attempt authentication without seeking a username or password. This can be used to attempt GSS-Negotiate authentication without specifying a username in the URL, as libcurl normally requires a username for authentication.

[][542]http.delegation

Control GSSAPI credential delegation. The delegation is disabled by default in libcurl since version 7.21.7. Set parameter to tell the server what it is allowed to delegate when it comes to user credentials. Used with GSS/kerberos. Possible values are:

-   `none` - Don’t allow any delegation.
    
-   `policy` - Delegates if and only if the OK-AS-DELEGATE flag is set in the Kerberos service ticket, which is a matter of realm policy.
    
-   `always` - Unconditionally allow the server to delegate.
    

Pass an additional HTTP header when communicating with a server. If more than one such entry exists, all of them are added as extra headers. To allow overriding the settings inherited from the system config, an empty value will reset the extra headers to the empty list.

[][543]http.cookieFile

The pathname of a file containing previously stored cookie lines, which should be used in the Git http session, if they match the server. The file format of the file to read cookies from should be plain HTTP headers or the Netscape/Mozilla cookie file format (see `curl(1)`). NOTE that the file specified with http.cookieFile is used only as input unless http.saveCookies is set.

[][544]http.saveCookies

If set, store cookies received during requests to the file specified by http.cookieFile. Has no effect if http.cookieFile is unset.

[][545]http.version

Use the specified HTTP protocol version when communicating with a server. If you want to force the default. The available and default version depend on libcurl. Currently the possible values of this option are:

[][546]http.sslVersion

The SSL version to use when negotiating an SSL connection, if you want to force the default. The available and default version depend on whether libcurl was built against NSS or OpenSSL and the particular configuration of the crypto library in use. Internally this sets the *CURLOPT\_SSL\_VERSION* option; see the libcurl documentation for more details on the format of this option and for the ssl version supported. Currently the possible values of this option are:

-   sslv2
    
-   sslv3
    
-   tlsv1
    
-   tlsv1.0
    
-   tlsv1.1
    
-   tlsv1.2
    
-   tlsv1.3
    

Can be overridden by the `GIT_SSL_VERSION` environment variable. To force git to use libcurl’s default ssl version and ignore any explicit http.sslversion option, set `GIT_SSL_VERSION` to the empty string.

[][547]http.sslCipherList

A list of SSL ciphers to use when negotiating an SSL connection. The available ciphers depend on whether libcurl was built against NSS or OpenSSL and the particular configuration of the crypto library in use. Internally this sets the *CURLOPT\_SSL\_CIPHER\_LIST* option; see the libcurl documentation for more details on the format of this list.

Can be overridden by the `GIT_SSL_CIPHER_LIST` environment variable. To force git to use libcurl’s default cipher list and ignore any explicit http.sslCipherList option, set `GIT_SSL_CIPHER_LIST` to the empty string.

[][548]http.sslVerify

Whether to verify the SSL certificate when fetching or pushing over HTTPS. Defaults to true. Can be overridden by the `GIT_SSL_NO_VERIFY` environment variable.

[][549]http.sslCert

File containing the SSL certificate when fetching or pushing over HTTPS. Can be overridden by the `GIT_SSL_CERT` environment variable.

[][550]http.sslKey

File containing the SSL private key when fetching or pushing over HTTPS. Can be overridden by the `GIT_SSL_KEY` environment variable.

[][551]http.sslCertPasswordProtected

Enable Git’s password prompt for the SSL certificate. Otherwise OpenSSL will prompt the user, possibly many times, if the certificate or private key is encrypted. Can be overridden by the `GIT_SSL_CERT_PASSWORD_PROTECTED` environment variable.

[][552]http.sslCAInfo

File containing the certificates to verify the peer with when fetching or pushing over HTTPS. Can be overridden by the `GIT_SSL_CAINFO` environment variable.

[][553]http.sslCAPath

Path containing files with the CA certificates to verify the peer with when fetching or pushing over HTTPS. Can be overridden by the `GIT_SSL_CAPATH` environment variable.

[][554]http.sslBackend

Name of the SSL backend to use (e.g. "openssl" or "schannel"). This option is ignored if cURL lacks support for choosing the SSL backend at runtime.

[][555]http.schannelCheckRevoke

Used to enforce or disable certificate revocation checks in cURL when http.sslBackend is set to "schannel". Defaults to `true` if unset. Only necessary to disable this if Git consistently errors and the message is about checking the revocation status of a certificate. This option is ignored if cURL lacks support for setting the relevant SSL option at runtime.

[][556]http.schannelUseSSLCAInfo

As of cURL v7.60.0, the Secure Channel backend can use the certificate bundle provided via `http.sslCAInfo`, but that would override the Windows Certificate Store. Since this is not desirable by default, Git will tell cURL not to use that bundle by default when the `schannel` backend was configured via `http.sslBackend`, unless `http.schannelUseSSLCAInfo` overrides this behavior.

[][557]http.pinnedpubkey

Public key of the https service. It may either be the filename of a PEM or DER encoded public key file or a string starting with *sha256//* followed by the base64 encoded sha256 hash of the public key. See also libcurl *CURLOPT\_PINNEDPUBLICKEY*. git will exit with an error if this option is set but not supported by cURL.

[][558]http.sslTry

Attempt to use AUTH SSL/TLS and encrypted data transfers when connecting via regular FTP protocol. This might be needed if the FTP server requires it for security reasons or you wish to connect securely whenever remote FTP server supports it. Default is false since it might trigger certificate verification errors on misconfigured servers.

[][559]http.maxRequests

How many HTTP requests to launch in parallel. Can be overridden by the `GIT_HTTP_MAX_REQUESTS` environment variable. Default is 5.

[][560]http.minSessions

The number of curl sessions (counted across slots) to be kept across requests. They will not be ended with curl\_easy\_cleanup() until http\_cleanup() is invoked. If USE\_CURL\_MULTI is not defined, this value will be capped at 1. Defaults to 1.

[][561]http.postBuffer

Maximum size in bytes of the buffer used by smart HTTP transports when POSTing data to the remote system. For requests larger than this buffer size, HTTP/1.1 and Transfer-Encoding: chunked is used to avoid creating a massive pack file locally. Default is 1 MiB, which is sufficient for most requests.

Note that raising this limit is only effective for disabling chunked transfer encoding and therefore should be used only where the remote server or a proxy only supports HTTP/1.0 or is noncompliant with the HTTP standard. Raising this is not, in general, an effective solution for most push problems, but can increase memory consumption significantly since the entire buffer is allocated even for small pushes.

[][562]http.lowSpeedLimit, http.lowSpeedTime

If the HTTP transfer speed is less than *http.lowSpeedLimit* for longer than *http.lowSpeedTime* seconds, the transfer is aborted. Can be overridden by the `GIT_HTTP_LOW_SPEED_LIMIT` and `GIT_HTTP_LOW_SPEED_TIME` environment variables.

[][563]http.noEPSV

A boolean which disables using of EPSV ftp command by curl. This can helpful with some "poor" ftp servers which don’t support EPSV mode. Can be overridden by the `GIT_CURL_FTP_NO_EPSV` environment variable. Default is false (curl will use EPSV).

[][564]http.userAgent

The HTTP USER\_AGENT string presented to an HTTP server. The default value represents the version of the client Git such as git/1.7.1. This option allows you to override this value to a more common value such as Mozilla/4.0. This may be necessary, for instance, if connecting through a firewall that restricts HTTP connections to a set of common USER\_AGENT strings (but not including those like git/1.7.1). Can be overridden by the `GIT_HTTP_USER_AGENT` environment variable.

[][565]http.followRedirects

Whether git should follow HTTP redirects. If set to `true`, git will transparently follow any redirect issued by a server it encounters. If set to `false`, git will treat all redirects as errors. If set to `initial`, git will follow redirects only for the initial request to a remote, but not for subsequent follow-up HTTP requests. Since git uses the redirected URL as the base for the follow-up requests, this is generally sufficient. The default is `initial`.

[][566]http.<url>.\*

Any of the http.\* options above can be applied selectively to some URLs. For a config key to match a URL, each element of the config key is compared to that of the URL, in the following order:

1.  Scheme (e.g., `https` in `https://example.com/`). This field must match exactly between the config key and the URL.
    
2.  Host/domain name (e.g., `example.com` in `https://example.com/`). This field must match between the config key and the URL. It is possible to specify a `*` as part of the host name to match all subdomains at this level. `https://*.example.com/` for example would match `https://foo.example.com/`, but not `https://foo.bar.example.com/`.
    
3.  Port number (e.g., `8080` in `http://example.com:8080/`). This field must match exactly between the config key and the URL. Omitted port numbers are automatically converted to the correct default for the scheme before matching.
    
4.  Path (e.g., `repo.git` in `https://example.com/repo.git`). The path field of the config key must match the path field of the URL either exactly or as a prefix of slash-delimited path elements. This means a config key with path `foo/` matches URL path `foo/bar`. A prefix can only match on a slash (`/`) boundary. Longer matches take precedence (so a config key with path `foo/bar` is a better match to URL path `foo/bar` than a config key with just path `foo/`).
    
5.  User name (e.g., `user` in `https://user@example.com/repo.git`). If the config key has a user name it must match the user name in the URL exactly. If the config key does not have a user name, that config key will match a URL with any user name (including none), but at a lower precedence than a config key with a user name.
    

The list above is ordered by decreasing precedence; a URL that matches a config key’s path is preferred to one that matches its user name. For example, if the URL is `https://user@example.com/foo/bar` a config key match of `https://example.com/foo` will be preferred over a config key match of `https://user@example.com`.

All URLs are normalized before attempting any matching (the password part, if embedded in the URL, is always ignored for matching purposes) so that equivalent URLs that are simply spelled differently will match properly. Environment variable settings always override any matches. The URLs that are matched against are those given directly to Git commands. This means any URLs visited as a result of a redirection do not participate in matching.

[][567]i18n.commitEncoding

Character encoding the commit messages are stored in; Git itself does not care per se, but this information is necessary e.g. when importing commits from emails or in the gitk graphical history browser (and possibly at other places in the future or in other porcelains). See e.g. [git-mailinfo\[1\]][568]. Defaults to *utf-8*.

[][569]i18n.logOutputEncoding

Character encoding the commit messages are converted to when running *git log* and friends.

[][570]imap.folder

The folder to drop the mails into, which is typically the Drafts folder. For example: "INBOX.Drafts", "INBOX/Drafts" or "\[Gmail\]/Drafts". Required.

[][571]imap.tunnel

Command used to setup a tunnel to the IMAP server through which commands will be piped instead of using a direct network connection to the server. Required when imap.host is not set.

[][572]imap.host

A URL identifying the server. Use an `imap://` prefix for non-secure connections and an `imaps://` prefix for secure connections. Ignored when imap.tunnel is set, but required otherwise.

[][573]imap.user

The username to use when logging in to the server.

[][574]imap.pass

The password to use when logging in to the server.

[][575]imap.port

An integer port number to connect to on the server. Defaults to 143 for imap:// hosts and 993 for imaps:// hosts. Ignored when imap.tunnel is set.

[][576]imap.sslverify

A boolean to enable/disable verification of the server certificate used by the SSL/TLS connection. Default is `true`. Ignored when imap.tunnel is set.

[][577]imap.preformattedHTML

A boolean to enable/disable the use of html encoding when sending a patch. An html encoded patch will be bracketed with <pre> and have a content type of text/html. Ironically, enabling this option causes Thunderbird to send the patch as a plain/text, format=fixed email. Default is `false`.

[][578]imap.authMethod

Specify authenticate method for authentication with IMAP server. If Git was built with the NO\_CURL option, or if your curl version is older than 7.34.0, or if you’re running git-imap-send with the `--no-curl` option, the only supported method is *CRAM-MD5*. If this is not set then *git imap-send* uses the basic IMAP plaintext LOGIN command.

[][579]index.recordEndOfIndexEntries

Specifies whether the index file should include an "End Of Index Entry" section. This reduces index load time on multiprocessor machines but produces a message "ignoring EOIE extension" when reading the index using Git versions before 2.20. Defaults to *true* if index.threads has been explicitly enabled, *false* otherwise.

[][580]index.recordOffsetTable

Specifies whether the index file should include an "Index Entry Offset Table" section. This reduces index load time on multiprocessor machines but produces a message "ignoring IEOT extension" when reading the index using Git versions before 2.20. Defaults to *true* if index.threads has been explicitly enabled, *false* otherwise.

[][581]index.sparse

When enabled, write the index using sparse-directory entries. This has no effect unless `core.sparseCheckout` and `core.sparseCheckoutCone` are both enabled. Defaults to *false*.

[][582]index.threads

Specifies the number of threads to spawn when loading the index. This is meant to reduce index load time on multiprocessor machines. Specifying 0 or *true* will cause Git to auto-detect the number of CPU’s and set the number of threads accordingly. Specifying 1 or *false* will disable multithreading. Defaults to *true*.

[][583]index.version

Specify the version with which new index files should be initialized. This does not affect existing repositories. If `feature.manyFiles` is enabled, then the default is 4.

[][584]init.templateDir

Specify the directory from which templates will be copied. (See the "TEMPLATE DIRECTORY" section of [git-init\[1\]][585].)

[][586]init.defaultBranch

Allows overriding the default branch name e.g. when initializing a new repository.

[][587]instaweb.browser

Specify the program that will be used to browse your working repository in gitweb. See [git-instaweb\[1\]][588].

[][589]instaweb.httpd

The HTTP daemon command-line to start gitweb on your working repository. See [git-instaweb\[1\]][590].

[][591]instaweb.local

If true the web server started by [git-instaweb\[1\]][592] will be bound to the local IP (127.0.0.1).

[][593]instaweb.modulePath

The default module path for [git-instaweb\[1\]][594] to use instead of /usr/lib/apache2/modules. Only used if httpd is Apache.

[][595]instaweb.port

The port number to bind the gitweb httpd to. See [git-instaweb\[1\]][596].

[][597]interactive.singleKey

In interactive commands, allow the user to provide one-letter input with a single key (i.e., without hitting enter). Currently this is used by the `--patch` mode of [git-add\[1\]][598], [git-checkout\[1\]][599], [git-restore\[1\]][600], [git-commit\[1\]][601], [git-reset\[1\]][602], and [git-stash\[1\]][603]. Note that this setting is silently ignored if portable keystroke input is not available; requires the Perl module Term::ReadKey.

[][604]interactive.diffFilter

When an interactive command (such as `git add --patch`) shows a colorized diff, git will pipe the diff through the shell command defined by this configuration variable. The command may mark up the diff further for human consumption, provided that it retains a one-to-one correspondence with the lines in the original diff. Defaults to disabled (no filtering).

[][605]log.abbrevCommit

If true, makes [git-log\[1\]][606], [git-show\[1\]][607], and [git-whatchanged\[1\]][608] assume `--abbrev-commit`. You may override this option with `--no-abbrev-commit`.

[][609]log.date

Set the default date-time mode for the *log* command. Setting a value for log.date is similar to using *git log*'s `--date` option. See [git-log\[1\]][610] for details.

[][611]log.decorate

Print out the ref names of any commits that are shown by the log command. If *short* is specified, the ref name prefixes *refs/heads/*, *refs/tags/* and *refs/remotes/* will not be printed. If *full* is specified, the full ref name (including prefix) will be printed. If *auto* is specified, then if the output is going to a terminal, the ref names are shown as if *short* were given, otherwise no ref names are shown. This is the same as the `--decorate` option of the `git log`.

[][612]log.excludeDecoration

Exclude the specified patterns from the log decorations. This is similar to the `--decorate-refs-exclude` command-line option, but the config option can be overridden by the `--decorate-refs` option.

[][613]log.diffMerges

Set default diff format to be used for merge commits. See `--diff-merges` in [git-log\[1\]][614] for details. Defaults to `separate`.

[][615]log.follow

If `true`, `git log` will act as if the `--follow` option was used when a single <path> is given. This has the same limitations as `--follow`, i.e. it cannot be used to follow multiple files and does not work well on non-linear history.

[][616]log.graphColors

A list of colors, separated by commas, that can be used to draw history lines in `git log --graph`.

[][617]log.showRoot

If true, the initial commit will be shown as a big creation event. This is equivalent to a diff against an empty tree. Tools like [git-log\[1\]][618] or [git-whatchanged\[1\]][619], which normally hide the root commit will now show it. True by default.

[][620]log.showSignature

If true, makes [git-log\[1\]][621], [git-show\[1\]][622], and [git-whatchanged\[1\]][623] assume `--show-signature`.

[][624]log.mailmap

If true, makes [git-log\[1\]][625], [git-show\[1\]][626], and [git-whatchanged\[1\]][627] assume `--use-mailmap`, otherwise assume `--no-use-mailmap`. True by default.

[][628]lsrefs.unborn

May be "advertise" (the default), "allow", or "ignore". If "advertise", the server will respond to the client sending "unborn" (as described in protocol-v2.txt) and will advertise support for this feature during the protocol v2 capability advertisement. "allow" is the same as "advertise" except that the server will not advertise support for this feature; this is useful for load-balanced servers that cannot be updated atomically (for example), since the administrator could configure "allow", then after a delay, configure "advertise".

[][629]mailinfo.scissors

If true, makes [git-mailinfo\[1\]][630] (and therefore [git-am\[1\]][631]) act by default as if the --scissors option was provided on the command-line. When active, this features removes everything from the message body before a scissors line (i.e. consisting mainly of ">8", "8<" and "-").

[][632]mailmap.file

The location of an augmenting mailmap file. The default mailmap, located in the root of the repository, is loaded first, then the mailmap file pointed to by this variable. The location of the mailmap file may be in a repository subdirectory, or somewhere outside of the repository itself. See [git-shortlog\[1\]][633] and [git-blame\[1\]][634].

[][635]mailmap.blob

Like `mailmap.file`, but consider the value as a reference to a blob in the repository. If both `mailmap.file` and `mailmap.blob` are given, both are parsed, with entries from `mailmap.file` taking precedence. In a bare repository, this defaults to `HEAD:.mailmap`. In a non-bare repository, it defaults to empty.

[][636]maintenance.auto

This boolean config option controls whether some commands run `git maintenance run --auto` after doing their normal work. Defaults to true.

[][637]maintenance.strategy

This string config option provides a way to specify one of a few recommended schedules for background maintenance. This only affects which tasks are run during `git maintenance run --schedule=X` commands, provided no `--task=<task>` arguments are provided. Further, if a `maintenance.<task>.schedule` config value is set, then that value is used instead of the one provided by `maintenance.strategy`. The possible strategy strings are:

-   `none`: This default setting implies no task are run at any schedule.
    
-   `incremental`: This setting optimizes for performing small maintenance activities that do not delete any data. This does not schedule the `gc` task, but runs the `prefetch` and `commit-graph` tasks hourly, the `loose-objects` and `incremental-repack` tasks daily, and the `pack-refs` task weekly.
    

[][638]maintenance.<task>.enabled

This boolean config option controls whether the maintenance task with name `<task>` is run when no `--task` option is specified to `git maintenance run`. These config values are ignored if a `--task` option exists. By default, only `maintenance.gc.enabled` is true.

[][639]maintenance.<task>.schedule

This config option controls whether or not the given `<task>` runs during a `git maintenance run --schedule=<frequency>` command. The value must be one of "hourly", "daily", or "weekly".

[][640]maintenance.commit-graph.auto

This integer config option controls how often the `commit-graph` task should be run as part of `git maintenance run --auto`. If zero, then the `commit-graph` task will not run with the `--auto` option. A negative value will force the task to run every time. Otherwise, a positive value implies the command should run when the number of reachable commits that are not in the commit-graph file is at least the value of `maintenance.commit-graph.auto`. The default value is 100.

[][641]maintenance.loose-objects.auto

This integer config option controls how often the `loose-objects` task should be run as part of `git maintenance run --auto`. If zero, then the `loose-objects` task will not run with the `--auto` option. A negative value will force the task to run every time. Otherwise, a positive value implies the command should run when the number of loose objects is at least the value of `maintenance.loose-objects.auto`. The default value is 100.

[][642]maintenance.incremental-repack.auto

This integer config option controls how often the `incremental-repack` task should be run as part of `git maintenance run --auto`. If zero, then the `incremental-repack` task will not run with the `--auto` option. A negative value will force the task to run every time. Otherwise, a positive value implies the command should run when the number of pack-files not in the multi-pack-index is at least the value of `maintenance.incremental-repack.auto`. The default value is 10.

[][643]man.viewer

Specify the programs that may be used to display help in the *man* format. See [git-help\[1\]][644].

[][645]man.<tool>.cmd

Specify the command to invoke the specified man viewer. The specified command is evaluated in shell with the man page passed as argument. (See [git-help\[1\]][646].)

[][647]man.<tool>.path

Override the path for the given tool that may be used to display help in the *man* format. See [git-help\[1\]][648].

[][649]merge.conflictStyle

Specify the style in which conflicted hunks are written out to working tree files upon merge. The default is "merge", which shows a `<<<<<<<` conflict marker, changes made by one side, a `=======` marker, changes made by the other side, and then a `>>>>>>>` marker. An alternate style, "diff3", adds a `|||||||` marker and the original text before the `=======` marker.

[][650]merge.defaultToUpstream

If merge is called without any commit argument, merge the upstream branches configured for the current branch by using their last observed values stored in their remote-tracking branches. The values of the `branch.<current branch>.merge` that name the branches at the remote named by `branch.<current branch>.remote` are consulted, and then they are mapped via `remote.<remote>.fetch` to their corresponding remote-tracking branches, and the tips of these tracking branches are merged. Defaults to true.

[][651]merge.ff

By default, Git does not create an extra merge commit when merging a commit that is a descendant of the current commit. Instead, the tip of the current branch is fast-forwarded. When set to `false`, this variable tells Git to create an extra merge commit in such a case (equivalent to giving the `--no-ff` option from the command line). When set to `only`, only such fast-forward merges are allowed (equivalent to giving the `--ff-only` option from the command line).

[][652]merge.verifySignatures

If true, this is equivalent to the --verify-signatures command line option. See [git-merge\[1\]][653] for details.

[][654]merge.branchdesc

In addition to branch names, populate the log message with the branch description text associated with them. Defaults to false.

[][655]merge.log

In addition to branch names, populate the log message with at most the specified number of one-line descriptions from the actual commits that are being merged. Defaults to false, and true is a synonym for 20.

[][656]merge.suppressDest

By adding a glob that matches the names of integration branches to this multi-valued configuration variable, the default merge message computed for merges into these integration branches will omit "into <branch name>" from its title.

An element with an empty value can be used to clear the list of globs accumulated from previous configuration entries. When there is no `merge.suppressDest` variable defined, the default value of `master` is used for backward compatibility.

[][657]merge.renameLimit

The number of files to consider in the exhaustive portion of rename detection during a merge. If not specified, defaults to the value of diff.renameLimit. If neither merge.renameLimit nor diff.renameLimit are specified, currently defaults to 7000. This setting has no effect if rename detection is turned off.

[][658]merge.renames

Whether Git detects renames. If set to "false", rename detection is disabled. If set to "true", basic rename detection is enabled. Defaults to the value of diff.renames.

[][659]merge.directoryRenames

Whether Git detects directory renames, affecting what happens at merge time to new files added to a directory on one side of history when that directory was renamed on the other side of history. If merge.directoryRenames is set to "false", directory rename detection is disabled, meaning that such new files will be left behind in the old directory. If set to "true", directory rename detection is enabled, meaning that such new files will be moved into the new directory. If set to "conflict", a conflict will be reported for such paths. If merge.renames is false, merge.directoryRenames is ignored and treated as false. Defaults to "conflict".

[][660]merge.renormalize

Tell Git that canonical representation of files in the repository has changed over time (e.g. earlier commits record text files with CRLF line endings, but recent ones use LF line endings). In such a repository, Git can convert the data recorded in commits to a canonical form before performing a merge to reduce unnecessary conflicts. For more information, see section "Merging branches with differing checkin/checkout attributes" in [gitattributes\[5\]][661].

[][662]merge.stat

Whether to print the diffstat between ORIG\_HEAD and the merge result at the end of the merge. True by default.

[][663]merge.autoStash

When set to true, automatically create a temporary stash entry before the operation begins, and apply it after the operation ends. This means that you can run merge on a dirty worktree. However, use with care: the final stash application after a successful merge might result in non-trivial conflicts. This option can be overridden by the `--no-autostash` and `--autostash` options of [git-merge\[1\]][664]. Defaults to false.

[][665]merge.tool

Controls which merge tool is used by [git-mergetool\[1\]][666]. The list below shows the valid built-in values. Any other value is treated as a custom merge tool and requires that a corresponding mergetool.<tool>.cmd variable is defined.

[][667]merge.guitool

Controls which merge tool is used by [git-mergetool\[1\]][668] when the -g/--gui flag is specified. The list below shows the valid built-in values. Any other value is treated as a custom merge tool and requires that a corresponding mergetool.<guitool>.cmd variable is defined.

-   araxis
    
-   bc
    
-   codecompare
    
-   deltawalker
    
-   diffmerge
    
-   diffuse
    
-   ecmerge
    
-   emerge
    
-   examdiff
    
-   guiffy
    
-   gvimdiff
    
-   kdiff3
    
-   meld
    
-   nvimdiff
    
-   opendiff
    
-   p4merge
    
-   smerge
    
-   tkdiff
    
-   tortoisemerge
    
-   vimdiff
    
-   winmerge
    
-   xxdiff
    

[][669]merge.verbosity

Controls the amount of output shown by the recursive merge strategy. Level 0 outputs nothing except a final error message if conflicts were detected. Level 1 outputs only conflicts, 2 outputs conflicts and file changes. Level 5 and above outputs debugging information. The default is level 2. Can be overridden by the `GIT_MERGE_VERBOSITY` environment variable.

[][670]merge.<driver>.name

Defines a human-readable name for a custom low-level merge driver. See [gitattributes\[5\]][671] for details.

[][672]merge.<driver>.driver

Defines the command that implements a custom low-level merge driver. See [gitattributes\[5\]][673] for details.

[][674]merge.<driver>.recursive

Names a low-level merge driver to be used when performing an internal merge between common ancestors. See [gitattributes\[5\]][675] for details.

[][676]mergetool.<tool>.path

Override the path for the given tool. This is useful in case your tool is not in the PATH.

[][677]mergetool.<tool>.cmd

Specify the command to invoke the specified merge tool. The specified command is evaluated in shell with the following variables available: *BASE* is the name of a temporary file containing the common base of the files to be merged, if available; *LOCAL* is the name of a temporary file containing the contents of the file on the current branch; *REMOTE* is the name of a temporary file containing the contents of the file from the branch being merged; *MERGED* contains the name of the file to which the merge tool should write the results of a successful merge.

[][678]mergetool.<tool>.hideResolved

Allows the user to override the global `mergetool.hideResolved` value for a specific tool. See `mergetool.hideResolved` for the full description.

[][679]mergetool.<tool>.trustExitCode

For a custom merge command, specify whether the exit code of the merge command can be used to determine whether the merge was successful. If this is not set to true then the merge target file timestamp is checked and the merge assumed to have been successful if the file has been updated, otherwise the user is prompted to indicate the success of the merge.

[][680]mergetool.meld.hasOutput

Older versions of `meld` do not support the `--output` option. Git will attempt to detect whether `meld` supports `--output` by inspecting the output of `meld --help`. Configuring `mergetool.meld.hasOutput` will make Git skip these checks and use the configured value instead. Setting `mergetool.meld.hasOutput` to `true` tells Git to unconditionally use the `--output` option, and `false` avoids using `--output`.

[][681]mergetool.meld.useAutoMerge

When the `--auto-merge` is given, meld will merge all non-conflicting parts automatically, highlight the conflicting parts and wait for user decision. Setting `mergetool.meld.useAutoMerge` to `true` tells Git to unconditionally use the `--auto-merge` option with `meld`. Setting this value to `auto` makes git detect whether `--auto-merge` is supported and will only use `--auto-merge` when available. A value of `false` avoids using `--auto-merge` altogether, and is the default value.

[][682]mergetool.hideResolved

During a merge Git will automatically resolve as many conflicts as possible and write the *MERGED* file containing conflict markers around any conflicts that it cannot resolve; *LOCAL* and *REMOTE* normally represent the versions of the file from before Git’s conflict resolution. This flag causes *LOCAL* and *REMOTE* to be overwriten so that only the unresolved conflicts are presented to the merge tool. Can be configured per-tool via the `mergetool.<tool>.hideResolved` configuration variable. Defaults to `false`.

[][683]mergetool.keepBackup

After performing a merge, the original file with conflict markers can be saved as a file with a `.orig` extension. If this variable is set to `false` then this file is not preserved. Defaults to `true` (i.e. keep the backup files).

[][684]mergetool.keepTemporaries

When invoking a custom merge tool, Git uses a set of temporary files to pass to the tool. If the tool returns an error and this variable is set to `true`, then these temporary files will be preserved, otherwise they will be removed after the tool has exited. Defaults to `false`.

[][685]mergetool.writeToTemp

Git writes temporary *BASE*, *LOCAL*, and *REMOTE* versions of conflicting files in the worktree by default. Git will attempt to use a temporary directory for these files when set `true`. Defaults to `false`.

[][686]mergetool.prompt

Prompt before each invocation of the merge resolution program.

[][687]notes.mergeStrategy

Which merge strategy to choose by default when resolving notes conflicts. Must be one of `manual`, `ours`, `theirs`, `union`, or `cat_sort_uniq`. Defaults to `manual`. See "NOTES MERGE STRATEGIES" section of [git-notes\[1\]][688] for more information on each strategy.

[][689]notes.<name>.mergeStrategy

Which merge strategy to choose when doing a notes merge into refs/notes/<name>. This overrides the more general "notes.mergeStrategy". See the "NOTES MERGE STRATEGIES" section in [git-notes\[1\]][690] for more information on the available strategies.

[][691]notes.displayRef

The (fully qualified) refname from which to show notes when showing commit messages. The value of this variable can be set to a glob, in which case notes from all matching refs will be shown. You may also specify this configuration variable several times. A warning will be issued for refs that do not exist, but a glob that does not match any refs is silently ignored.

This setting can be overridden with the `GIT_NOTES_DISPLAY_REF` environment variable, which must be a colon separated list of refs or globs.

The effective value of "core.notesRef" (possibly overridden by GIT\_NOTES\_REF) is also implicitly added to the list of refs to be displayed.

[][692]notes.rewrite.<command>

When rewriting commits with <command> (currently `amend` or `rebase`) and this variable is set to `true`, Git automatically copies your notes from the original to the rewritten commit. Defaults to `true`, but see "notes.rewriteRef" below.

[][693]notes.rewriteMode

When copying notes during a rewrite (see the "notes.rewrite.<command>" option), determines what to do if the target commit already has a note. Must be one of `overwrite`, `concatenate`, `cat_sort_uniq`, or `ignore`. Defaults to `concatenate`.

This setting can be overridden with the `GIT_NOTES_REWRITE_MODE` environment variable.

[][694]notes.rewriteRef

When copying notes during a rewrite, specifies the (fully qualified) ref whose notes should be copied. The ref may be a glob, in which case notes in all matching refs will be copied. You may also specify this configuration several times.

Does not have a default value; you must configure this variable to enable note rewriting. Set it to `refs/notes/commits` to enable rewriting for the default commit notes.

This setting can be overridden with the `GIT_NOTES_REWRITE_REF` environment variable, which must be a colon separated list of refs or globs.

[][695]pack.window

The size of the window used by [git-pack-objects\[1\]][696] when no window size is given on the command line. Defaults to 10.

[][697]pack.depth

The maximum delta depth used by [git-pack-objects\[1\]][698] when no maximum depth is given on the command line. Defaults to 50. Maximum value is 4095.

[][699]pack.windowMemory

The maximum size of memory that is consumed by each thread in [git-pack-objects\[1\]][700] for pack window memory when no limit is given on the command line. The value can be suffixed with "k", "m", or "g". When left unconfigured (or set explicitly to 0), there will be no limit.

[][701]pack.compression

An integer -1..9, indicating the compression level for objects in a pack file. -1 is the zlib default. 0 means no compression, and 1..9 are various speed/size tradeoffs, 9 being slowest. If not set, defaults to core.compression. If that is not set, defaults to -1, the zlib default, which is "a default compromise between speed and compression (currently equivalent to level 6)."

Note that changing the compression level will not automatically recompress all existing objects. You can force recompression by passing the -F option to [git-repack\[1\]][702].

[][703]pack.allowPackReuse

When true, and when reachability bitmaps are enabled, pack-objects will try to send parts of the bitmapped packfile verbatim. This can reduce memory and CPU usage to serve fetches, but might result in sending a slightly larger pack. Defaults to true.

[][704]pack.island

An extended regular expression configuring a set of delta islands. See "DELTA ISLANDS" in [git-pack-objects\[1\]][705] for details.

[][706]pack.islandCore

Specify an island name which gets to have its objects be packed first. This creates a kind of pseudo-pack at the front of one pack, so that the objects from the specified island are hopefully faster to copy into any pack that should be served to a user requesting these objects. In practice this means that the island specified should likely correspond to what is the most commonly cloned in the repo. See also "DELTA ISLANDS" in [git-pack-objects\[1\]][707].

[][708]pack.deltaCacheSize

The maximum memory in bytes used for caching deltas in [git-pack-objects\[1\]][709] before writing them out to a pack. This cache is used to speed up the writing object phase by not having to recompute the final delta result once the best match for all objects is found. Repacking large repositories on machines which are tight with memory might be badly impacted by this though, especially if this cache pushes the system into swapping. A value of 0 means no limit. The smallest size of 1 byte may be used to virtually disable this cache. Defaults to 256 MiB.

[][710]pack.deltaCacheLimit

The maximum size of a delta, that is cached in [git-pack-objects\[1\]][711]. This cache is used to speed up the writing object phase by not having to recompute the final delta result once the best match for all objects is found. Defaults to 1000. Maximum value is 65535.

[][712]pack.threads

Specifies the number of threads to spawn when searching for best delta matches. This requires that [git-pack-objects\[1\]][713] be compiled with pthreads otherwise this option is ignored with a warning. This is meant to reduce packing time on multiprocessor machines. The required amount of memory for the delta search window is however multiplied by the number of threads. Specifying 0 will cause Git to auto-detect the number of CPU’s and set the number of threads accordingly.

[][714]pack.indexVersion

Specify the default pack index version. Valid values are 1 for legacy pack index used by Git versions prior to 1.5.2, and 2 for the new pack index with capabilities for packs larger than 4 GB as well as proper protection against the repacking of corrupted packs. Version 2 is the default. Note that version 2 is enforced and this config option ignored whenever the corresponding pack is larger than 2 GB.

If you have an old Git that does not understand the version 2 `*.idx` file, cloning or fetching over a non native protocol (e.g. "http") that will copy both `*.pack` file and corresponding `*.idx` file from the other side may give you a repository that cannot be accessed with your older version of Git. If the `*.pack` file is smaller than 2 GB, however, you can use [git-index-pack\[1\]][715] on the \*.pack file to regenerate the `*.idx` file.

[][716]pack.packSizeLimit

The maximum size of a pack. This setting only affects packing to a file when repacking, i.e. the git:// protocol is unaffected. It can be overridden by the `--max-pack-size` option of [git-repack\[1\]][717]. Reaching this limit results in the creation of multiple packfiles.

Note that this option is rarely useful, and may result in a larger total on-disk size (because Git will not store deltas between packs), as well as worse runtime performance (object lookup within multiple packs is slower than a single pack, and optimizations like reachability bitmaps cannot cope with multiple packs).

If you need to actively run Git using smaller packfiles (e.g., because your filesystem does not support large files), this option may help. But if your goal is to transmit a packfile over a medium that supports limited sizes (e.g., removable media that cannot store the whole repository), you are likely better off creating a single large packfile and splitting it using a generic multi-volume archive tool (e.g., Unix `split`).

The minimum size allowed is limited to 1 MiB. The default is unlimited. Common unit suffixes of *k*, *m*, or *g* are supported.

[][718]pack.useBitmaps

When true, git will use pack bitmaps (if available) when packing to stdout (e.g., during the server side of a fetch). Defaults to true. You should not generally need to turn this off unless you are debugging pack bitmaps.

[][719]pack.useSparse

When true, git will default to using the *\--sparse* option in *git pack-objects* when the *\--revs* option is present. This algorithm only walks trees that appear in paths that introduce new objects. This can have significant performance benefits when computing a pack to send a small change. However, it is possible that extra objects are added to the pack-file if the included commits contain certain types of direct renames. Default is `true`.

[][720]pack.preferBitmapTips

When selecting which commits will receive bitmaps, prefer a commit at the tip of any reference that is a suffix of any value of this configuration over any other commits in the "selection window".

Note that setting this configuration to `refs/foo` does not mean that the commits at the tips of `refs/foo/bar` and `refs/foo/baz` will necessarily be selected. This is because commits are selected for bitmaps from within a series of windows of variable length.

If a commit at the tip of any reference which is a suffix of any value of this configuration is seen in a window, it is immediately given preference over any other commit in that window.

[][721]pack.writeBitmaps (deprecated)

This is a deprecated synonym for `repack.writeBitmaps`.

[][722]pack.writeBitmapHashCache

When true, git will include a "hash cache" section in the bitmap index (if one is written). This cache can be used to feed git’s delta heuristics, potentially leading to better deltas between bitmapped and non-bitmapped objects (e.g., when serving a fetch between an older, bitmapped pack and objects that have been pushed since the last gc). The downside is that it consumes 4 bytes per object of disk space. Defaults to true.

When writing a multi-pack reachability bitmap, no new namehashes are computed; instead, any namehashes stored in an existing bitmap are permuted into their appropriate location when writing a new bitmap.

[][723]pack.writeReverseIndex

When true, git will write a corresponding .rev file (see: [Documentation/technical/pack-format.txt][724]) for each new packfile that it writes in all places except for [git-fast-import\[1\]][725] and in the bulk checkin mechanism. Defaults to false.

If the value is boolean, turns on or off pagination of the output of a particular Git subcommand when writing to a tty. Otherwise, turns on pagination for the subcommand using the pager specified by the value of `pager.<cmd>`. If `--paginate` or `--no-pager` is specified on the command line, it takes precedence over this option. To disable pagination for all commands, set `core.pager` or `GIT_PAGER` to `cat`.

[][726]pretty.<name>

Alias for a --pretty= format string, as specified in [git-log\[1\]][727]. Any aliases defined here can be used just as the built-in pretty formats could. For example, running `git config pretty.changelog "format:* %H %s"` would cause the invocation `git log --pretty=changelog` to be equivalent to running `git log "--pretty=format:* %H %s"`. Note that an alias with the same name as a built-in format will be silently ignored.

[][728]protocol.allow

If set, provide a user defined default policy for all protocols which don’t explicitly have a policy (`protocol.<name>.allow`). By default, if unset, known-safe protocols (http, https, git, ssh, file) have a default policy of `always`, known-dangerous protocols (ext) have a default policy of `never`, and all other protocols have a default policy of `user`. Supported policies:

-   `always` - protocol is always able to be used.
    
-   `never` - protocol is never able to be used.
    
-   `user` - protocol is only able to be used when `GIT_PROTOCOL_FROM_USER` is either unset or has a value of 1. This policy should be used when you want a protocol to be directly usable by the user but don’t want it used by commands which execute clone/fetch/push commands without user input, e.g. recursive submodule initialization.
    

[][729]protocol.<name>.allow

Set a policy to be used by protocol `<name>` with clone/fetch/push commands. See `protocol.allow` above for the available policies.

The protocol names currently used by git are:

-   `file`: any local file-based path (including `file://` URLs, or local paths)
    
-   `git`: the anonymous git protocol over a direct TCP connection (or proxy, if configured)
    
-   `ssh`: git over ssh (including `host:path` syntax, `ssh://`, etc).
    
-   `http`: git over http, both "smart http" and "dumb http". Note that this does *not* include `https`; if you want to configure both, you must do so individually.
    
-   any external helpers are named by their protocol (e.g., use `hg` to allow the `git-remote-hg` helper)
    

[][730]protocol.version

If set, clients will attempt to communicate with a server using the specified protocol version. If the server does not support it, communication falls back to version 0. If unset, the default is `2`. Supported versions:

-   `0` - the original wire protocol.
    
-   `1` - the original wire protocol with the addition of a version string in the initial response from the server.
    
-   `2` - [wire protocol version 2][731].
    

[][732]pull.ff

By default, Git does not create an extra merge commit when merging a commit that is a descendant of the current commit. Instead, the tip of the current branch is fast-forwarded. When set to `false`, this variable tells Git to create an extra merge commit in such a case (equivalent to giving the `--no-ff` option from the command line). When set to `only`, only such fast-forward merges are allowed (equivalent to giving the `--ff-only` option from the command line). This setting overrides `merge.ff` when pulling.

[][733]pull.rebase

When true, rebase branches on top of the fetched branch, instead of merging the default branch from the default remote when "git pull" is run. See "branch.<name>.rebase" for setting this on a per-branch basis.

When `merges` (or just *m*), pass the `--rebase-merges` option to *git rebase* so that the local merge commits are included in the rebase (see [git-rebase\[1\]][734] for details).

When the value is `interactive` (or just *i*), the rebase is run in interactive mode.

__NOTE__: this is a possibly dangerous operation; do __not__ use it unless you understand the implications (see [git-rebase\[1\]][735] for details).

[][736]pull.octopus

The default merge strategy to use when pulling multiple branches at once.

[][737]pull.twohead

The default merge strategy to use when pulling a single branch.

[][738]push.default

Defines the action `git push` should take if no refspec is given (whether from the command-line, config, or elsewhere). Different values are well-suited for specific workflows; for instance, in a purely central workflow (i.e. the fetch source is equal to the push destination), `upstream` is probably what you want. Possible values are:

-   `nothing` - do not push anything (error out) unless a refspec is given. This is primarily meant for people who want to avoid mistakes by always being explicit.
    
-   `current` - push the current branch to update a branch with the same name on the receiving end. Works in both central and non-central workflows.
    
-   `upstream` - push the current branch back to the branch whose changes are usually integrated into the current branch (which is called `@{upstream}`). This mode only makes sense if you are pushing to the same repository you would normally pull from (i.e. central workflow).
    
-   `tracking` - This is a deprecated synonym for `upstream`.
    
-   `simple` - pushes the current branch with the same name on the remote.
    
    If you are working on a centralized workflow (pushing to the same repository you pull from, which is typically `origin`), then you need to configure an upstream branch with the same name.
    
    This mode is the default since Git 2.0, and is the safest option suited for beginners.
    
-   `matching` - push all branches having the same name on both ends. This makes the repository you are pushing to remember the set of branches that will be pushed out (e.g. if you always push *maint* and *master* there and no other branches, the repository you push to will have these two branches, and your local *maint* and *master* will be pushed there).
    
    To use this mode effectively, you have to make sure *all* the branches you would push out are ready to be pushed out before running *git push*, as the whole point of this mode is to allow you to push all of the branches in one go. If you usually finish work on only one branch and push out the result, while other branches are unfinished, this mode is not for you. Also this mode is not suitable for pushing into a shared central repository, as other people may add new branches there, or update the tip of existing branches outside your control.
    
    This used to be the default, but not since Git 2.0 (`simple` is the new default).
    

[][739]push.followTags

If set to true enable `--follow-tags` option by default. You may override this configuration at time of push by specifying `--no-follow-tags`.

[][740]push.gpgSign

May be set to a boolean value, or the string *if-asked*. A true value causes all pushes to be GPG signed, as if `--signed` is passed to [git-push\[1\]][741]. The string *if-asked* causes pushes to be signed if the server supports it, as if `--signed=if-asked` is passed to *git push*. A false value may override a value from a lower-priority config file. An explicit command-line flag always overrides this config option.

[][742]push.pushOption

When no `--push-option=<option>` argument is given from the command line, `git push` behaves as if each <value> of this variable is given as `--push-option=<value>`.

This is a multi-valued variable, and an empty value can be used in a higher priority configuration file (e.g. `.git/config` in a repository) to clear the values inherited from a lower priority configuration files (e.g. `$HOME/.gitconfig`).

Example:

/etc/gitconfig
  push.pushoption = a
  push.pushoption = b

~/.gitconfig
  push.pushoption = c

repo/.git/config
  push.pushoption =
  push.pushoption = b

This will result in only b (a and c are cleared).

[][743]push.recurseSubmodules

Make sure all submodule commits used by the revisions to be pushed are available on a remote-tracking branch. If the value is *check* then Git will verify that all submodule commits that changed in the revisions to be pushed are available on at least one remote of the submodule. If any commits are missing, the push will be aborted and exit with non-zero status. If the value is *on-demand* then all submodules that changed in the revisions to be pushed will be pushed. If on-demand was not able to push all necessary revisions it will also be aborted and exit with non-zero status. If the value is *no* then default behavior of ignoring submodules when pushing is retained. You may override this configuration at time of push by specifying *\--recurse-submodules=check|on-demand|no*. If not set, *no* is used by default, unless *submodule.recurse* is set (in which case a *true* value means *on-demand*).

[][744]push.useForceIfIncludes

If set to "true", it is equivalent to specifying `--force-if-includes` as an option to [git-push\[1\]][745] in the command line. Adding `--no-force-if-includes` at the time of push overrides this configuration setting.

[][746]push.negotiate

If set to "true", attempt to reduce the size of the packfile sent by rounds of negotiation in which the client and the server attempt to find commits in common. If "false", Git will rely solely on the server’s ref advertisement to find commits in common.

[][747]rebase.backend

Default backend to use for rebasing. Possible choices are *apply* or *merge*. In the future, if the merge backend gains all remaining capabilities of the apply backend, this setting may become unused.

[][748]rebase.stat

Whether to show a diffstat of what changed upstream since the last rebase. False by default.

[][749]rebase.autoSquash

If set to true enable `--autosquash` option by default.

[][750]rebase.autoStash

When set to true, automatically create a temporary stash entry before the operation begins, and apply it after the operation ends. This means that you can run rebase on a dirty worktree. However, use with care: the final stash application after a successful rebase might result in non-trivial conflicts. This option can be overridden by the `--no-autostash` and `--autostash` options of [git-rebase\[1\]][751]. Defaults to false.

[][752]rebase.missingCommitsCheck

If set to "warn", git rebase -i will print a warning if some commits are removed (e.g. a line was deleted), however the rebase will still proceed. If set to "error", it will print the previous warning and stop the rebase, *git rebase --edit-todo* can then be used to correct the error. If set to "ignore", no checking is done. To drop a commit without warning or error, use the `drop` command in the todo list. Defaults to "ignore".

[][753]rebase.instructionFormat

A format string, as specified in [git-log\[1\]][754], to be used for the todo list during an interactive rebase. The format will automatically have the long commit hash prepended to the format.

[][755]rebase.abbreviateCommands

If set to true, `git rebase` will use abbreviated command names in the todo list resulting in something like this:

p deadbee The oneline of the commit
p fa1afe1 The oneline of the next commit
...

instead of:

pick deadbee The oneline of the commit
pick fa1afe1 The oneline of the next commit
...

Defaults to false.

[][756]rebase.rescheduleFailedExec

Automatically reschedule `exec` commands that failed. This only makes sense in interactive mode (or when an `--exec` option was provided). This is the same as specifying the `--reschedule-failed-exec` option.

[][757]rebase.forkPoint

If set to false set `--no-fork-point` option by default.

[][758]receive.advertiseAtomic

By default, git-receive-pack will advertise the atomic push capability to its clients. If you don’t want to advertise this capability, set this variable to false.

[][759]receive.advertisePushOptions

When set to true, git-receive-pack will advertise the push options capability to its clients. False by default.

[][760]receive.autogc

By default, git-receive-pack will run "git-gc --auto" after receiving data from git-push and updating refs. You can stop it by setting this variable to false.

[][761]receive.certNonceSeed

By setting this variable to a string, `git receive-pack` will accept a `git push --signed` and verifies it by using a "nonce" protected by HMAC using this string as a secret key.

[][762]receive.certNonceSlop

When a `git push --signed` sent a push certificate with a "nonce" that was issued by a receive-pack serving the same repository within this many seconds, export the "nonce" found in the certificate to `GIT_PUSH_CERT_NONCE` to the hooks (instead of what the receive-pack asked the sending side to include). This may allow writing checks in `pre-receive` and `post-receive` a bit easier. Instead of checking `GIT_PUSH_CERT_NONCE_SLOP` environment variable that records by how many seconds the nonce is stale to decide if they want to accept the certificate, they only can check `GIT_PUSH_CERT_NONCE_STATUS` is `OK`.

[][763]receive.fsckObjects

If it is set to true, git-receive-pack will check all received objects. See `transfer.fsckObjects` for what’s checked. Defaults to false. If not set, the value of `transfer.fsckObjects` is used instead.

[][764]receive.fsck.<msg-id>

Acts like `fsck.<msg-id>`, but is used by [git-receive-pack\[1\]][765] instead of [git-fsck\[1\]][766]. See the `fsck.<msg-id>` documentation for details.

[][767]receive.fsck.skipList

Acts like `fsck.skipList`, but is used by [git-receive-pack\[1\]][768] instead of [git-fsck\[1\]][769]. See the `fsck.skipList` documentation for details.

[][770]receive.keepAlive

After receiving the pack from the client, `receive-pack` may produce no output (if `--quiet` was specified) while processing the pack, causing some networks to drop the TCP connection. With this option set, if `receive-pack` does not transmit any data in this phase for `receive.keepAlive` seconds, it will send a short keepalive packet. The default is 5 seconds; set to 0 to disable keepalives entirely.

[][771]receive.unpackLimit

If the number of objects received in a push is below this limit then the objects will be unpacked into loose object files. However if the number of received objects equals or exceeds this limit then the received pack will be stored as a pack, after adding any missing delta bases. Storing the pack from a push can make the push operation complete faster, especially on slow filesystems. If not set, the value of `transfer.unpackLimit` is used instead.

[][772]receive.maxInputSize

If the size of the incoming pack stream is larger than this limit, then git-receive-pack will error out, instead of accepting the pack file. If not set or set to 0, then the size is unlimited.

[][773]receive.denyDeletes

If set to true, git-receive-pack will deny a ref update that deletes the ref. Use this to prevent such a ref deletion via a push.

[][774]receive.denyDeleteCurrent

If set to true, git-receive-pack will deny a ref update that deletes the currently checked out branch of a non-bare repository.

[][775]receive.denyCurrentBranch

If set to true or "refuse", git-receive-pack will deny a ref update to the currently checked out branch of a non-bare repository. Such a push is potentially dangerous because it brings the HEAD out of sync with the index and working tree. If set to "warn", print a warning of such a push to stderr, but allow the push to proceed. If set to false or "ignore", allow such pushes with no message. Defaults to "refuse".

Another option is "updateInstead" which will update the working tree if pushing into the current branch. This option is intended for synchronizing working directories when one side is not easily accessible via interactive ssh (e.g. a live web site, hence the requirement that the working directory be clean). This mode also comes in handy when developing inside a VM to test and fix code on different Operating Systems.

By default, "updateInstead" will refuse the push if the working tree or the index have any difference from the HEAD, but the `push-to-checkout` hook can be used to customize this. See [githooks\[5\]][776].

[][777]receive.denyNonFastForwards

If set to true, git-receive-pack will deny a ref update which is not a fast-forward. Use this to prevent such an update via a push, even if that push is forced. This configuration variable is set when initializing a shared repository.

[][778]receive.hideRefs

This variable is the same as `transfer.hideRefs`, but applies only to `receive-pack` (and so affects pushes, but not fetches). An attempt to update or delete a hidden ref by `git push` is rejected.

[][779]receive.procReceiveRefs

This is a multi-valued variable that defines reference prefixes to match the commands in `receive-pack`. Commands matching the prefixes will be executed by an external hook "proc-receive", instead of the internal `execute_commands` function. If this variable is not defined, the "proc-receive" hook will never be used, and all commands will be executed by the internal `execute_commands` function.

For example, if this variable is set to "refs/for", pushing to reference such as "refs/for/master" will not create or update a reference named "refs/for/master", but may create or update a pull request directly by running the hook "proc-receive".

Optional modifiers can be provided in the beginning of the value to filter commands for specific actions: create (a), modify (m), delete (d). A `!` can be included in the modifiers to negate the reference prefix entry. E.g.:

git config --system --add receive.procReceiveRefs ad:refs/heads
git config --system --add receive.procReceiveRefs !:refs/heads

[][780]receive.updateServerInfo

If set to true, git-receive-pack will run git-update-server-info after receiving data from git-push and updating refs.

[][781]receive.shallowUpdate

If set to true, .git/shallow can be updated when new refs require new shallow roots. Otherwise those refs are rejected.

[][782]remote.pushDefault

The remote to push to by default. Overrides `branch.<name>.remote` for all branches, and is overridden by `branch.<name>.pushRemote` for specific branches.

[][783]remote.<name>.url

The URL of a remote repository. See [git-fetch\[1\]][784] or [git-push\[1\]][785].

[][786]remote.<name>.pushurl

The push URL of a remote repository. See [git-push\[1\]][787].

[][788]remote.<name>.proxy

For remotes that require curl (http, https and ftp), the URL to the proxy to use for that remote. Set to the empty string to disable proxying for that remote.

[][789]remote.<name>.proxyAuthMethod

For remotes that require curl (http, https and ftp), the method to use for authenticating against the proxy in use (probably set in `remote.<name>.proxy`). See `http.proxyAuthMethod`.

[][790]remote.<name>.fetch

The default set of "refspec" for [git-fetch\[1\]][791]. See [git-fetch\[1\]][792].

[][793]remote.<name>.push

The default set of "refspec" for [git-push\[1\]][794]. See [git-push\[1\]][795].

[][796]remote.<name>.mirror

If true, pushing to this remote will automatically behave as if the `--mirror` option was given on the command line.

[][797]remote.<name>.skipDefaultUpdate

If true, this remote will be skipped by default when updating using [git-fetch\[1\]][798] or the `update` subcommand of [git-remote\[1\]][799].

[][800]remote.<name>.skipFetchAll

If true, this remote will be skipped by default when updating using [git-fetch\[1\]][801] or the `update` subcommand of [git-remote\[1\]][802].

[][803]remote.<name>.receivepack

The default program to execute on the remote side when pushing. See option --receive-pack of [git-push\[1\]][804].

[][805]remote.<name>.uploadpack

The default program to execute on the remote side when fetching. See option --upload-pack of [git-fetch-pack\[1\]][806].

[][807]remote.<name>.tagOpt

Setting this value to --no-tags disables automatic tag following when fetching from remote <name>. Setting it to --tags will fetch every tag from remote <name>, even if they are not reachable from remote branch heads. Passing these flags directly to [git-fetch\[1\]][808] can override this setting. See options --tags and --no-tags of [git-fetch\[1\]][809].

[][810]remote.<name>.vcs

Setting this to a value <vcs> will cause Git to interact with the remote with the git-remote-<vcs> helper.

[][811]remote.<name>.prune

When set to true, fetching from this remote by default will also remove any remote-tracking references that no longer exist on the remote (as if the `--prune` option was given on the command line). Overrides `fetch.prune` settings, if any.

[][812]remote.<name>.pruneTags

When set to true, fetching from this remote by default will also remove any local tags that no longer exist on the remote if pruning is activated in general via `remote.<name>.prune`, `fetch.prune` or `--prune`. Overrides `fetch.pruneTags` settings, if any.

See also `remote.<name>.prune` and the PRUNING section of [git-fetch\[1\]][813].

[][814]remote.<name>.promisor

When set to true, this remote will be used to fetch promisor objects.

[][815]remote.<name>.partialclonefilter

The filter that will be applied when fetching from this promisor remote.

[][816]remotes.<group>

The list of remotes which are fetched by "git remote update <group>". See [git-remote\[1\]][817].

[][818]repack.useDeltaBaseOffset

By default, [git-repack\[1\]][819] creates packs that use delta-base offset. If you need to share your repository with Git older than version 1.4.4, either directly or via a dumb protocol such as http, then you need to set this option to "false" and repack. Access from old Git versions over the native protocol are unaffected by this option.

[][820]repack.packKeptObjects

If set to true, makes `git repack` act as if `--pack-kept-objects` was passed. See [git-repack\[1\]][821] for details. Defaults to `false` normally, but `true` if a bitmap index is being written (either via `--write-bitmap-index` or `repack.writeBitmaps`).

[][822]repack.useDeltaIslands

If set to true, makes `git repack` act as if `--delta-islands` was passed. Defaults to `false`.

[][823]repack.writeBitmaps

When true, git will write a bitmap index when packing all objects to disk (e.g., when `git repack -a` is run). This index can speed up the "counting objects" phase of subsequent packs created for clones and fetches, at the cost of some disk space and extra time spent on the initial repack. This has no effect if multiple packfiles are created. Defaults to true on bare repos, false otherwise.

[][824]rerere.autoUpdate

When set to true, `git-rerere` updates the index with the resulting contents after it cleanly resolves conflicts using previously recorded resolution. Defaults to false.

[][825]rerere.enabled

Activate recording of resolved conflicts, so that identical conflict hunks can be resolved automatically, should they be encountered again. By default, [git-rerere\[1\]][826] is enabled if there is an `rr-cache` directory under the `$GIT_DIR`, e.g. if "rerere" was previously used in the repository.

[][827]reset.quiet

When set to true, *git reset* will default to the *\--quiet* option.

[][828]sendemail.identity

A configuration identity. When given, causes values in the *sendemail.<identity>* subsection to take precedence over values in the *sendemail* section. The default identity is the value of `sendemail.identity`.

[][829]sendemail.smtpEncryption

See [git-send-email\[1\]][830] for description. Note that this setting is not subject to the *identity* mechanism.

[][831]sendemail.smtpsslcertpath

Path to ca-certificates (either a directory or a single file). Set it to an empty string to disable certificate verification.

[][832]sendemail.<identity>.\*

Identity-specific versions of the *sendemail.\** parameters found below, taking precedence over those when this identity is selected, through either the command-line or `sendemail.identity`.

[][833]sendemail.aliasesFile

[][834]sendemail.aliasFileType

[][835]sendemail.annotate

[][836]sendemail.bcc

[][837]sendemail.cc

[][838]sendemail.ccCmd

[][839]sendemail.chainReplyTo

[][840]sendemail.confirm

[][841]sendemail.envelopeSender

[][842]sendemail.from

[][843]sendemail.multiEdit

[][844]sendemail.signedoffbycc

[][845]sendemail.smtpPass

[][846]sendemail.suppresscc

[][847]sendemail.suppressFrom

[][848]sendemail.to

[][849]sendemail.tocmd

[][850]sendemail.smtpDomain

[][851]sendemail.smtpServer

[][852]sendemail.smtpServerPort

[][853]sendemail.smtpServerOption

[][854]sendemail.smtpUser

[][855]sendemail.thread

[][856]sendemail.transferEncoding

[][857]sendemail.validate

[][858]sendemail.xmailer

See [git-send-email\[1\]][859] for description.

[][860]sendemail.signedoffcc (deprecated)

Deprecated alias for `sendemail.signedoffbycc`.

[][861]sendemail.smtpBatchSize

Number of messages to be sent per connection, after that a relogin will happen. If the value is 0 or undefined, send all messages in one connection. See also the `--batch-size` option of [git-send-email\[1\]][862].

[][863]sendemail.smtpReloginDelay

Seconds wait before reconnecting to smtp server. See also the `--relogin-delay` option of [git-send-email\[1\]][864].

[][865]sendemail.forbidSendmailVariables

To avoid common misconfiguration mistakes, [git-send-email\[1\]][866] will abort with a warning if any configuration options for "sendmail" exist. Set this variable to bypass the check.

[][867]sequence.editor

Text editor used by `git rebase -i` for editing the rebase instruction file. The value is meant to be interpreted by the shell when it is used. It can be overridden by the `GIT_SEQUENCE_EDITOR` environment variable. When not configured the default commit message editor is used instead.

[][868]showBranch.default

The default set of branches for [git-show-branch\[1\]][869]. See [git-show-branch\[1\]][870].

[][871]splitIndex.maxPercentChange

When the split index feature is used, this specifies the percent of entries the split index can contain compared to the total number of entries in both the split index and the shared index before a new shared index is written. The value should be between 0 and 100. If the value is 0 then a new shared index is always written, if it is 100 a new shared index is never written. By default the value is 20, so a new shared index is written if the number of entries in the split index would be greater than 20 percent of the total number of entries. See [git-update-index\[1\]][872].

[][873]splitIndex.sharedIndexExpire

When the split index feature is used, shared index files that were not modified since the time this variable specifies will be removed when a new shared index file is created. The value "now" expires all entries immediately, and "never" suppresses expiration altogether. The default value is "2.weeks.ago". Note that a shared index file is considered modified (for the purpose of expiration) each time a new split-index file is either created based on it or read from it. See [git-update-index\[1\]][874].

[][875]ssh.variant

By default, Git determines the command line arguments to use based on the basename of the configured SSH command (configured using the environment variable `GIT_SSH` or `GIT_SSH_COMMAND` or the config setting `core.sshCommand`). If the basename is unrecognized, Git will attempt to detect support of OpenSSH options by first invoking the configured SSH command with the `-G` (print configuration) option and will subsequently use OpenSSH options (if that is successful) or no options besides the host and remote command (if it fails).

The config variable `ssh.variant` can be set to override this detection. Valid values are `ssh` (to use OpenSSH options), `plink`, `putty`, `tortoiseplink`, `simple` (no options except the host and remote command). The default auto-detection can be explicitly requested using the value `auto`. Any other value is treated as `ssh`. This setting can also be overridden via the environment variable `GIT_SSH_VARIANT`.

The current command-line parameters used for each variant are as follows:

-   `ssh` - \[-p port\] \[-4\] \[-6\] \[-o option\] \[username@\]host command
    
-   `simple` - \[username@\]host command
    
-   `plink` or `putty` - \[-P port\] \[-4\] \[-6\] \[username@\]host command
    
-   `tortoiseplink` - \[-P port\] \[-4\] \[-6\] -batch \[username@\]host command
    

Except for the `simple` variant, command-line parameters are likely to change as git gains new features.

[][876]status.relativePaths

By default, [git-status\[1\]][877] shows paths relative to the current directory. Setting this variable to `false` shows paths relative to the repository root (this was the default for Git prior to v1.5.4).

[][878]status.short

Set to true to enable --short by default in [git-status\[1\]][879]. The option --no-short takes precedence over this variable.

[][880]status.branch

Set to true to enable --branch by default in [git-status\[1\]][881]. The option --no-branch takes precedence over this variable.

[][882]status.aheadBehind

Set to true to enable `--ahead-behind` and false to enable `--no-ahead-behind` by default in [git-status\[1\]][883] for non-porcelain status formats. Defaults to true.

If set to true, [git-status\[1\]][884] will insert a comment prefix before each output line (starting with `core.commentChar`, i.e. `#` by default). This was the behavior of [git-status\[1\]][885] in Git 1.8.4 and previous. Defaults to false.

[][886]status.renameLimit

The number of files to consider when performing rename detection in [git-status\[1\]][887] and [git-commit\[1\]][888]. Defaults to the value of diff.renameLimit.

[][889]status.renames

Whether and how Git detects renames in [git-status\[1\]][890] and [git-commit\[1\]][891] . If set to "false", rename detection is disabled. If set to "true", basic rename detection is enabled. If set to "copies" or "copy", Git will detect copies, as well. Defaults to the value of diff.renames.

[][892]status.showStash

If set to true, [git-status\[1\]][893] will display the number of entries currently stashed away. Defaults to false.

[][894]status.showUntrackedFiles

By default, [git-status\[1\]][895] and [git-commit\[1\]][896] show files which are not currently tracked by Git. Directories which contain only untracked files, are shown with the directory name only. Showing untracked files means that Git needs to lstat() all the files in the whole repository, which might be slow on some systems. So, this variable controls how the commands displays the untracked files. Possible values are:

-   `no` - Show no untracked files.
    
-   `normal` - Show untracked files and directories.
    
-   `all` - Show also individual files in untracked directories.
    

If this variable is not specified, it defaults to *normal*. This variable can be overridden with the -u|--untracked-files option of [git-status\[1\]][897] and [git-commit\[1\]][898].

[][899]status.submoduleSummary

Defaults to false. If this is set to a non zero number or true (identical to -1 or an unlimited number), the submodule summary will be enabled and a summary of commits for modified submodules will be shown (see --summary-limit option of [git-submodule\[1\]][900]). Please note that the summary output command will be suppressed for all submodules when `diff.ignoreSubmodules` is set to *all* or only for those submodules where `submodule.<name>.ignore=all`. The only exception to that rule is that status and commit will show staged submodule changes. To also view the summary for ignored submodules you can either use the --ignore-submodules=dirty command-line option or the *git submodule summary* command, which shows a similar output but does not honor these settings.

[][901]stash.useBuiltin

Unused configuration variable. Used in Git versions 2.22 to 2.26 as an escape hatch to enable the legacy shellscript implementation of stash. Now the built-in rewrite of it in C is always used. Setting this will emit a warning, to alert any remaining users that setting this now does nothing.

[][902]stash.showIncludeUntracked

If this is set to true, the `git stash show` command will show the untracked files of a stash entry. Defaults to false. See description of *show* command in [git-stash\[1\]][903].

[][904]stash.showPatch

If this is set to true, the `git stash show` command without an option will show the stash entry in patch form. Defaults to false. See description of *show* command in [git-stash\[1\]][905].

[][906]stash.showStat

If this is set to true, the `git stash show` command without an option will show diffstat of the stash entry. Defaults to true. See description of *show* command in [git-stash\[1\]][907].

[][908]submodule.<name>.url

The URL for a submodule. This variable is copied from the .gitmodules file to the git config via *git submodule init*. The user can change the configured URL before obtaining the submodule via *git submodule update*. If neither submodule.<name>.active or submodule.active are set, the presence of this variable is used as a fallback to indicate whether the submodule is of interest to git commands. See [git-submodule\[1\]][909] and [gitmodules\[5\]][910] for details.

[][911]submodule.<name>.update

The method by which a submodule is updated by *git submodule update*, which is the only affected command, others such as *git checkout --recurse-submodules* are unaffected. It exists for historical reasons, when *git submodule* was the only command to interact with submodules; settings like `submodule.active` and `pull.rebase` are more specific. It is populated by `git submodule init` from the [gitmodules\[5\]][912] file. See description of *update* command in [git-submodule\[1\]][913].

[][914]submodule.<name>.branch

The remote branch name for a submodule, used by `git submodule update --remote`. Set this option to override the value found in the `.gitmodules` file. See [git-submodule\[1\]][915] and [gitmodules\[5\]][916] for details.

[][917]submodule.<name>.fetchRecurseSubmodules

This option can be used to control recursive fetching of this submodule. It can be overridden by using the --\[no-\]recurse-submodules command-line option to "git fetch" and "git pull". This setting will override that from in the [gitmodules\[5\]][918] file.

[][919]submodule.<name>.ignore

Defines under what circumstances "git status" and the diff family show a submodule as modified. When set to "all", it will never be considered modified (but it will nonetheless show up in the output of status and commit when it has been staged), "dirty" will ignore all changes to the submodules work tree and takes only differences between the HEAD of the submodule and the commit recorded in the superproject into account. "untracked" will additionally let submodules with modified tracked files in their work tree show up. Using "none" (the default when this option is not set) also shows submodules that have untracked files in their work tree as changed. This setting overrides any setting made in .gitmodules for this submodule, both settings can be overridden on the command line by using the "--ignore-submodules" option. The *git submodule* commands are not affected by this setting.

[][920]submodule.<name>.active

Boolean value indicating if the submodule is of interest to git commands. This config option takes precedence over the submodule.active config option. See [gitsubmodules\[7\]][921] for details.

[][922]submodule.active

A repeated field which contains a pathspec used to match against a submodule’s path to determine if the submodule is of interest to git commands. See [gitsubmodules\[7\]][923] for details.

[][924]submodule.recurse

A boolean indicating if commands should enable the `--recurse-submodules` option by default. Applies to all commands that support this option (`checkout`, `fetch`, `grep`, `pull`, `push`, `read-tree`, `reset`, `restore` and `switch`) except `clone` and `ls-files`. Defaults to false. When set to true, it can be deactivated via the `--no-recurse-submodules` option. Note that some Git commands lacking this option may call some of the above commands affected by `submodule.recurse`; for instance `git remote update` will call `git fetch` but does not have a `--no-recurse-submodules` option. For these commands a workaround is to temporarily change the configuration value by using `git -c submodule.recurse=0`.

[][925]submodule.fetchJobs

Specifies how many submodules are fetched/cloned at the same time. A positive integer allows up to that number of submodules fetched in parallel. A value of 0 will give some reasonable default. If unset, it defaults to 1.

[][926]submodule.alternateLocation

Specifies how the submodules obtain alternates when submodules are cloned. Possible values are `no`, `superproject`. By default `no` is assumed, which doesn’t add references. When the value is set to `superproject` the submodule to be cloned computes its alternates location relative to the superprojects alternate.

[][927]submodule.alternateErrorStrategy

Specifies how to treat errors with the alternates for a submodule as computed via `submodule.alternateLocation`. Possible values are `ignore`, `info`, `die`. Default is `die`. Note that if set to `ignore` or `info`, and if there is an error with the computed alternate, the clone proceeds as if no alternate was specified.

[][928]tag.forceSignAnnotated

A boolean to specify whether annotated tags created should be GPG signed. If `--annotate` is specified on the command line, it takes precedence over this option.

[][929]tag.sort

This variable controls the sort ordering of tags when displayed by [git-tag\[1\]][930]. Without the "--sort=<value>" option provided, the value of this variable will be used as the default.

[][931]tag.gpgSign

A boolean to specify whether all tags should be GPG signed. Use of this option when running in an automated script can result in a large number of tags being signed. It is therefore convenient to use an agent to avoid typing your gpg passphrase several times. Note that this option doesn’t affect tag signing behavior enabled by "-u <keyid>" or "--local-user=<keyid>" options.

[][932]tar.umask

This variable can be used to restrict the permission bits of tar archive entries. The default is 0002, which turns off the world write bit. The special value "user" indicates that the archiving user’s umask will be used instead. See umask(2) and [git-archive\[1\]][933].

Trace2 config settings are only read from the system and global config files; repository local and worktree config files and `-c` command line arguments are not respected.

[][934]trace2.normalTarget

This variable controls the normal target destination. It may be overridden by the `GIT_TRACE2` environment variable. The following table shows possible values.

[][935]trace2.perfTarget

This variable controls the performance target destination. It may be overridden by the `GIT_TRACE2_PERF` environment variable. The following table shows possible values.

[][936]trace2.eventTarget

This variable controls the event target destination. It may be overridden by the `GIT_TRACE2_EVENT` environment variable. The following table shows possible values.

-   `0` or `false` - Disables the target.
    
-   `1` or `true` - Writes to `STDERR`.
    
-   `[2-9]` - Writes to the already opened file descriptor.
    
-   `<absolute-pathname>` - Writes to the file in append mode. If the target already exists and is a directory, the traces will be written to files (one per process) underneath the given directory.
    
-   `af_unix:[<socket_type>:]<absolute-pathname>` - Write to a Unix DomainSocket (on platforms that support them). Socket type can be either `stream` or `dgram`; if omitted Git will try both.
    

[][937]trace2.normalBrief

Boolean. When true `time`, `filename`, and `line` fields are omitted from normal output. May be overridden by the `GIT_TRACE2_BRIEF` environment variable. Defaults to false.

[][938]trace2.perfBrief

Boolean. When true `time`, `filename`, and `line` fields are omitted from PERF output. May be overridden by the `GIT_TRACE2_PERF_BRIEF` environment variable. Defaults to false.

[][939]trace2.eventBrief

Boolean. When true `time`, `filename`, and `line` fields are omitted from event output. May be overridden by the `GIT_TRACE2_EVENT_BRIEF` environment variable. Defaults to false.

[][940]trace2.eventNesting

Integer. Specifies desired depth of nested regions in the event output. Regions deeper than this value will be omitted. May be overridden by the `GIT_TRACE2_EVENT_NESTING` environment variable. Defaults to 2.

[][941]trace2.configParams

A comma-separated list of patterns of "important" config settings that should be recorded in the trace2 output. For example, `core.*,remote.*.url` would cause the trace2 output to contain events listing each configured remote. May be overridden by the `GIT_TRACE2_CONFIG_PARAMS` environment variable. Unset by default.

[][942]trace2.envVars

A comma-separated list of "important" environment variables that should be recorded in the trace2 output. For example, `GIT_HTTP_USER_AGENT,GIT_CONFIG` would cause the trace2 output to contain events listing the overrides for HTTP user agent and the location of the Git configuration file (assuming any are set). May be overridden by the `GIT_TRACE2_ENV_VARS` environment variable. Unset by default.

[][943]trace2.destinationDebug

Boolean. When true Git will print error messages when a trace target destination cannot be opened for writing. By default, these errors are suppressed and tracing is silently disabled. May be overridden by the `GIT_TRACE2_DST_DEBUG` environment variable.

[][944]trace2.maxFiles

Integer. When writing trace files to a target directory, do not write additional traces if we would exceed this many files. Instead, write a sentinel file that will block further tracing to this directory. Defaults to 0, which disables this check.

[][945]transfer.fsckObjects

When `fetch.fsckObjects` or `receive.fsckObjects` are not set, the value of this variable is used instead. Defaults to false.

When set, the fetch or receive will abort in the case of a malformed object or a link to a nonexistent object. In addition, various other issues are checked for, including legacy issues (see `fsck.<msg-id>`), and potential security issues like the existence of a `.GIT` directory or a malicious `.gitmodules` file (see the release notes for v2.2.1 and v2.17.1 for details). Other sanity and security checks may be added in future releases.

On the receiving side, failing fsckObjects will make those objects unreachable, see "QUARANTINE ENVIRONMENT" in [git-receive-pack\[1\]][946]. On the fetch side, malformed objects will instead be left unreferenced in the repository.

Due to the non-quarantine nature of the `fetch.fsckObjects` implementation it cannot be relied upon to leave the object store clean like `receive.fsckObjects` can.

As objects are unpacked they’re written to the object store, so there can be cases where malicious objects get introduced even though the "fetch" failed, only to have a subsequent "fetch" succeed because only new incoming objects are checked, not those that have already been written to the object store. That difference in behavior should not be relied upon. In the future, such objects may be quarantined for "fetch" as well.

For now, the paranoid need to find some way to emulate the quarantine environment if they’d like the same protection as "push". E.g. in the case of an internal mirror do the mirroring in two steps, one to fetch the untrusted objects, and then do a second "push" (which will use the quarantine) to another internal repo, and have internal clients consume this pushed-to repository, or embargo internal fetches and only allow them once a full "fsck" has run (and no new fetches have happened in the meantime).

[][947]transfer.hideRefs

String(s) `receive-pack` and `upload-pack` use to decide which refs to omit from their initial advertisements. Use more than one definition to specify multiple prefix strings. A ref that is under the hierarchies listed in the value of this variable is excluded, and is hidden when responding to `git push` or `git fetch`. See `receive.hideRefs` and `uploadpack.hideRefs` for program-specific versions of this config.

You may also include a `!` in front of the ref name to negate the entry, explicitly exposing it, even if an earlier entry marked it as hidden. If you have multiple hideRefs values, later entries override earlier ones (and entries in more-specific config files override less-specific ones).

If a namespace is in use, the namespace prefix is stripped from each reference before it is matched against `transfer.hiderefs` patterns. In order to match refs before stripping, add a `^` in front of the ref name. If you combine `!` and `^`, `!` must be specified first.

For example, if `refs/heads/master` is specified in `transfer.hideRefs` and the current namespace is `foo`, then `refs/namespaces/foo/refs/heads/master` is omitted from the advertisements. If `uploadpack.allowRefInWant` is set, `upload-pack` will treat `want-ref refs/heads/master` in a protocol v2 `fetch` command as if `refs/namespaces/foo/refs/heads/master` did not exist. `receive-pack`, on the other hand, will still advertise the object id the ref is pointing to without mentioning its name (a so-called ".have" line).

Even if you hide refs, a client may still be able to steal the target objects via the techniques described in the "SECURITY" section of the [gitnamespaces\[7\]][948] man page; it’s best to keep private data in a separate repository.

[][949]transfer.unpackLimit

When `fetch.unpackLimit` or `receive.unpackLimit` are not set, the value of this variable is used instead. The default value is 100.

[][950]transfer.advertiseSID

Boolean. When true, client and server processes will advertise their unique session IDs to their remote counterpart. Defaults to false.

[][951]uploadarchive.allowUnreachable

If true, allow clients to use `git archive --remote` to request any tree, whether reachable from the ref tips or not. See the discussion in the "SECURITY" section of [git-upload-archive\[1\]][952] for more details. Defaults to `false`.

[][953]uploadpack.hideRefs

This variable is the same as `transfer.hideRefs`, but applies only to `upload-pack` (and so affects only fetches, not pushes). An attempt to fetch a hidden ref by `git fetch` will fail. See also `uploadpack.allowTipSHA1InWant`.

[][954]uploadpack.allowTipSHA1InWant

When `uploadpack.hideRefs` is in effect, allow `upload-pack` to accept a fetch request that asks for an object at the tip of a hidden ref (by default, such a request is rejected). See also `uploadpack.hideRefs`. Even if this is false, a client may be able to steal objects via the techniques described in the "SECURITY" section of the [gitnamespaces\[7\]][955] man page; it’s best to keep private data in a separate repository.

[][956]uploadpack.allowReachableSHA1InWant

Allow `upload-pack` to accept a fetch request that asks for an object that is reachable from any ref tip. However, note that calculating object reachability is computationally expensive. Defaults to `false`. Even if this is false, a client may be able to steal objects via the techniques described in the "SECURITY" section of the [gitnamespaces\[7\]][957] man page; it’s best to keep private data in a separate repository.

[][958]uploadpack.allowAnySHA1InWant

Allow `upload-pack` to accept a fetch request that asks for any object at all. Defaults to `false`.

[][959]uploadpack.keepAlive

When `upload-pack` has started `pack-objects`, there may be a quiet period while `pack-objects` prepares the pack. Normally it would output progress information, but if `--quiet` was used for the fetch, `pack-objects` will output nothing at all until the pack data begins. Some clients and networks may consider the server to be hung and give up. Setting this option instructs `upload-pack` to send an empty keepalive packet every `uploadpack.keepAlive` seconds. Setting this option to 0 disables keepalive packets entirely. The default is 5 seconds.

[][960]uploadpack.packObjectsHook

If this option is set, when `upload-pack` would run `git pack-objects` to create a packfile for a client, it will run this shell command instead. The `pack-objects` command and arguments it *would* have run (including the `git pack-objects` at the beginning) are appended to the shell command. The stdin and stdout of the hook are treated as if `pack-objects` itself was run. I.e., `upload-pack` will feed input intended for `pack-objects` to the hook, and expects a completed packfile on stdout.

Note that this configuration variable is ignored if it is seen in the repository-level config (this is a safety measure against fetching from untrusted repositories).

[][961]uploadpack.allowFilter

If this option is set, `upload-pack` will support partial clone and partial fetch object filtering.

[][962]uploadpackfilter.allow

Provides a default value for unspecified object filters (see: the below configuration variable). If set to `true`, this will also enable all filters which get added in the future. Defaults to `true`.

[][963]uploadpackfilter.<filter>.allow

Explicitly allow or ban the object filter corresponding to `<filter>`, where `<filter>` may be one of: `blob:none`, `blob:limit`, `object:type`, `tree`, `sparse:oid`, or `combine`. If using combined filters, both `combine` and all of the nested filter kinds must be allowed. Defaults to `uploadpackfilter.allow`.

[][964]uploadpackfilter.tree.maxDepth

Only allow `--filter=tree:<n>` when `<n>` is no more than the value of `uploadpackfilter.tree.maxDepth`. If set, this also implies `uploadpackfilter.tree.allow=true`, unless this configuration variable had already been set. Has no effect if unset.

[][965]uploadpack.allowRefInWant

If this option is set, `upload-pack` will support the `ref-in-want` feature of the protocol version 2 `fetch` command. This feature is intended for the benefit of load-balanced servers which may not have the same view of what OIDs their refs point to due to replication delay.

[][966]url.<base>.insteadOf

Any URL that starts with this value will be rewritten to start, instead, with <base>. In cases where some site serves a large number of repositories, and serves them with multiple access methods, and some users need to use different access methods, this feature allows people to specify any of the equivalent URLs and have Git automatically rewrite the URL to the best alternative for the particular user, even for a never-before-seen repository on the site. When more than one insteadOf strings match a given URL, the longest match is used.

Note that any protocol restrictions will be applied to the rewritten URL. If the rewrite changes the URL to use a custom protocol or remote helper, you may need to adjust the `protocol.*.allow` config to permit the request. In particular, protocols you expect to use for submodules must be set to `always` rather than the default of `user`. See the description of `protocol.allow` above.

[][967]url.<base>.pushInsteadOf

Any URL that starts with this value will not be pushed to; instead, it will be rewritten to start with <base>, and the resulting URL will be pushed to. In cases where some site serves a large number of repositories, and serves them with multiple access methods, some of which do not allow push, this feature allows people to specify a pull-only URL and have Git automatically use an appropriate URL to push, even for a never-before-seen repository on the site. When more than one pushInsteadOf strings match a given URL, the longest match is used. If a remote has an explicit pushurl, Git will ignore this setting for that remote.

[][968]user.name

[][969]user.email

[][970]author.email

[][971]committer.name

[][972]committer.email

The `user.name` and `user.email` variables determine what ends up in the `author` and `committer` field of commit objects. If you need the `author` or `committer` to be different, the `author.name`, `author.email`, `committer.name` or `committer.email` variables can be set. Also, all of these can be overridden by the `GIT_AUTHOR_NAME`, `GIT_AUTHOR_EMAIL`, `GIT_COMMITTER_NAME`, `GIT_COMMITTER_EMAIL` and `EMAIL` environment variables.

Note that the `name` forms of these variables conventionally refer to some form of a personal name. See [git-commit\[1\]][973] and the environment variables section of [git\[1\]][974] for more information on these settings and the `credential.username` option if you’re looking for authentication credentials instead.

[][975]user.useConfigOnly

Instruct Git to avoid trying to guess defaults for `user.email` and `user.name`, and instead retrieve the values only from the configuration. For example, if you have multiple email addresses and would like to use a different one for each repository, then with this configuration option set to `true` in the global config along with a name, Git will prompt you to set up an email before making new commits in a newly cloned repository. Defaults to `false`.

[][976]user.signingKey

If [git-tag\[1\]][977] or [git-commit\[1\]][978] is not selecting the key you want it to automatically when creating a signed tag or commit, you can override the default selection with this variable. This option is passed unchanged to gpg’s --local-user parameter, so you may specify a key using any method that gpg supports. If gpg.format is set to "ssh" this can contain the literal ssh public key (e.g.: "ssh-rsa XXXXXX identifier") or a file which contains it and corresponds to the private key used for signing. The private key needs to be available via ssh-agent. Alternatively it can be set to a file containing a private key directly. If not set git will call gpg.ssh.defaultKeyCommand (e.g.: "ssh-add -L") and try to use the first key available.

[][979]versionsort.prereleaseSuffix (deprecated)

Deprecated alias for `versionsort.suffix`. Ignored if `versionsort.suffix` is set.

[][980]versionsort.suffix

Even when version sort is used in [git-tag\[1\]][981], tagnames with the same base version but different suffixes are still sorted lexicographically, resulting e.g. in prerelease tags appearing after the main release (e.g. "1.0-rc1" after "1.0"). This variable can be specified to determine the sorting order of tags with different suffixes.

By specifying a single suffix in this variable, any tagname containing that suffix will appear before the corresponding main release. E.g. if the variable is set to "-rc", then all "1.0-rcX" tags will appear before "1.0". If specified multiple times, once per suffix, then the order of suffixes in the configuration will determine the sorting order of tagnames with those suffixes. E.g. if "-pre" appears before "-rc" in the configuration, then all "1.0-preX" tags will be listed before any "1.0-rcX" tags. The placement of the main release tag relative to tags with various suffixes can be determined by specifying the empty suffix among those other suffixes. E.g. if the suffixes "-rc", "", "-ck" and "-bfs" appear in the configuration in this order, then all "v4.8-rcX" tags are listed first, followed by "v4.8", then "v4.8-ckX" and finally "v4.8-bfsX".

If more than one suffixes match the same tagname, then that tagname will be sorted according to the suffix which starts at the earliest position in the tagname. If more than one different matching suffixes start at that earliest position, then that tagname will be sorted according to the longest of those suffixes. The sorting order between different suffixes is undefined if they are in multiple config files.

[][982]web.browser

Specify a web browser that may be used by some commands. Currently only [git-instaweb\[1\]][983] and [git-help\[1\]][984] may use it.

[][985]worktree.guessRemote

If no branch is specified and neither `-b` nor `-B` nor `--detach` is used, then `git worktree add` defaults to creating a new branch from HEAD. If `worktree.guessRemote` is set to true, `worktree add` tries to find a remote-tracking branch whose name uniquely matches the new branch name. If such a branch exists, it is checked out and set as "upstream" for the new branch. If no such match can be found, it falls back to creating a new branch from the current HEAD.

[1]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-advice
[2]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchShowForcedUpdates
[3]: https://www.git-scm.com/docs/git-fetch
[4]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushUpdateRejected
[5]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushNonFFCurrent
[6]: https://www.git-scm.com/docs/git-push
[7]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushNonFFMatching
[8]: https://www.git-scm.com/docs/git-push
[9]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushAlreadyExists
[10]: https://www.git-scm.com/docs/git-push
[11]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushFetchFirst
[12]: https://www.git-scm.com/docs/git-push
[13]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushNeedsForce
[14]: https://www.git-scm.com/docs/git-push
[15]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushUnqualifiedRefname
[16]: https://www.git-scm.com/docs/git-push
[17]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushRefNeedsUpdate
[18]: https://www.git-scm.com/docs/git-push
[19]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-skippedCherryPicks
[20]: https://www.git-scm.com/docs/git-rebase
[21]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusAheadBehind
[22]: https://www.git-scm.com/docs/git-status
[23]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusHints
[24]: https://www.git-scm.com/docs/git-status
[25]: https://www.git-scm.com/docs/git-commit
[26]: https://www.git-scm.com/docs/git-switch
[27]: https://www.git-scm.com/docs/git-checkout
[28]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusUoption
[29]: https://www.git-scm.com/docs/git-status
[30]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitBeforeMerge
[31]: https://www.git-scm.com/docs/git-merge
[32]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-resetQuiet
[33]: https://www.git-scm.com/docs/git-reset
[34]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-resolveConflict
[35]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sequencerInUse
[36]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-implicitIdentity
[37]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-detachedHead
[38]: https://www.git-scm.com/docs/git-switch
[39]: https://www.git-scm.com/docs/git-checkout
[40]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-checkoutAmbiguousRemoteBranchName
[41]: https://www.git-scm.com/docs/git-checkout
[42]: https://www.git-scm.com/docs/git-switch
[43]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-amWorkDir
[44]: https://www.git-scm.com/docs/git-am
[45]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rmHints
[46]: https://www.git-scm.com/docs/git-rm
[47]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addEmbeddedRepo
[48]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-ignoredHook
[49]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-waitingForEditor
[50]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-nestedTag
[51]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleAlternateErrorStrategyDie
[52]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addIgnoredFile
[53]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addEmptyPathspec
[54]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-updateSparsePath
[55]: https://www.git-scm.com/docs/git-add
[56]: https://www.git-scm.com/docs/git-rm
[57]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corefileMode
[58]: https://www.git-scm.com/docs/git-clone
[59]: https://www.git-scm.com/docs/git-init
[60]: https://www.git-scm.com/docs/git-update-index
[61]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corehideDotFiles
[62]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreignoreCase
[63]: https://www.git-scm.com/docs/git-clone
[64]: https://www.git-scm.com/docs/git-init
[65]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreprecomposeUnicode
[66]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreprotectHFS
[67]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreprotectNTFS
[68]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corefsmonitor
[69]: https://www.git-scm.com/docs/githooks
[70]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corefsmonitorHookVersion
[71]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coretrustctime
[72]: https://www.git-scm.com/docs/git-update-index
[73]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresplitIndex
[74]: https://www.git-scm.com/docs/git-update-index
[75]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreuntrackedCache
[76]: https://www.git-scm.com/docs/git-update-index
[77]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corecheckStat
[78]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corequotePath
[79]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreeol
[80]: https://www.git-scm.com/docs/gitattributes
[81]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresafecrlf
[82]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreautocrlf
[83]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corecheckRoundtripEncoding
[84]: https://www.git-scm.com/docs/gitattributes
[85]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresymlinks
[86]: https://www.git-scm.com/docs/git-update-index
[87]: https://www.git-scm.com/docs/git-add
[88]: https://www.git-scm.com/docs/git-clone
[89]: https://www.git-scm.com/docs/git-init
[90]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coregitProxy
[91]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresshCommand
[92]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreignoreStat
[93]: https://www.git-scm.com/docs/git-update-index
[94]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corepreferSymlinkRefs
[95]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corealternateRefsCommand
[96]: https://www.git-scm.com/docs/git-for-each-ref
[97]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corealternateRefsPrefixes
[98]: https://www.git-scm.com/docs/git-for-each-ref
[99]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corebare
[100]: https://www.git-scm.com/docs/git-add
[101]: https://www.git-scm.com/docs/git-merge
[102]: https://www.git-scm.com/docs/git-clone
[103]: https://www.git-scm.com/docs/git-init
[104]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreworktree
[105]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corelogAllRefUpdates
[106]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corerepositoryFormatVersion
[107]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresharedRepository
[108]: https://www.git-scm.com/docs/git-init
[109]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corewarnAmbiguousRefs
[110]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corecompression
[111]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corelooseCompression
[112]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corepackedGitWindowSize
[113]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corepackedGitLimit
[114]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coredeltaBaseCacheLimit
[115]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corebigFileThreshold
[116]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreexcludesFile
[117]: https://www.git-scm.com/docs/gitignore
[118]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreaskPass
[119]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreattributesFile
[120]: https://www.git-scm.com/docs/gitattributes
[121]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corehooksPath
[122]: https://www.git-scm.com/docs/githooks
[123]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreeditor
[124]: https://www.git-scm.com/docs/git-var
[125]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corefilesRefLockTimeout
[126]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corepackedRefsTimeout
[127]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corewhitespace
[128]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corefsyncObjectFiles
[129]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corepreloadIndex
[130]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreunsetenvvars
[131]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corerestrictinheritedhandles
[132]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corecreateObject
[133]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corenotesRef
[134]: https://www.git-scm.com/docs/git-notes
[135]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-corecommitGraph
[136]: https://www.git-scm.com/docs/git-commit-graph
[137]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreuseReplaceRefs
[138]: https://www.git-scm.com/docs/git
[139]: https://www.git-scm.com/docs/git-replace
[140]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coremultiPackIndex
[141]: https://www.git-scm.com/docs/git-multi-pack-index
[142]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresparseCheckout
[143]: https://www.git-scm.com/docs/git-sparse-checkout
[144]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coresparseCheckoutCone
[145]: https://www.git-scm.com/docs/git-sparse-checkout
[146]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coreabbrev
[147]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addignoreErrors
[148]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addignore-errorsdeprecated
[149]: https://www.git-scm.com/docs/git-add
[150]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-addinteractiveuseBuiltin
[151]: https://www.git-scm.com/docs/git-add
[152]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-alias
[153]: https://www.git-scm.com/docs/git
[154]: https://www.git-scm.com/docs/git-rev-parse
[155]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-amkeepcr
[156]: https://www.git-scm.com/docs/git-am
[157]: https://www.git-scm.com/docs/git-mailsplit
[158]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-amthreeWay
[159]: https://www.git-scm.com/docs/git-am
[160]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-applyignoreWhitespace
[161]: https://www.git-scm.com/docs/git-apply
[162]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-applywhitespace
[163]: https://www.git-scm.com/docs/git-apply
[164]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blameblankBoundary
[165]: https://www.git-scm.com/docs/git-blame
[166]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blamecoloring
[167]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blamedate
[168]: https://www.git-scm.com/docs/git-blame
[169]: https://www.git-scm.com/docs/git-log
[170]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blameshowEmail
[171]: https://www.git-scm.com/docs/git-blame
[172]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blameshowRoot
[173]: https://www.git-scm.com/docs/git-blame
[174]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blameignoreRevsFile
[175]: https://www.git-scm.com/docs/git-blame
[176]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blamemarkUnblamableLines
[177]: https://www.git-scm.com/docs/git-blame
[178]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-blamemarkIgnoredLines
[179]: https://www.git-scm.com/docs/git-blame
[180]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchautoSetupMerge
[181]: https://www.git-scm.com/docs/git-pull
[182]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchautoSetupRebase
[183]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchsort
[184]: https://www.git-scm.com/docs/git-branch
[185]: https://www.git-scm.com/docs/git-for-each-ref
[186]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtremote
[187]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtpushRemote
[188]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtmerge
[189]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtmergeOptions
[190]: https://www.git-scm.com/docs/git-merge
[191]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtrebase
[192]: https://www.git-scm.com/docs/git-rebase
[193]: https://www.git-scm.com/docs/git-rebase
[194]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-branchltnamegtdescription
[195]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-browserlttoolgtcmd
[196]: https://www.git-scm.com/docs/git-web--browse
[197]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-browserlttoolgtpath
[198]: https://www.git-scm.com/docs/git-help
[199]: https://www.git-scm.com/docs/git-instaweb
[200]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-checkoutdefaultRemote
[201]: https://www.git-scm.com/docs/git-switch
[202]: https://www.git-scm.com/docs/git-checkout
[203]: https://www.git-scm.com/docs/git-worktree
[204]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-checkoutguess
[205]: https://www.git-scm.com/docs/git-switch
[206]: https://www.git-scm.com/docs/git-checkout
[207]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-checkoutworkers
[208]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-checkoutthresholdForParallelism
[209]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-cleanrequireForce
[210]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-clonedefaultRemoteName
[211]: https://www.git-scm.com/docs/git-clone
[212]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-clonerejectShallow
[213]: https://www.git-scm.com/docs/git-clone
[214]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coloradvice
[215]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coloradvicehint
[216]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorblamehighlightRecent
[217]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorblamerepeatedLines
[218]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorbranch
[219]: https://www.git-scm.com/docs/git-branch
[220]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorbranchltslotgt
[221]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colordiff
[222]: https://www.git-scm.com/docs/git-diff
[223]: https://www.git-scm.com/docs/git-log
[224]: https://www.git-scm.com/docs/git-show
[225]: https://www.git-scm.com/docs/git-format-patch
[226]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colordiffltslotgt
[227]: https://www.git-scm.com/docs/git-diff
[228]: https://www.git-scm.com/docs/git-range-diff
[229]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colordecorateltslotgt
[230]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorgrep
[231]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorgrepltslotgt
[232]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codecontextcode
[233]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codefilenamecode
[234]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codefunctioncode
[235]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codelineNumbercode
[236]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codecolumncode
[237]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codematchcode
[238]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codematchContextcode
[239]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codematchSelectedcode
[240]: https://www.git-scm.com/docs/git-log
[241]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codeselectedcode
[242]: https://www.git-scm.com/docs/git-log
[243]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codeseparatorcode
[244]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorinteractive
[245]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorinteractiveltslotgt
[246]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorpush
[247]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorpusherror
[248]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorremote
[249]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorremoteltslotgt
[250]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorshowBranch
[251]: https://www.git-scm.com/docs/git-show-branch
[252]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorstatus
[253]: https://www.git-scm.com/docs/git-status
[254]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorstatusltslotgt
[255]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colortransport
[256]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colortransportrejected
[257]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-colorui
[258]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-columnui
[259]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codealwayscode
[260]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codenevercode
[261]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codeautocode
[262]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codecolumncode
[263]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-coderowcode
[264]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codeplaincode
[265]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codedensecode
[266]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codenodensecode
[267]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-columnbranch
[268]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-columnclean
[269]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-columnstatus
[270]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-columntag
[271]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitcleanup
[272]: https://www.git-scm.com/docs/git-commit
[273]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitgpgSign
[274]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitstatus
[275]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-committemplate
[276]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitverbose
[277]: https://www.git-scm.com/docs/git-commit
[278]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitGraphgenerationVersion
[279]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitGraphmaxNewFilters
[280]: https://www.git-scm.com/docs/git-commit-graph
[281]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-commitGraphreadChangedPaths
[282]: https://www.git-scm.com/docs/git-commit-graph
[283]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentialhelper
[284]: https://www.git-scm.com/docs/gitcredentials
[285]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentialuseHttpPath
[286]: https://www.git-scm.com/docs/gitcredentials
[287]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentialusername
[288]: https://www.git-scm.com/docs/gitcredentials
[289]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentiallturlgt
[290]: https://www.git-scm.com/docs/gitcredentials
[291]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentialCacheignoreSIGHUP
[292]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-credentialStorelockTimeoutMS
[293]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-completioncommands
[294]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffautoRefreshIndex
[295]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffdirstat
[296]: https://www.git-scm.com/docs/git-diff
[297]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codechangescode
[298]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codelinescode
[299]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codefilescode
[300]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codecumulativecode
[301]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-ltlimitgt
[302]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffstatGraphWidth
[303]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffcontext
[304]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffinterHunkContext
[305]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffexternal
[306]: https://www.git-scm.com/docs/git
[307]: https://www.git-scm.com/docs/gitattributes
[308]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffignoreSubmodules
[309]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffmnemonicPrefix
[310]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codegitdiffcode
[311]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codegitdiffHEADcode
[312]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codegitdiff--cachedcode
[313]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codegitdiffHEADfile1file2code
[314]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codegitdiff--no-indexabcode
[315]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffnoprefix
[316]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffrelative
[317]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-difforderFile
[318]: https://www.git-scm.com/docs/git-diff
[319]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffrenameLimit
[320]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffrenames
[321]: https://www.git-scm.com/docs/git-diff
[322]: https://www.git-scm.com/docs/git-log
[323]: https://www.git-scm.com/docs/git-diff-files
[324]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffsuppressBlankEmpty
[325]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffsubmodule
[326]: https://www.git-scm.com/docs/git-submodule
[327]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffwordRegex
[328]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergtcommand
[329]: https://www.git-scm.com/docs/gitattributes
[330]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergtxfuncname
[331]: https://www.git-scm.com/docs/gitattributes
[332]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergtbinary
[333]: https://www.git-scm.com/docs/gitattributes
[334]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergttextconv
[335]: https://www.git-scm.com/docs/gitattributes
[336]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergtwordRegex
[337]: https://www.git-scm.com/docs/gitattributes
[338]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffltdrivergtcachetextconv
[339]: https://www.git-scm.com/docs/gitattributes
[340]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-difftool
[341]: https://www.git-scm.com/docs/git-difftool
[342]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffguitool
[343]: https://www.git-scm.com/docs/git-difftool
[344]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffindentHeuristic
[345]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffalgorithm
[346]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codedefaultcodecodemyerscode
[347]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codeminimalcode
[348]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codepatiencecode
[349]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-codehistogramcode
[350]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffwsErrorHighlight
[351]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffcolorMoved
[352]: https://www.git-scm.com/docs/git-diff
[353]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-diffcolorMovedWS
[354]: https://www.git-scm.com/docs/git-diff
[355]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-difftoollttoolgtpath
[356]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-difftoollttoolgtcmd
[357]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-difftoolprompt
[358]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-extensionsobjectFormat
[359]: https://www.git-scm.com/docs/git-init
[360]: https://www.git-scm.com/docs/git-clone
[361]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fastimportunpackLimit
[362]: https://www.git-scm.com/docs/git-fast-import
[363]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-feature
[364]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-featureexperimental
[365]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-featuremanyFiles
[366]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchrecurseSubmodules
[367]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchfsckObjects
[368]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchfsckltmsg-idgt
[369]: https://www.git-scm.com/docs/git-fetch-pack
[370]: https://www.git-scm.com/docs/git-fsck
[371]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchfsckskipList
[372]: https://www.git-scm.com/docs/git-fetch-pack
[373]: https://www.git-scm.com/docs/git-fsck
[374]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchunpackLimit
[375]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchprune
[376]: https://www.git-scm.com/docs/git-fetch
[377]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchpruneTags
[378]: https://www.git-scm.com/docs/git-fetch
[379]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchoutput
[380]: https://www.git-scm.com/docs/git-fetch
[381]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchnegotiationAlgorithm
[382]: https://www.git-scm.com/docs/git-fetch
[383]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchshowForcedUpdates
[384]: https://www.git-scm.com/docs/git-fetch
[385]: https://www.git-scm.com/docs/git-pull
[386]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchparallel
[387]: https://www.git-scm.com/docs/git-fetch
[388]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fetchwriteCommitGraph
[389]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatattach
[390]: https://www.git-scm.com/docs/git-format-patch
[391]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatfrom
[392]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatnumbered
[393]: https://www.git-scm.com/docs/git-format-patch
[394]: https://www.git-scm.com/docs/git-format-patch
[395]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatto
[396]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatcc
[397]: https://www.git-scm.com/docs/git-format-patch
[398]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatsubjectPrefix
[399]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatcoverFromDescription
[400]: https://www.git-scm.com/docs/git-format-patch
[401]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatsignature
[402]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatsignatureFile
[403]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatsuffix
[404]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatpretty
[405]: https://www.git-scm.com/docs/git-log
[406]: https://www.git-scm.com/docs/git-show
[407]: https://www.git-scm.com/docs/git-whatchanged
[408]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatthread
[409]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatsignOff
[410]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatcoverLetter
[411]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatoutputDirectory
[412]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatfilenameMaxLength
[413]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatuseAutoBase
[414]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-formatnotes
[415]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-filterltdrivergtclean
[416]: https://www.git-scm.com/docs/gitattributes
[417]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-filterltdrivergtsmudge
[418]: https://www.git-scm.com/docs/gitattributes
[419]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fsckltmsg-idgt
[420]: https://www.git-scm.com/docs/git-fsck
[421]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-fsckskipList
[422]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcaggressiveDepth
[423]: https://www.git-scm.com/docs/git-repack
[424]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcaggressiveWindow
[425]: https://www.git-scm.com/docs/git-repack
[426]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcauto
[427]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcautoPackLimit
[428]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcautoDetach
[429]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcbigPackThreshold
[430]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcwriteCommitGraph
[431]: https://www.git-scm.com/docs/git-gc
[432]: https://www.git-scm.com/docs/git-commit-graph
[433]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gclogExpiry
[434]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcpackRefs
[435]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcpruneExpire
[436]: https://www.git-scm.com/docs/git-gc
[437]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcworktreePruneExpire
[438]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcreflogExpire
[439]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcltpatterngtreflogExpire
[440]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcreflogExpireUnreachable
[441]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcltpatterngtreflogExpireUnreachable
[442]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcrerereResolved
[443]: https://www.git-scm.com/docs/git-rerere
[444]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gcrerereUnresolved
[445]: https://www.git-scm.com/docs/git-rerere
[446]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvscommitMsgAnnotation
[447]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsenabled
[448]: https://www.git-scm.com/docs/git-cvsserver
[449]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvslogFile
[450]: https://www.git-scm.com/docs/git-cvsserver
[451]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsusecrlfattr
[452]: https://www.git-scm.com/docs/gitattributes
[453]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsallBinary
[454]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsdbName
[455]: https://www.git-scm.com/docs/git-cvsserver
[456]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsdbDriver
[457]: https://www.git-scm.com/docs/git-cvsserver
[458]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsdbUsergitcvsdbPass
[459]: https://www.git-scm.com/docs/git-cvsserver
[460]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitcvsdbTableNamePrefix
[461]: https://www.git-scm.com/docs/git-cvsserver
[462]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebcategory
[463]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebdescription
[464]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebowner
[465]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitweburl
[466]: https://www.git-scm.com/docs/gitweb
[467]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebavatar
[468]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebblame
[469]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebgrep
[470]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebhighlight
[471]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebpatches
[472]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebpickaxe
[473]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebremoteheads
[474]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebshowSizes
[475]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gitwebsnapshot
[476]: https://www.git-scm.com/docs/gitweb.conf
[477]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-greplineNumber
[478]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-grepcolumn
[479]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-greppatternType
[480]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-grepextendedRegexp
[481]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-grepthreads
[482]: https://www.git-scm.com/docs/git-grep
[483]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-grepfallbackToNoIndex
[484]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgprogram
[485]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgformat
[486]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgltformatgtprogram
[487]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgminTrustLevel
[488]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgsshallowedSignersFile
[489]: mailto:user1@example.com
[490]: mailto:user2@example.com
[491]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-gpgsshrevocationFile
[492]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guicommitMsgWidth
[493]: https://www.git-scm.com/docs/git-gui
[494]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guidiffContext
[495]: https://www.git-scm.com/docs/git-gui
[496]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guidisplayUntracked
[497]: https://www.git-scm.com/docs/git-gui
[498]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guiencoding
[499]: https://www.git-scm.com/docs/git-gui
[500]: https://www.git-scm.com/docs/gitk
[501]: https://www.git-scm.com/docs/gitattributes
[502]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guimatchTrackingBranch
[503]: https://www.git-scm.com/docs/git-gui
[504]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guinewBranchTemplate
[505]: https://www.git-scm.com/docs/git-gui
[506]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guipruneDuringFetch
[507]: https://www.git-scm.com/docs/git-gui
[508]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitrustmtime
[509]: https://www.git-scm.com/docs/git-gui
[510]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guispellingDictionary
[511]: https://www.git-scm.com/docs/git-gui
[512]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guifastCopyBlame
[513]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guicopyBlameThreshold
[514]: https://www.git-scm.com/docs/git-blame
[515]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guiblamehistoryctx
[516]: https://www.git-scm.com/docs/gitk
[517]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtcmd
[518]: https://www.git-scm.com/docs/git-gui
[519]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtneedsFile
[520]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtnoConsole
[521]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtnoRescan
[522]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtconfirm
[523]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtargPrompt
[524]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtrevPrompt
[525]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtrevUnmerged
[526]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegttitle
[527]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-guitoolltnamegtprompt
[528]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-helpbrowser
[529]: https://www.git-scm.com/docs/git-help
[530]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-helpformat
[531]: https://www.git-scm.com/docs/git-help
[532]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-helpautoCorrect
[533]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-helphtmlPath
[534]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxy
[535]: https://www.git-scm.com/docs/gitcredentials
[536]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxyAuthMethod
[537]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxySSLCert
[538]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxySSLKey
[539]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxySSLCertPasswordProtected
[540]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpproxySSLCAInfo
[541]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpemptyAuth
[542]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpdelegation
[543]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpcookieFile
[544]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsaveCookies
[545]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpversion
[546]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslVersion
[547]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslCipherList
[548]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslVerify
[549]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslCert
[550]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslKey
[551]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslCertPasswordProtected
[552]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslCAInfo
[553]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslCAPath
[554]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslBackend
[555]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpschannelCheckRevoke
[556]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpschannelUseSSLCAInfo
[557]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httppinnedpubkey
[558]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpsslTry
[559]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpmaxRequests
[560]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpminSessions
[561]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httppostBuffer
[562]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httplowSpeedLimithttplowSpeedTime
[563]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpnoEPSV
[564]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpuserAgent
[565]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httpfollowRedirects
[566]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-httplturlgt
[567]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-i18ncommitEncoding
[568]: https://www.git-scm.com/docs/git-mailinfo
[569]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-i18nlogOutputEncoding
[570]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imapfolder
[571]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imaptunnel
[572]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imaphost
[573]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imapuser
[574]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imappass
[575]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imapport
[576]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imapsslverify
[577]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imappreformattedHTML
[578]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-imapauthMethod
[579]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-indexrecordEndOfIndexEntries
[580]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-indexrecordOffsetTable
[581]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-indexsparse
[582]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-indexthreads
[583]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-indexversion
[584]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-inittemplateDir
[585]: https://www.git-scm.com/docs/git-init
[586]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-initdefaultBranch
[587]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-instawebbrowser
[588]: https://www.git-scm.com/docs/git-instaweb
[589]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-instawebhttpd
[590]: https://www.git-scm.com/docs/git-instaweb
[591]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-instaweblocal
[592]: https://www.git-scm.com/docs/git-instaweb
[593]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-instawebmodulePath
[594]: https://www.git-scm.com/docs/git-instaweb
[595]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-instawebport
[596]: https://www.git-scm.com/docs/git-instaweb
[597]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-interactivesingleKey
[598]: https://www.git-scm.com/docs/git-add
[599]: https://www.git-scm.com/docs/git-checkout
[600]: https://www.git-scm.com/docs/git-restore
[601]: https://www.git-scm.com/docs/git-commit
[602]: https://www.git-scm.com/docs/git-reset
[603]: https://www.git-scm.com/docs/git-stash
[604]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-interactivediffFilter
[605]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logabbrevCommit
[606]: https://www.git-scm.com/docs/git-log
[607]: https://www.git-scm.com/docs/git-show
[608]: https://www.git-scm.com/docs/git-whatchanged
[609]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logdate
[610]: https://www.git-scm.com/docs/git-log
[611]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logdecorate
[612]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logexcludeDecoration
[613]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logdiffMerges
[614]: https://www.git-scm.com/docs/git-log
[615]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logfollow
[616]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-loggraphColors
[617]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logshowRoot
[618]: https://www.git-scm.com/docs/git-log
[619]: https://www.git-scm.com/docs/git-whatchanged
[620]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logshowSignature
[621]: https://www.git-scm.com/docs/git-log
[622]: https://www.git-scm.com/docs/git-show
[623]: https://www.git-scm.com/docs/git-whatchanged
[624]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-logmailmap
[625]: https://www.git-scm.com/docs/git-log
[626]: https://www.git-scm.com/docs/git-show
[627]: https://www.git-scm.com/docs/git-whatchanged
[628]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-lsrefsunborn
[629]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mailinfoscissors
[630]: https://www.git-scm.com/docs/git-mailinfo
[631]: https://www.git-scm.com/docs/git-am
[632]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mailmapfile
[633]: https://www.git-scm.com/docs/git-shortlog
[634]: https://www.git-scm.com/docs/git-blame
[635]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mailmapblob
[636]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenanceauto
[637]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenancestrategy
[638]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenancelttaskgtenabled
[639]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenancelttaskgtschedule
[640]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenancecommit-graphauto
[641]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenanceloose-objectsauto
[642]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-maintenanceincremental-repackauto
[643]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-manviewer
[644]: https://www.git-scm.com/docs/git-help
[645]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-manlttoolgtcmd
[646]: https://www.git-scm.com/docs/git-help
[647]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-manlttoolgtpath
[648]: https://www.git-scm.com/docs/git-help
[649]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeconflictStyle
[650]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergedefaultToUpstream
[651]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeff
[652]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeverifySignatures
[653]: https://www.git-scm.com/docs/git-merge
[654]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergebranchdesc
[655]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergelog
[656]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergesuppressDest
[657]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergerenameLimit
[658]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergerenames
[659]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergedirectoryRenames
[660]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergerenormalize
[661]: https://www.git-scm.com/docs/gitattributes
[662]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergestat
[663]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeautoStash
[664]: https://www.git-scm.com/docs/git-merge
[665]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetool
[666]: https://www.git-scm.com/docs/git-mergetool
[667]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeguitool
[668]: https://www.git-scm.com/docs/git-mergetool
[669]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeverbosity
[670]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeltdrivergtname
[671]: https://www.git-scm.com/docs/gitattributes
[672]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeltdrivergtdriver
[673]: https://www.git-scm.com/docs/gitattributes
[674]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergeltdrivergtrecursive
[675]: https://www.git-scm.com/docs/gitattributes
[676]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoollttoolgtpath
[677]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoollttoolgtcmd
[678]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoollttoolgthideResolved
[679]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoollttoolgttrustExitCode
[680]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolmeldhasOutput
[681]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolmelduseAutoMerge
[682]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolhideResolved
[683]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolkeepBackup
[684]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolkeepTemporaries
[685]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolwriteToTemp
[686]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-mergetoolprompt
[687]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesmergeStrategy
[688]: https://www.git-scm.com/docs/git-notes
[689]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesltnamegtmergeStrategy
[690]: https://www.git-scm.com/docs/git-notes
[691]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesdisplayRef
[692]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesrewriteltcommandgt
[693]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesrewriteMode
[694]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-notesrewriteRef
[695]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packwindow
[696]: https://www.git-scm.com/docs/git-pack-objects
[697]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packdepth
[698]: https://www.git-scm.com/docs/git-pack-objects
[699]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packwindowMemory
[700]: https://www.git-scm.com/docs/git-pack-objects
[701]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packcompression
[702]: https://www.git-scm.com/docs/git-repack
[703]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packallowPackReuse
[704]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packisland
[705]: https://www.git-scm.com/docs/git-pack-objects
[706]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packislandCore
[707]: https://www.git-scm.com/docs/git-pack-objects
[708]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packdeltaCacheSize
[709]: https://www.git-scm.com/docs/git-pack-objects
[710]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packdeltaCacheLimit
[711]: https://www.git-scm.com/docs/git-pack-objects
[712]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packthreads
[713]: https://www.git-scm.com/docs/git-pack-objects
[714]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packindexVersion
[715]: https://www.git-scm.com/docs/git-index-pack
[716]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packpackSizeLimit
[717]: https://www.git-scm.com/docs/git-repack
[718]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packuseBitmaps
[719]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packuseSparse
[720]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packpreferBitmapTips
[721]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packwriteBitmapsdeprecated
[722]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packwriteBitmapHashCache
[723]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-packwriteReverseIndex
[724]: https://www.git-scm.com/technical/pack-format
[725]: https://www.git-scm.com/docs/git-fast-import
[726]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-prettyltnamegt
[727]: https://www.git-scm.com/docs/git-log
[728]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-protocolallow
[729]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-protocolltnamegtallow
[730]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-protocolversion
[731]: https://www.git-scm.com/docs/protocol-v2
[732]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pullff
[733]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pullrebase
[734]: https://www.git-scm.com/docs/git-rebase
[735]: https://www.git-scm.com/docs/git-rebase
[736]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pulloctopus
[737]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pulltwohead
[738]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushdefault
[739]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushfollowTags
[740]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushgpgSign
[741]: https://www.git-scm.com/docs/git-push
[742]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushpushOption
[743]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushrecurseSubmodules
[744]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushuseForceIfIncludes
[745]: https://www.git-scm.com/docs/git-push
[746]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-pushnegotiate
[747]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebasebackend
[748]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebasestat
[749]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaseautoSquash
[750]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaseautoStash
[751]: https://www.git-scm.com/docs/git-rebase
[752]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebasemissingCommitsCheck
[753]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaseinstructionFormat
[754]: https://www.git-scm.com/docs/git-log
[755]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaseabbreviateCommands
[756]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaserescheduleFailedExec
[757]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rebaseforkPoint
[758]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveadvertiseAtomic
[759]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveadvertisePushOptions
[760]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveautogc
[761]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivecertNonceSeed
[762]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivecertNonceSlop
[763]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivefsckObjects
[764]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivefsckltmsg-idgt
[765]: https://www.git-scm.com/docs/git-receive-pack
[766]: https://www.git-scm.com/docs/git-fsck
[767]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivefsckskipList
[768]: https://www.git-scm.com/docs/git-receive-pack
[769]: https://www.git-scm.com/docs/git-fsck
[770]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivekeepAlive
[771]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveunpackLimit
[772]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivemaxInputSize
[773]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivedenyDeletes
[774]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivedenyDeleteCurrent
[775]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivedenyCurrentBranch
[776]: https://www.git-scm.com/docs/githooks
[777]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivedenyNonFastForwards
[778]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receivehideRefs
[779]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveprocReceiveRefs
[780]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveupdateServerInfo
[781]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-receiveshallowUpdate
[782]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remotepushDefault
[783]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegturl
[784]: https://www.git-scm.com/docs/git-fetch
[785]: https://www.git-scm.com/docs/git-push
[786]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtpushurl
[787]: https://www.git-scm.com/docs/git-push
[788]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtproxy
[789]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtproxyAuthMethod
[790]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtfetch
[791]: https://www.git-scm.com/docs/git-fetch
[792]: https://www.git-scm.com/docs/git-fetch
[793]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtpush
[794]: https://www.git-scm.com/docs/git-push
[795]: https://www.git-scm.com/docs/git-push
[796]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtmirror
[797]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtskipDefaultUpdate
[798]: https://www.git-scm.com/docs/git-fetch
[799]: https://www.git-scm.com/docs/git-remote
[800]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtskipFetchAll
[801]: https://www.git-scm.com/docs/git-fetch
[802]: https://www.git-scm.com/docs/git-remote
[803]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtreceivepack
[804]: https://www.git-scm.com/docs/git-push
[805]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtuploadpack
[806]: https://www.git-scm.com/docs/git-fetch-pack
[807]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegttagOpt
[808]: https://www.git-scm.com/docs/git-fetch
[809]: https://www.git-scm.com/docs/git-fetch
[810]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtvcs
[811]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtprune
[812]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtpruneTags
[813]: https://www.git-scm.com/docs/git-fetch
[814]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtpromisor
[815]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remoteltnamegtpartialclonefilter
[816]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-remotesltgroupgt
[817]: https://www.git-scm.com/docs/git-remote
[818]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-repackuseDeltaBaseOffset
[819]: https://www.git-scm.com/docs/git-repack
[820]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-repackpackKeptObjects
[821]: https://www.git-scm.com/docs/git-repack
[822]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-repackuseDeltaIslands
[823]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-repackwriteBitmaps
[824]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rerereautoUpdate
[825]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-rerereenabled
[826]: https://www.git-scm.com/docs/git-rerere
[827]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-resetquiet
[828]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailidentity
[829]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpEncryption
[830]: https://www.git-scm.com/docs/git-send-email
[831]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpsslcertpath
[832]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailltidentitygt
[833]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailaliasesFile
[834]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailaliasFileType
[835]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailannotate
[836]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailbcc
[837]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailcc
[838]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailccCmd
[839]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailchainReplyTo
[840]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailconfirm
[841]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailenvelopeSender
[842]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailfrom
[843]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailmultiEdit
[844]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsignedoffbycc
[845]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpPass
[846]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsuppresscc
[847]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsuppressFrom
[848]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailto
[849]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailtocmd
[850]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpDomain
[851]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpServer
[852]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpServerPort
[853]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpServerOption
[854]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpUser
[855]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailthread
[856]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailtransferEncoding
[857]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailvalidate
[858]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailxmailer
[859]: https://www.git-scm.com/docs/git-send-email
[860]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsignedoffccdeprecated
[861]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpBatchSize
[862]: https://www.git-scm.com/docs/git-send-email
[863]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailsmtpReloginDelay
[864]: https://www.git-scm.com/docs/git-send-email
[865]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sendemailforbidSendmailVariables
[866]: https://www.git-scm.com/docs/git-send-email
[867]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sequenceeditor
[868]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-showBranchdefault
[869]: https://www.git-scm.com/docs/git-show-branch
[870]: https://www.git-scm.com/docs/git-show-branch
[871]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-splitIndexmaxPercentChange
[872]: https://www.git-scm.com/docs/git-update-index
[873]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-splitIndexsharedIndexExpire
[874]: https://www.git-scm.com/docs/git-update-index
[875]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-sshvariant
[876]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusrelativePaths
[877]: https://www.git-scm.com/docs/git-status
[878]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusshort
[879]: https://www.git-scm.com/docs/git-status
[880]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusbranch
[881]: https://www.git-scm.com/docs/git-status
[882]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusaheadBehind
[883]: https://www.git-scm.com/docs/git-status
[884]: https://www.git-scm.com/docs/git-status
[885]: https://www.git-scm.com/docs/git-status
[886]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusrenameLimit
[887]: https://www.git-scm.com/docs/git-status
[888]: https://www.git-scm.com/docs/git-commit
[889]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusrenames
[890]: https://www.git-scm.com/docs/git-status
[891]: https://www.git-scm.com/docs/git-commit
[892]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusshowStash
[893]: https://www.git-scm.com/docs/git-status
[894]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statusshowUntrackedFiles
[895]: https://www.git-scm.com/docs/git-status
[896]: https://www.git-scm.com/docs/git-commit
[897]: https://www.git-scm.com/docs/git-status
[898]: https://www.git-scm.com/docs/git-commit
[899]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-statussubmoduleSummary
[900]: https://www.git-scm.com/docs/git-submodule
[901]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-stashuseBuiltin
[902]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-stashshowIncludeUntracked
[903]: https://www.git-scm.com/docs/git-stash
[904]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-stashshowPatch
[905]: https://www.git-scm.com/docs/git-stash
[906]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-stashshowStat
[907]: https://www.git-scm.com/docs/git-stash
[908]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegturl
[909]: https://www.git-scm.com/docs/git-submodule
[910]: https://www.git-scm.com/docs/gitmodules
[911]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegtupdate
[912]: https://www.git-scm.com/docs/gitmodules
[913]: https://www.git-scm.com/docs/git-submodule
[914]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegtbranch
[915]: https://www.git-scm.com/docs/git-submodule
[916]: https://www.git-scm.com/docs/gitmodules
[917]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegtfetchRecurseSubmodules
[918]: https://www.git-scm.com/docs/gitmodules
[919]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegtignore
[920]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleltnamegtactive
[921]: https://www.git-scm.com/docs/gitsubmodules
[922]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submoduleactive
[923]: https://www.git-scm.com/docs/gitsubmodules
[924]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submodulerecurse
[925]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submodulefetchJobs
[926]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submodulealternateLocation
[927]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-submodulealternateErrorStrategy
[928]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-tagforceSignAnnotated
[929]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-tagsort
[930]: https://www.git-scm.com/docs/git-tag
[931]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-taggpgSign
[932]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-tarumask
[933]: https://www.git-scm.com/docs/git-archive
[934]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2normalTarget
[935]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2perfTarget
[936]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2eventTarget
[937]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2normalBrief
[938]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2perfBrief
[939]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2eventBrief
[940]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2eventNesting
[941]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2configParams
[942]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2envVars
[943]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2destinationDebug
[944]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-trace2maxFiles
[945]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-transferfsckObjects
[946]: https://www.git-scm.com/docs/git-receive-pack
[947]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-transferhideRefs
[948]: https://www.git-scm.com/docs/gitnamespaces
[949]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-transferunpackLimit
[950]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-transferadvertiseSID
[951]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadarchiveallowUnreachable
[952]: https://www.git-scm.com/docs/git-upload-archive
[953]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackhideRefs
[954]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackallowTipSHA1InWant
[955]: https://www.git-scm.com/docs/gitnamespaces
[956]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackallowReachableSHA1InWant
[957]: https://www.git-scm.com/docs/gitnamespaces
[958]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackallowAnySHA1InWant
[959]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackkeepAlive
[960]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackpackObjectsHook
[961]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackallowFilter
[962]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackfilterallow
[963]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackfilterltfiltergtallow
[964]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackfiltertreemaxDepth
[965]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-uploadpackallowRefInWant
[966]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-urlltbasegtinsteadOf
[967]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-urlltbasegtpushInsteadOf
[968]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-username
[969]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-useremail
[970]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-authoremail
[971]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-committername
[972]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-committeremail
[973]: https://www.git-scm.com/docs/git-commit
[974]: https://www.git-scm.com/docs/git
[975]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-useruseConfigOnly
[976]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-usersigningKey
[977]: https://www.git-scm.com/docs/git-tag
[978]: https://www.git-scm.com/docs/git-commit
[979]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-versionsortprereleaseSuffixdeprecated
[980]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-versionsortsuffix
[981]: https://www.git-scm.com/docs/git-tag
[982]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-webbrowser
[983]: https://www.git-scm.com/docs/git-instaweb
[984]: https://www.git-scm.com/docs/git-help
[985]: https://www.git-scm.com/docs/git-config#Documentation/git-config.txt-worktreeguessRemote
