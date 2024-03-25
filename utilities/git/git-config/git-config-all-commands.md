# git :: all config vars

- `git help --config`  list of all available configuration variables
- `git help   config`  more info


## All configuration variables

[add]
add.ignoreErrors
add.interactive.useBuiltin

[advice]
advice.addEmbeddedRepo
advice.addEmptyPathspec
advice.addIgnoredFile
advice.ambiguousFetchRefspec
advice.amWorkDir
advice.checkoutAmbiguousRemoteBranchName
advice.commitBeforeMerge
advice.detachedHead
advice.fetchShowForcedUpdates
advice.graftFileDeprecated
advice.ignoredHook
advice.implicitIdentity
advice.nameTooLong
advice.nestedTag
advice.objectNameWarning
advice.pushAlreadyExists
advice.pushFetchFirst
advice.pushNeedsForce
advice.pushNonFastForward
advice.pushNonFFCurrent
advice.pushNonFFMatching
advice.pushRefNeedsUpdate
advice.pushUnqualifiedRefName
advice.pushUpdateRejected
advice.resetNoRefresh
advice.resolveConflict
advice.rmHints
advice.sequencerInUse
advice.setUpstreamFailure
advice.skippedCherryPicks
advice.statusAheadBehindWarning
advice.statusHints
advice.statusUoption
advice.submoduleAlternateErrorStrategyDie
advice.submodulesNotUpdated
advice.suggestDetachingHead
advice.updateSparsePath
advice.useCoreFSMonitorConfig
advice.waitingForEditor

[alias]
alias.*

[am]
am.keepcr
am.threeWay

[apply]
apply.ignoreWhitespace
apply.whitespace

[author]
author.email
author.name

[blame]
blame.blankBoundary
blame.coloring
blame.date
blame.ignoreRevsFile
blame.markIgnoredLines
blame.markUnblamableLines
blame.showEmail
blame.showRoot

[branch]
branch.<name>.description
branch.<name>.merge
branch.<name>.mergeOptions
branch.<name>.pushRemote
branch.<name>.rebase
branch.<name>.remote
branch.autoSetupMerge
branch.autoSetupRebase
branch.sort

[browser]
browser.<tool>.cmd
browser.<tool>.path

[checkout]
checkout.defaultRemote
checkout.guess
checkout.thresholdForParallelism
checkout.workers

[clean]
clean.requireForce

[clone]
clone.defaultRemoteName
clone.filterSubmodules
clone.rejectShallow

[color]
color.advice
color.advice.hint
color.blame.highlightRecent
color.blame.repeatedLines
color.branch
color.branch.current
color.branch.local
color.branch.plain
color.branch.remote
color.branch.reset
color.branch.upstream
color.branch.worktree
color.decorate.branch
color.decorate.grafted
color.decorate.HEAD
color.decorate.remoteBranch
color.decorate.stash
color.decorate.tag

[color "diff"]

color.diff
color.diff.commit
color.diff.context
color.diff.contextBold
color.diff.contextDimmed
color.diff.frag
color.diff.func
color.diff.meta
color.diff.new
color.diff.newBold
color.diff.newDimmed
color.diff.newMoved
color.diff.newMovedAlternative
color.diff.newMovedAlternativeDimmed
color.diff.newMovedDimmed
color.diff.old
color.diff.oldBold
color.diff.oldDimmed
color.diff.oldMoved
color.diff.oldMovedAlternative
color.diff.oldMovedAlternativeDimmed
color.diff.oldMovedDimmed
color.diff.plain
color.diff.whitespace

color.grep
color.grep.column
color.grep.context
color.grep.filename
color.grep.function
color.grep.lineNumber
color.grep.match
color.grep.matchContext
color.grep.matchSelected
color.grep.selected
color.grep.separator

color.interactive
color.interactive.error
color.interactive.header
color.interactive.help
color.interactive.plain
color.interactive.prompt
color.interactive.reset

color.pager
color.push
color.push.error
color.remote
color.remote.error
color.remote.hint
color.remote.success
color.remote.warning
color.showBranch

color.status
color.status.added
color.status.branch
color.status.changed
color.status.header
color.status.localBranch
color.status.noBranch
color.status.remoteBranch
color.status.unmerged
color.status.untracked
color.status.updated

color.transport
color.transport.rejected
color.ui

[column]
column.branch
column.clean
column.status
column.tag
column.ui

