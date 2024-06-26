# option-list

https://vimhelp.org/quickref.txt.html#option-list

Short explanation of each option:		option-list
'aleph'		  'al'	    ASCII code of the letter Aleph (Hebrew)
'allowrevins'	  'ari'     allow CTRL-_ in Insert and Command-line mode
'altkeymap'	  'akm'	    obsolete option for Farsi
'ambiwidth'	  'ambw'    what to do with Unicode chars of ambiguous width
'antialias'	  'anti'    Mac OS X: use smooth, antialiased fonts
'arabic'	  'arab'    for Arabic as a default second language
'arabicshape'	  'arshape' do shaping for Arabic characters
'autochdir'	  'acd'     change directory to the file in the current window
'autoindent'	  'ai'	    take indent for new line from previous line
'autoread'	  'ar'	    autom. read file when changed outside of Vim
'autoshelldir'	  'asd'     change directory to the shell's current directory
'autowrite'	  'aw'	    automatically write file if changed
'autowriteall'	  'awa'     as 'autowrite', but works with more commands
'background'	  'bg'	    "dark" or "light", used for highlight colors
'backspace'	  'bs'	    how backspace works at start of line
'backup'	  'bk'	    keep backup file after overwriting a file
'backupcopy'	  'bkc'     make backup as a copy, don't rename the file
'backupdir'	  'bdir'    list of directories for the backup file
'backupext'	  'bex'     extension used for the backup file
'backupskip'	  'bsk'     no backup for files that match these patterns
'balloondelay'	  'bdlay'   delay in mS before a balloon may pop up
'ballooneval'	  'beval'     switch on balloon evaluation in the GUI
'balloonevalterm' 'bevalterm' switch on balloon evaluation in the terminal
'balloonexpr'	  'bexpr'   expression to show in balloon
'belloff'	  'bo'	    do not ring the bell for these reasons
'binary'	  'bin'     read/write/edit file in binary mode
'bioskey'	  'biosk'   MS-DOS: use bios calls for input characters
'bomb'			    prepend a Byte Order Mark to the file
'breakat'	  'brk'     characters that may cause a line break
'breakindent'	  'bri'     wrapped line repeats indent
'breakindentopt'  'briopt'  settings for 'breakindent'
'browsedir'	  'bsdir'   which directory to start browsing in
'bufhidden'	  'bh'	    what to do when buffer is no longer in window
'buflisted'	  'bl'	    whether the buffer shows up in the buffer list
'buftype'	  'bt'	    special type of buffer
'casemap'	  'cmp'     specifies how case of letters is changed
'cdhome'	  'cdh'	    change directory to the home directory by ":cd"
'cdpath'	  'cd'	    list of directories searched with ":cd"
'cedit'			    key used to open the command-line window
'charconvert'	  'ccv'     expression for character encoding conversion
'cindent'	  'cin'     do C program indenting
'cinkeys'	  'cink'    keys that trigger indent when 'cindent' is set
'cinoptions'	  'cino'    how to do indenting when 'cindent' is set
'cinscopedecls'	  'cinsd'   words that are recognized by 'cino-g'
'cinwords'	  'cinw'    words where 'si' and 'cin' add an indent
'clipboard'	  'cb'	    use the clipboard as the unnamed register
'cmdheight'	  'ch'	    number of lines to use for the command-line
'cmdwinheight'	  'cwh'     height of the command-line window
'colorcolumn'	  'cc'	    columns to highlight
'columns'	  'co'	    number of columns in the display
'comments'	  'com'     patterns that can start a comment line
'commentstring'   'cms'     template for comments; used for fold marker
'compatible'	  'cp'	    behave Vi-compatible as much as possible
'complete'	  'cpt'     specify how Insert mode completion works
'completefunc'	  'cfu'     function to be used for Insert mode completion
'completeopt'	  'cot'     options for Insert mode completion
'completepopup'	  'cpp'     options for the Insert mode completion info popup
'completeslash'	  'csl'	    like 'shellslash' for completion
'concealcursor'	  'cocu'    whether concealable text is hidden in cursor line
'conceallevel'	  'cole'    whether concealable text is shown or hidden
'confirm'	  'cf'	    ask what to do about unsaved/read-only files
'conskey'	  'consk'   get keys directly from console (MS-DOS only)
'copyindent'	  'ci'	    make 'autoindent' use existing indent structure
'cpoptions'	  'cpo'     flags for Vi-compatible behavior
'cryptmethod'	  'cm'	    type of encryption to use for file writing
'cscopepathcomp'  'cspc'    how many components of the path to show
'cscopeprg'       'csprg'   command to execute cscope
'cscopequickfix'  'csqf'    use quickfix window for cscope results
'cscoperelative'  'csre'    Use cscope.out path basename as prefix
'cscopetag'       'cst'     use cscope for tag commands
'cscopetagorder'  'csto'    determines ":cstag" search order
'cscopeverbose'   'csverb'  give messages when adding a cscope database
'cursorbind'	  'crb'     move cursor in window as it moves in other windows
'cursorcolumn'	  'cuc'	    highlight the screen column of the cursor
'cursorline'	  'cul'	    highlight the screen line of the cursor
'cursorlineopt'	  'culopt'  settings for 'cursorline'
'debug'			    set to "msg" to see all error messages
'define'	  'def'     pattern to be used to find a macro definition
'delcombine'	  'deco'    delete combining characters on their own
'dictionary'	  'dict'    list of file names used for keyword completion
'diff'			    use diff mode for the current window
'diffexpr'	  'dex'     expression used to obtain a diff file
'diffopt'	  'dip'     options for using diff mode
'digraph'	  'dg'	    enable the entering of digraphs in Insert mode
'directory'	  'dir'     list of directory names for the swap file
'display'	  'dy'	    list of flags for how to display text
'eadirection'	  'ead'     in which direction 'equalalways' works
'edcompatible'	  'ed'	    toggle flags of ":substitute" command
'emoji'		  'emo'	    emoji characters are considered full width
'encoding'	  'enc'     encoding used internally
'endoffile'	  'eof'     write CTRL-Z at end of the file
'endofline'	  'eol'     write <EOL> for last line in file
'equalalways'	  'ea'	    windows are automatically made the same size
'equalprg'	  'ep'	    external program to use for "=" command
'errorbells'	  'eb'	    ring the bell for error messages
'errorfile'	  'ef'	    name of the errorfile for the QuickFix mode
'errorformat'	  'efm'     description of the lines in the error file
'esckeys'	  'ek'	    recognize function keys in Insert mode
'eventignore'	  'ei'	    autocommand events that are ignored
'expandtab'	  'et'	    use spaces when <Tab> is inserted
'exrc'		  'ex'	    read .vimrc and .exrc in the current directory
'fileencoding'	  'fenc'    file encoding for multibyte text
'fileencodings'   'fencs'   automatically detected character encodings
'fileformat'	  'ff'	    file format used for file I/O
'fileformats'	  'ffs'     automatically detected values for 'fileformat'
'fileignorecase'  'fic'     ignore case when using file names
'filetype'	  'ft'	    type of file, used for autocommands
'fillchars'	  'fcs'     characters to use for displaying special items
'fixendofline'	  'fixeol'  make sure last line in file has <EOL>
'fkmap'		  'fk'	    obsolete option for Farsi
'foldclose'	  'fcl'     close a fold when the cursor leaves it
'foldcolumn'	  'fdc'     width of the column used to indicate folds
'foldenable'	  'fen'     set to display all folds open
'foldexpr'	  'fde'     expression used when 'foldmethod' is "expr"
'foldignore'	  'fdi'     ignore lines when 'foldmethod' is "indent"
'foldlevel'	  'fdl'     close folds with a level higher than this
'foldlevelstart'  'fdls'    'foldlevel' when starting to edit a file
'foldmarker'	  'fmr'     markers used when 'foldmethod' is "marker"
'foldmethod'	  'fdm'     folding type
'foldminlines'	  'fml'     minimum number of lines for a fold to be closed
'foldnestmax'	  'fdn'     maximum fold depth
'foldopen'	  'fdo'     for which commands a fold will be opened
'foldtext'	  'fdt'     expression used to display for a closed fold
'formatexpr'	  'fex'     expression used with "gq" command
'formatlistpat'   'flp'     pattern used to recognize a list header
'formatoptions'   'fo'	    how automatic formatting is to be done
'formatprg'	  'fp'	    name of external program used with "gq" command
'fsync'		  'fs'	    whether to invoke fsync() after file write
'gdefault'	  'gd'	    the ":substitute" flag 'g' is default on
'grepformat'	  'gfm'     format of 'grepprg' output
'grepprg'	  'gp'	    program to use for ":grep"
'guicursor'	  'gcr'     GUI: settings for cursor shape and blinking
'guifont'	  'gfn'     GUI: Name(s) of font(s) to be used
'guifontset'	  'gfs'     GUI: Names of multibyte fonts to be used
'guifontwide'	  'gfw'     list of font names for double-wide characters
'guiheadroom'	  'ghr'     GUI: pixels room for window decorations
'guiligatures'	  'gli'	    GTK GUI: ASCII characters that can form shapes
'guioptions'	  'go'	    GUI: Which components and options are used
'guipty'		    GUI: try to use a pseudo-tty for ":!" commands
'guitablabel'	  'gtl'     GUI: custom label for a tab page
'guitabtooltip'   'gtt'     GUI: custom tooltip for a tab page
'helpfile'	  'hf'	    full path name of the main help file
'helpheight'	  'hh'	    minimum height of a new help window
'helplang'	  'hlg'     preferred help languages
'hidden'	  'hid'     don't unload buffer when it is abandoned
'highlight'	  'hl'	    sets highlighting mode for various occasions
'history'	  'hi'	    number of command-lines that are remembered
'hkmap'		  'hk'	    Hebrew keyboard mapping
'hkmapp'	  'hkp'     phonetic Hebrew keyboard mapping
'hlsearch'	  'hls'     highlight matches with last search pattern
'icon'			    let Vim set the text of the window icon
'iconstring'		    string to use for the Vim icon text
'ignorecase'	  'ic'	    ignore case in search patterns
'imactivatefunc'  'imaf'    function to enable/disable the X input method
'imactivatekey'   'imak'    key that activates the X input method
'imcmdline'	  'imc'     use IM when starting to edit a command line
'imdisable'	  'imd'     do not use the IM in any mode
'iminsert'	  'imi'     use :lmap or IM in Insert mode
'imsearch'	  'ims'     use :lmap or IM when typing a search pattern
'imstatusfunc'    'imsf'    function to obtain X input method status
'imstyle'	  'imst'    specifies the input style of the input method
'include'	  'inc'     pattern to be used to find an include file
'includeexpr'	  'inex'    expression used to process an include line
'incsearch'	  'is'	    highlight match while typing search pattern
'indentexpr'	  'inde'    expression used to obtain the indent of a line
'indentkeys'	  'indk'    keys that trigger indenting with 'indentexpr'
'infercase'	  'inf'     adjust case of match for keyword completion
'insertmode'	  'im'	    start the edit of a file in Insert mode
'isfname'	  'isf'     characters included in file names and pathnames
'isident'	  'isi'     characters included in identifiers
'iskeyword'	  'isk'     characters included in keywords
'isprint'	  'isp'     printable characters
'joinspaces'	  'js'	    two spaces after a period with a join command
'jumpoptions'	  'jop'     specifies how jumping is done
'key'			    encryption key
'keymap'	  'kmp'     name of a keyboard mapping
'keymodel'	  'km'	    enable starting/stopping selection with keys
'keyprotocol'	  'kpc'	    what keyboard protocol to use for what terminal
'keywordprg'	  'kp'	    program to use for the "K" command
'langmap'	  'lmap'    alphabetic characters for other language mode
'langmenu'	  'lm'	    language to be used for the menus
'langnoremap'	  'lnr'	    do not apply 'langmap' to mapped characters
'langremap'	  'lrm'	    do apply 'langmap' to mapped characters
'laststatus'	  'ls'	    tells when last window has status lines
'lazyredraw'	  'lz'	    don't redraw while executing macros
'linebreak'	  'lbr'     wrap long lines at a blank
'lines'			    number of lines in the display
'linespace'	  'lsp'     number of pixel lines to use between characters
'lisp'			    automatic indenting for Lisp
'lispoptions'	  'lop'     changes how Lisp indenting is done
'lispwords'	  'lw'	    words that change how lisp indenting works
'list'			    show <Tab> and <EOL>
'listchars'	  'lcs'     characters for displaying in list mode
'loadplugins'	  'lpl'     load plugin scripts when starting up
'luadll'		    name of the Lua dynamic library
'macatsui'		    Mac GUI: use ATSUI text drawing
'magic'			    changes special characters in search patterns
'makeef'	  'mef'     name of the errorfile for ":make"
'makeencoding'	  'menc'    encoding of external make/grep commands
'makeprg'	  'mp'	    program to use for the ":make" command
'matchpairs'	  'mps'     pairs of characters that "%" can match
'matchtime'	  'mat'     tenths of a second to show matching paren
'maxcombine'	  'mco'     maximum nr of combining characters displayed
'maxfuncdepth'	  'mfd'     maximum recursive depth for user functions
'maxmapdepth'	  'mmd'     maximum recursive depth for mapping
'maxmem'	  'mm'	    maximum memory (in Kbyte) used for one buffer
'maxmempattern'   'mmp'     maximum memory (in Kbyte) used for pattern search
'maxmemtot'	  'mmt'     maximum memory (in Kbyte) used for all buffers
'menuitems'	  'mis'     maximum number of items in a menu
'mkspellmem'	  'msm'     memory used before :mkspell compresses the tree
'modeline'	  'ml'	    recognize modelines at start or end of file
'modelineexpr'	  'mle'	    allow setting expression options from a modeline
'modelines'	  'mls'     number of lines checked for modelines
'modifiable'	  'ma'	    changes to the text are not possible
'modified'	  'mod'     buffer has been modified
'more'			    pause listings when the whole screen is filled
'mouse'			    enable the use of mouse clicks
'mousefocus'	  'mousef'  keyboard focus follows the mouse
'mousehide'	  'mh'	    hide mouse pointer while typing
'mousemodel'	  'mousem'  changes meaning of mouse buttons
'mousemoveevent'  'mousemev'  report mouse moves with <MouseMove>
'mouseshape'	  'mouses'  shape of the mouse pointer in different modes
'mousetime'	  'mouset'  max time between mouse double-click
'mzquantum'	  'mzq'     the interval between polls for MzScheme threads
'mzschemedll'		    name of the MzScheme dynamic library
'mzschemegcdll'		    name of the MzScheme dynamic library for GC
'nrformats'	  'nf'	    number formats recognized for CTRL-A command
'number'	  'nu'	    print the line number in front of each line
'numberwidth'	  'nuw'     number of columns used for the line number
'omnifunc'	  'ofu'     function for filetype-specific completion
'opendevice'	  'odev'    allow reading/writing devices on MS-Windows
'operatorfunc'	  'opfunc'  function to be called for g@ operator
'osfiletype'	  'oft'     no longer supported
'packpath'	  'pp'      list of directories used for packages
'paragraphs'	  'para'    nroff macros that separate paragraphs
'paste'			    allow pasting text
'pastetoggle'	  'pt'	    key code that causes 'paste' to toggle
'patchexpr'	  'pex'     expression used to patch a file
'patchmode'	  'pm'	    keep the oldest version of a file
'path'		  'pa'	    list of directories searched with "gf" et.al.
'perldll'		    name of the Perl dynamic library
'preserveindent'  'pi'	    preserve the indent structure when reindenting
'previewheight'   'pvh'     height of the preview window
'previewpopup'    'pvp'     use popup window for preview
'previewwindow'   'pvw'     identifies the preview window
'printdevice'	  'pdev'    name of the printer to be used for :hardcopy
'printencoding'   'penc'    encoding to be used for printing
'printexpr'	  'pexpr'   expression used to print PostScript for :hardcopy
'printfont'	  'pfn'     name of the font to be used for :hardcopy
'printheader'	  'pheader' format of the header used for :hardcopy
'printmbcharset'  'pmbcs'   CJK character set to be used for :hardcopy
'printmbfont'	  'pmbfn'   font names to be used for CJK output of :hardcopy
'printoptions'	  'popt'    controls the format of :hardcopy output
'prompt'	  'prompt'  enable prompt in Ex mode
'pumheight'	  'ph'	    maximum height of the popup menu
'pumwidth'	  'pw'	    minimum width of the popup menu
'pythondll'		    name of the Python 2 dynamic library
'pythonhome'		    name of the Python 2 home directory
'pythonthreedll'	    name of the Python 3 dynamic library
'pythonthreehome'	    name of the Python 3 home directory
'pyxversion'	  'pyx'	    Python version used for pyx* commands
'quickfixtextfunc' 'qftf'   function for the text in the quickfix window
'quoteescape'	  'qe'	    escape characters used in a string
'readonly'	  'ro'	    disallow writing the buffer
'redrawtime'	  'rdt'     timeout for 'hlsearch' and :match highlighting
'regexpengine'	  're'	    default regexp engine to use
'relativenumber'  'rnu'	    show relative line number in front of each line
'remap'			    allow mappings to work recursively
'renderoptions'	  'rop'	    options for text rendering on Windows
'report'		    threshold for reporting nr. of lines changed
'restorescreen'   'rs'	    Win32: restore screen when exiting
'revins'	  'ri'	    inserting characters will work backwards
'rightleft'	  'rl'	    window is right-to-left oriented
'rightleftcmd'	  'rlc'     commands for which editing works right-to-left
'rubydll'		    name of the Ruby dynamic library
'ruler'		  'ru'	    show cursor line and column in the status line
'rulerformat'	  'ruf'     custom format for the ruler
'runtimepath'	  'rtp'     list of directories used for runtime files
'scroll'	  'scr'     lines to scroll with CTRL-U and CTRL-D
'scrollbind'	  'scb'     scroll in window as other windows scroll
'scrollfocus'	  'scf'     scroll wheel applies to window under pointer
'scrolljump'	  'sj'	    minimum number of lines to scroll
'scrolloff'	  'so'	    minimum nr. of lines above and below cursor
'scrollopt'	  'sbo'     how 'scrollbind' should behave
'sections'	  'sect'    nroff macros that separate sections
'secure'		    secure mode for reading .vimrc in current dir
'selection'	  'sel'     what type of selection to use
'selectmode'	  'slm'     when to use Select mode instead of Visual mode
'sessionoptions'  'ssop'    options for :mksession
'shell'		  'sh'	    name of shell to use for external commands
'shellcmdflag'	  'shcf'    flag to shell to execute one command
'shellpipe'	  'sp'	    string to put output of ":make" in error file
'shellquote'	  'shq'     quote character(s) for around shell command
'shellredir'	  'srr'     string to put output of filter in a temp file
'shellslash'	  'ssl'     use forward slash for shell file names
'shelltemp'	  'stmp'    whether to use a temp file for shell commands
'shelltype'	  'st'	    Amiga: influences how to use a shell
'shellxescape'	  'sxe'     characters to escape when 'shellxquote' is (
'shellxquote'	  'sxq'     like 'shellquote', but include redirection
'shiftround'	  'sr'	    round indent to multiple of shiftwidth
'shiftwidth'	  'sw'	    number of spaces to use for (auto)indent step
'shortmess'	  'shm'     list of flags, reduce length of messages
'shortname'	  'sn'	    Filenames assumed to be 8.3 chars
'showbreak'	  'sbr'     string to use at the start of wrapped lines
'showcmd'	  'sc'	    show (partial) command somewhere
'showcmdloc'	  'sloc'    where to show (partial) command
'showfulltag'	  'sft'     show full tag pattern when completing tag
'showmatch'	  'sm'	    briefly jump to matching bracket if insert one
'showmode'	  'smd'     message on status line to show current mode
'showtabline'	  'stal'    tells when the tab pages line is displayed
'sidescroll'	  'ss'	    minimum number of columns to scroll horizontal
'sidescrolloff'   'siso'    min. nr. of columns to left and right of cursor
'signcolumn'	  'scl'	    when to display the sign column
'smartcase'	  'scs'     no ignore case when pattern has uppercase
'smartindent'	  'si'	    smart autoindenting for C programs
'smarttab'	  'sta'     use 'shiftwidth' when inserting <Tab>
'smoothscroll'	  'sms'     scroll by screen lines when 'wrap' is set
'softtabstop'	  'sts'     number of spaces that <Tab> uses while editing
'spell'			    enable spell checking
'spellcapcheck'   'spc'     pattern to locate end of a sentence
'spellfile'	  'spf'     files where zg and zw store words
'spelllang'	  'spl'     language(s) to do spell checking for
'spelloptions'	  'spo'     options for spell checking
'spellsuggest'	  'sps'     method(s) used to suggest spelling corrections
'splitbelow'	  'sb'	    new window from split is below the current one
'splitkeep'	  'spk'     determines scroll behavior for split windows
'splitright'	  'spr'     new window is put right of the current one
'startofline'	  'sol'     commands move cursor to first non-blank in line
'statusline'	  'stl'     custom format for the status line
'suffixes'	  'su'	    suffixes that are ignored with multiple match
'suffixesadd'	  'sua'     suffixes added when searching for a file
'swapfile'	  'swf'     whether to use a swapfile for a buffer
'swapsync'	  'sws'     how to sync the swap file
'switchbuf'	  'swb'     sets behavior when switching to another buffer
'synmaxcol'	  'smc'     maximum column to find syntax items
'syntax'	  'syn'     syntax to be loaded for current buffer
'tabline'	  'tal'     custom format for the console tab pages line
'tabpagemax'	  'tpm'     maximum number of tab pages for -p and "tab all"
'tabstop'	  'ts'	    number of spaces that <Tab> in file uses
'tagbsearch'	  'tbs'     use binary searching in tags files
'tagcase'	  'tc'      how to handle case when searching in tags files
'tagfunc'	  'tfu'	    function to get list of tag matches
'taglength'	  'tl'	    number of significant characters for a tag
'tagrelative'	  'tr'	    file names in tag file are relative
'tags'		  'tag'     list of file names used by the tag command
'tagstack'	  'tgst'    push tags onto the tag stack
'tcldll'		    name of the Tcl dynamic library
'term'			    name of the terminal
'termbidi'	  'tbidi'   terminal takes care of bi-directionality
'termencoding'	  'tenc'    character encoding used by the terminal
'termguicolors'	  'tgc'     use GUI colors for the terminal
'termwinkey'	  'twk'	    key that precedes a Vim command in a terminal
'termwinscroll'   'twsl'    max number of scrollback lines in a terminal window
'termwinsize'	  'tws'	    size of a terminal window
'termwintype'	  'twt'	    MS-Windows: type of pty to use for terminal window
'terse'			    shorten some messages
'textauto'	  'ta'	    obsolete, use 'fileformats'
'textmode'	  'tx'	    obsolete, use 'fileformat'
'textwidth'	  'tw'	    maximum width of text that is being inserted
'thesaurus'	  'tsr'     list of thesaurus files for keyword completion
'thesaurusfunc'	  'tsrfu'   function to be used for thesaurus completion
'tildeop'	  'top'     tilde command "~" behaves like an operator
'timeout'	  'to'	    time out on mappings and key codes
'timeoutlen'	  'tm'	    time out time in milliseconds
'title'			    let Vim set the title of the window
'titlelen'		    percentage of 'columns' used for window title
'titleold'		    old title, restored when exiting
'titlestring'		    string to use for the Vim window title
'toolbar'	  'tb'	    GUI: which items to show in the toolbar
'toolbariconsize' 'tbis'    size of the toolbar icons (for GTK 2 only)
'ttimeout'		    time out on mappings
'ttimeoutlen'	  'ttm'     time out time for key codes in milliseconds
'ttybuiltin'	  'tbi'     use built-in termcap before external termcap
'ttyfast'	  'tf'	    indicates a fast terminal connection
'ttymouse'	  'ttym'    type of mouse codes generated
'ttyscroll'	  'tsl'     maximum number of lines for a scroll
'ttytype'	  'tty'     alias for 'term'
'undodir'	  'udir'    where to store undo files
'undofile'	  'udf'	    save undo information in a file
'undolevels'	  'ul'	    maximum number of changes that can be undone
'undoreload'	  'ur'	    max nr of lines to save for undo on a buffer reload
'updatecount'	  'uc'	    after this many characters flush swap file
'updatetime'	  'ut'	    after this many milliseconds flush swap file
'varsofttabstop'  'vsts'    a list of number of spaces when typing <Tab>
'vartabstop'	  'vts'	    a list of number of spaces for <Tab>s
'verbose'	  'vbs'     give informative messages
'verbosefile'	  'vfile'   file to write messages in
'viewdir'	  'vdir'    directory where to store files with :mkview
'viewoptions'	  'vop'     specifies what to save for :mkview
'viminfo'	  'vi'	    use .viminfo file upon startup and exiting
'viminfofile'	  'vif'	    file name used for the viminfo file
'virtualedit'	  've'	    when to use virtual editing
'visualbell'	  'vb'	    use visual bell instead of beeping
'warn'			    warn for shell command when buffer was changed
'weirdinvert'	  'wiv'	    for terminals that have weird inversion method
'whichwrap'	  'ww'	    allow specified keys to cross line boundaries
'wildchar'	  'wc'	    command-line character for wildcard expansion
'wildcharm'	  'wcm'     like 'wildchar' but also works when mapped
'wildignore'	  'wig'     files matching these patterns are not completed
'wildignorecase'  'wic'     ignore case when completing file names
'wildmenu'	  'wmnu'    use menu for command line completion
'wildmode'	  'wim'     mode for 'wildchar' command-line expansion
'wildoptions'	  'wop'     specifies how command line completion is done
'winaltkeys'	  'wak'     when the windows system handles ALT keys
'wincolor'	  'wcr'	    window-local highlighting
'window'	  'wi'	    nr of lines to scroll for CTRL-F and CTRL-B
'winfixheight'	  'wfh'     keep window height when opening/closing windows
'winfixwidth'	  'wfw'     keep window width when opening/closing windows
'winheight'	  'wh'	    minimum number of lines for the current window
'winminheight'	  'wmh'     minimum number of lines for any window
'winminwidth'	  'wmw'     minimal number of columns for any window
'winptydll'		    name of the winpty dynamic library
'winwidth'	  'wiw'     minimal number of columns for current window
'wrap'			    long lines wrap and continue on the next line
'wrapmargin'	  'wm'	    chars from the right where wrapping starts
'wrapscan'	  'ws'	    searches wrap around the end of the file
'write'			    writing to a file is allowed
'writeany'	  'wa'	    write to file with no need for "!" override
'writebackup'	  'wb'	    make a backup before overwriting a file
'writedelay'	  'wd'	    delay this many msec for each char (for debug)
'xtermcodes'		    request terminal codes from an xterm