[commit]
commit.cleanup
commit.gpgSign
commit.status
commit.template
commit.verbose

[commitGraph]
commitGraph.generationVersion
commitGraph.maxNewFilters
commitGraph.readChangedPaths

[committer]
committer.email
committer.name

[completion]
completion.commands

[core]
core.abbrev
core.alternateRefsCommand
core.alternateRefsPrefixes
core.askPass
core.attributesFile
core.autocrlf
core.bare
core.bigFileThreshold
core.checkRoundtripEncoding
core.checkStat
core.commentChar
core.commitGraph
core.compression
core.createObject
core.deltaBaseCacheLimit
core.editor
core.eol
core.excludesFile
core.fileMode
core.filesRefLockTimeout
core.fscache
core.fsmonitor
core.fsmonitorHookVersion
core.fsync
core.fsyncMethod
core.fsyncObjectFiles
core.gitProxy
core.hideDotFiles
core.hooksPath
core.ignoreCase
core.ignoreStat
core.logAllRefUpdates
core.longpaths
core.looseCompression
core.multiPackIndex
core.notesRef
core.packedGitLimit
core.packedGitWindowSize
core.packedRefsTimeout
core.pager
core.precomposeUnicode
core.preferSymlinkRefs
core.preloadIndex
core.protectHFS
core.protectNTFS
core.quotePath
core.repositoryFormatVersion
core.restrictinheritedhandles
core.safecrlf
core.sharedRepository
core.sparseCheckout
core.sparseCheckoutCone
core.splitIndex
core.sshCommand
core.symlinks
core.trustctime
core.unsetenvvars
core.untrackedCache
core.useReplaceRefs
core.warnAmbiguousRefs
core.whitespace
core.worktree

[credential]
credential.<url>.*
credential.helper
credential.useHttpPath
credential.username

credentialCache.ignoreSIGHUP

credentialStore.lockTimeoutMS

[diff]
diff.<driver>.binary
diff.<driver>.cachetextconv
diff.<driver>.command
diff.<driver>.textconv
diff.<driver>.wordRegex
diff.<driver>.xfuncname
diff.algorithm
diff.autoRefreshIndex
diff.colorMoved
diff.colorMovedWS
diff.context
diff.dirstat
diff.external
diff.guitool
diff.ignoreSubmodules
diff.indentHeuristic
diff.interHunkContext
diff.mnemonicPrefix
diff.noprefix
diff.orderFile
diff.relative
diff.renameLimit
diff.renames
diff.statGraphWidth
diff.submodule
diff.suppressBlankEmpty
diff.tool
diff.wordRegex
diff.wsErrorHighlight

difftool.<tool>.cmd
difftool.<tool>.path
difftool.prompt

extensions.objectFormat
extensions.worktreeConfig

fastimport.unpackLimit

[feature]
feature.*
feature.experimental
feature.manyFiles

[fetch]
fetch.fsck.<msg-id>
fetch.fsck.skipList
fetch.fsckObjects
fetch.negotiationAlgorithm
fetch.output
fetch.parallel
fetch.prune
fetch.pruneTags
fetch.recurseSubmodules
fetch.showForcedUpdates
fetch.unpackLimit
fetch.writeCommitGraph

filter.<driver>.clean
filter.<driver>.smudge

format.attach
format.cc
format.coverFromDescription
format.coverLetter
format.encodeEmailHeaders
format.filenameMaxLength
format.from
format.headers
format.notes
format.numbered
format.outputDirectory
format.pretty
format.signature
format.signatureFile
format.signOff
format.subjectPrefix
format.suffix
format.thread
format.to
format.useAutoBase

fsck.badDate
fsck.badDateOverflow
fsck.badEmail
fsck.badFilemode
fsck.badName
fsck.badObjectSha1
fsck.badParentSha1
fsck.badTagName
fsck.badTagObject
fsck.badTimezone
fsck.badTree
fsck.badTreeSha1
fsck.badType
fsck.duplicateEntries
fsck.emptyName
fsck.extraHeaderEntry
fsck.fullPathname
fsck.gitattributesSymlink
fsck.gitignoreSymlink
fsck.gitmodulesBlob
fsck.gitmodulesLarge
fsck.gitmodulesMissing
fsck.gitmodulesName
fsck.gitmodulesParse
fsck.gitmodulesPath
fsck.gitmodulesSymlink
fsck.gitmodulesUpdate
fsck.gitmodulesUrl
fsck.hasDot
fsck.hasDotdot
fsck.hasDotgit
fsck.mailmapSymlink
fsck.missingAuthor
fsck.missingCommitter
fsck.missingEmail
fsck.missingNameBeforeEmail
fsck.missingObject
fsck.missingSpaceBeforeDate
fsck.missingSpaceBeforeEmail
fsck.missingTag
fsck.missingTagEntry
fsck.missingTaggerEntry
fsck.missingTree
fsck.missingTreeObject
fsck.missingType
fsck.missingTypeEntry
fsck.multipleAuthors
fsck.nulInCommit
fsck.nulInHeader
fsck.nullSha1
fsck.skipList
fsck.treeNotSorted
fsck.unknownType
fsck.unterminatedHeader
fsck.zeroPaddedDate
fsck.zeroPaddedFilemode

gc.<pattern>.reflogExpire
gc.<pattern>.reflogExpireUnreachable
gc.aggressiveDepth
gc.aggressiveWindow
gc.auto
gc.autoDetach
gc.autoPackLimit
gc.bigPackThreshold
gc.cruftPacks
gc.logExpiry
gc.packRefs
gc.pruneExpire
gc.reflogExpire
gc.reflogExpireUnreachable
gc.rerereResolved
gc.rerereUnresolved
gc.worktreePruneExpire
gc.writeCommitGraph

gitcvs.allBinary
gitcvs.commitMsgAnnotation
gitcvs.dbDriver
gitcvs.dbName
gitcvs.dbPass
gitcvs.dbTableNamePrefix
gitcvs.dbUser
gitcvs.enabled
gitcvs.logFile
gitcvs.usecrlfattr

gitweb.avatar
gitweb.blame
gitweb.category
gitweb.description
gitweb.grep
gitweb.highlight
gitweb.owner
gitweb.patches
gitweb.pickaxe
gitweb.remote_heads
gitweb.showSizes
gitweb.snapshot
gitweb.url

gpg.<format>.program
gpg.format
gpg.minTrustLevel
gpg.program
gpg.ssh.allowedSignersFile
gpg.ssh.defaultKeyCommand
gpg.ssh.revocationFile

grep.column
grep.extendedRegexp
grep.fallbackToNoIndex
grep.lineNumber
grep.patternType
grep.threads

gui.blamehistoryctx
gui.commitMsgWidth
gui.copyBlameThreshold
gui.diffContext
gui.displayUntracked
gui.encoding
gui.fastCopyBlame
gui.matchTrackingBranch
gui.newBranchTemplate
gui.pruneDuringFetch
gui.spellingDictionary
gui.trustmtime

guitool.<name>.argPrompt
guitool.<name>.cmd
guitool.<name>.confirm
guitool.<name>.needsFile
guitool.<name>.noConsole
guitool.<name>.noRescan
guitool.<name>.prompt
guitool.<name>.revPrompt
guitool.<name>.revUnmerged
guitool.<name>.title

help.autoCorrect
help.browser
help.format
help.htmlPath

http.<url>.*
http.cookieFile
http.curloptResolve
http.delegation
http.emptyAuth
http.extraHeader
http.followRedirects
http.lowSpeedLimit
http.lowSpeedTime
http.maxRequests
http.minSessions
http.noEPSV
http.pinnedPubkey
http.postBuffer
http.proxy
http.proxyAuthMethod
http.proxySSLCAInfo
http.proxySSLCert
http.proxySSLCertPasswordProtected
http.proxySSLKey
http.saveCookies
http.schannelCheckRevoke
http.schannelUseSSLCAInfo
http.sslAutoClientCert
http.sslBackend
http.sslCAInfo
http.sslCAPath
http.sslCert
http.sslCertPasswordProtected
http.sslCipherList
http.sslKey
http.sslTry
http.sslVerify
http.sslVersion
http.userAgent
http.version

i18n.commitEncoding
i18n.logOutputEncoding

imap.authMethod
imap.folder
imap.host
imap.pass
imap.port
imap.preformattedHTML
imap.sslverify
imap.tunnel
imap.user

index.recordEndOfIndexEntries
index.recordOffsetTable
index.sparse
index.threads
index.version

init.defaultBranch
init.templateDir

instaweb.browser
instaweb.httpd
instaweb.local
instaweb.modulePath
instaweb.port

interactive.diffFilter
interactive.singleKey

log.abbrevCommit
log.date
log.decorate
log.diffMerges
log.excludeDecoration
log.follow
log.graphColors
log.mailmap
log.showRoot
log.showSignature

lsrefs.unborn

mailinfo.scissors

mailmap.blob
mailmap.file

maintenance.<task>.enabled
maintenance.<task>.schedule
maintenance.auto
maintenance.commit-graph.auto
maintenance.incremental-repack.auto
maintenance.loose-objects.auto
maintenance.strategy

man.<tool>.cmd
man.<tool>.path
man.viewer

merge.<driver>.driver
merge.<driver>.name
merge.<driver>.recursive
merge.autoStash
merge.branchdesc
merge.conflictStyle
merge.defaultToUpstream
merge.directoryRenames
merge.ff
merge.guitool
merge.log
merge.renameLimit
merge.renames
merge.renormalize
merge.stat
merge.suppressDest
merge.tool
merge.verbosity
merge.verifySignatures

mergetool.<tool>.cmd
mergetool.<tool>.hideResolved
mergetool.<tool>.path
mergetool.<tool>.trustExitCode
mergetool.hideResolved
mergetool.keepBackup
mergetool.keepTemporaries
mergetool.meld.hasOutput
mergetool.meld.useAutoMerge
mergetool.prompt
mergetool.vimdiff.layout
mergetool.writeToTemp

notes.<name>.mergeStrategy
notes.displayRef
notes.mergeStrategy
notes.rewrite.<command>
notes.rewriteMode
notes.rewriteRef

pack.allowPackReuse
pack.compression
pack.deltaCacheLimit
pack.deltaCacheSize
pack.depth
pack.indexVersion
pack.island
pack.islandCore
pack.packSizeLimit
pack.preferBitmapTips
pack.threads
pack.useBitmaps
pack.useSparse
pack.window
pack.windowMemory
pack.writeBitmapHashCache
pack.writeReverseIndex

pager.<cmd>

pretty.<name>

protocol.<name>.allow
protocol.allow
protocol.version

pull.ff
pull.octopus
pull.rebase
pull.twohead

push.autoSetupRemote
push.default
push.followTags
push.gpgSign
push.negotiate
push.pushOption
push.recurseSubmodules
push.useForceIfIncludes

rebase.abbreviateCommands
rebase.autoSquash
rebase.autoStash
rebase.backend
rebase.forkPoint
rebase.instructionFormat
rebase.missingCommitsCheck
rebase.rescheduleFailedExec
rebase.stat

receive.advertiseAtomic
receive.advertisePushOptions
receive.autogc
receive.certNonceSeed
receive.certNonceSlop
receive.denyCurrentBranch
receive.denyDeleteCurrent
receive.denyDeletes
receive.denyNonFastForwards
receive.fsck.badDate
receive.fsck.badDateOverflow
receive.fsck.badEmail
receive.fsck.badFilemode
receive.fsck.badName
receive.fsck.badObjectSha1
receive.fsck.badParentSha1
receive.fsck.badTagName
receive.fsck.badTagObject
receive.fsck.badTimezone
receive.fsck.badTree
receive.fsck.badTreeSha1
receive.fsck.badType
receive.fsck.duplicateEntries
receive.fsck.emptyName
receive.fsck.extraHeaderEntry
receive.fsck.fullPathname
receive.fsck.gitattributesSymlink
receive.fsck.gitignoreSymlink
receive.fsck.gitmodulesBlob
receive.fsck.gitmodulesLarge
receive.fsck.gitmodulesMissing
receive.fsck.gitmodulesName
receive.fsck.gitmodulesParse
receive.fsck.gitmodulesPath
receive.fsck.gitmodulesSymlink
receive.fsck.gitmodulesUpdate
receive.fsck.gitmodulesUrl
receive.fsck.hasDot
receive.fsck.hasDotdot
receive.fsck.hasDotgit
receive.fsck.mailmapSymlink
receive.fsck.missingAuthor
receive.fsck.missingCommitter
receive.fsck.missingEmail
receive.fsck.missingNameBeforeEmail
receive.fsck.missingObject
receive.fsck.missingSpaceBeforeDate
receive.fsck.missingSpaceBeforeEmail
receive.fsck.missingTag
receive.fsck.missingTagEntry
receive.fsck.missingTaggerEntry
receive.fsck.missingTree
receive.fsck.missingTreeObject
receive.fsck.missingType
receive.fsck.missingTypeEntry
receive.fsck.multipleAuthors
receive.fsck.nulInCommit
receive.fsck.nulInHeader
receive.fsck.nullSha1
receive.fsck.skipList
receive.fsck.treeNotSorted
receive.fsck.unknownType
receive.fsck.unterminatedHeader
receive.fsck.zeroPaddedDate
receive.fsck.zeroPaddedFilemode
receive.fsckObjects
receive.hideRefs
receive.keepAlive
receive.maxInputSize
receive.procReceiveRefs
receive.shallowUpdate
receive.unpackLimit
receive.updateServerInfo

remote.<name>.fetch
remote.<name>.mirror
remote.<name>.partialclonefilter
remote.<name>.promisor
remote.<name>.proxy
remote.<name>.proxyAuthMethod
remote.<name>.prune
remote.<name>.pruneTags
remote.<name>.push
remote.<name>.pushurl
remote.<name>.receivepack
remote.<name>.skipDefaultUpdate
remote.<name>.skipFetchAll
remote.<name>.tagOpt
remote.<name>.uploadpack
remote.<name>.url
remote.<name>.vcs
remote.pushDefault

remotes.<group>

repack.cruftDepth
repack.cruftThreads
repack.cruftWindow
repack.cruftWindowMemory
repack.packKeptObjects
repack.updateServerInfo
repack.useDeltaBaseOffset
repack.useDeltaIslands
repack.writeBitmaps

rerere.autoUpdate
rerere.enabled

revert.reference

safe.directory

sendemail.<identity>.*
sendemail.aliasesFile
sendemail.aliasFileType
sendemail.annotate
sendemail.bcc
sendemail.cc
sendemail.ccCmd
sendemail.chainReplyTo
sendemail.confirm
sendemail.envelopeSender
sendemail.forbidSendmailVariables
sendemail.from
sendemail.identity
sendemail.multiEdit
sendemail.signedoffbycc
sendemail.smtpBatchSize
sendemail.smtpDomain
sendemail.smtpEncryption
sendemail.smtpPass
sendemail.smtpReloginDelay
sendemail.smtpServer
sendemail.smtpServerOption
sendemail.smtpServerPort
sendemail.smtpsslcertpath
sendemail.smtpUser
sendemail.suppresscc
sendemail.suppressFrom
sendemail.thread
sendemail.to
sendemail.tocmd
sendemail.transferEncoding
sendemail.validate
sendemail.xmailer

sendpack.sideband
sequence.editor
showBranch.default
sparse.expectFilesOutsideOfPatterns

splitIndex.maxPercentChange
splitIndex.sharedIndexExpire

ssh.variant

stash.showIncludeUntracked
stash.showPatch
stash.showStat

status.aheadBehind
status.branch
status.displayCommentPrefix
status.relativePaths
status.renameLimit
status.renames
status.short
status.showStash
status.showUntrackedFiles
status.submoduleSummary

submodule.<name>.active
submodule.<name>.branch
submodule.<name>.fetchRecurseSubmodules
submodule.<name>.ignore
submodule.<name>.update
submodule.<name>.url
submodule.active
submodule.alternateErrorStrategy
submodule.alternateLocation
submodule.fetchJobs
submodule.propagateBranches
submodule.recurse

tag.forceSignAnnotated
tag.gpgSign
tag.sort

tar.umask

trace2.configParams
trace2.destinationDebug
trace2.envVars
trace2.eventBrief
trace2.eventNesting
trace2.eventTarget
trace2.maxFiles
trace2.normalBrief
trace2.normalTarget
trace2.perfBrief
trace2.perfTarget

transfer.advertiseSID
transfer.credentialsInUrl
transfer.fsckObjects
transfer.hideRefs
transfer.unpackLimit

uploadarchive.allowUnreachable

uploadpack.allowAnySHA1InWant
uploadpack.allowFilter
uploadpack.allowReachableSHA1InWant
uploadpack.allowRefInWant
uploadpack.allowTipSHA1InWant
uploadpack.hideRefs
uploadpack.keepAlive
uploadpack.packObjectsHook

uploadpackfilter.<filter>.allow
uploadpackfilter.allow
uploadpackfilter.tree.maxDepth

url.<base>.insteadOf
url.<base>.pushInsteadOf

user.email
user.name
user.signingKey
user.useConfigOnly

versionsort.suffix
web.browser
windows.appendAtomically
worktree.guessRemote