# EX commands

https://vimhelp.org/index.txt.html#ex-cmd-index

This is a brief but complete listing of all the ex (`:`) commands, without mentioning any arguments. The optional part of the command name is inside the brackets. The commands are sorted on the non-optional part of their name.


COMMAND          | ACTION
-----------------|------------------------------------------------------------
:                | nothing
:{range}         | go to last line in {range}
:!               | filter lines or execute an external command
:!!              | repeat last ":!" command
:#               | same as ":number"
:&               | repeat last ":substitute"
:*               | use the last Visual area, like `:'<,'>`
:<               | shift lines one 'shiftwidth' left
:>               | shift lines one 'shiftwidth' right
:=               | print the last line number
:@               | execute contents of a register
:@@              | repeat the previous `:@`
:N[ext]          | go to previous file in the Argument List
:P[rint]         | print lines
:X               | ask for encryption key
:a[ppend]        | append text
:ab[breviate]    | enter abbreviation
:abc[lear]       | remove all abbreviations
:abo[veleft]     | make split window appear left or above
:al[l]           | open a window for each file in the Argument List
:am[enu]         | enter new menu item for all modes
:an[oremenu]     | enter a new menu for all modes that will not be remapped
:ar[gs]          | print the Argument List
:arga[dd]        | add items to the Argument List
:argded[upe]     | remove duplicates from the Argument List
:argd[elete]     | delete items from the Argument List
:arge[dit]       | add item to the Argument List and edit it
:argdo           | do a command on all items in the Argument List
:argg[lobal]     | define the global Argument List
:argl[ocal]      | define a local Argument List
:argu[ment]      | go to specific file in the Argument List
:as[cii]         | print ascii value of character under the cursor
:au[tocmd]       | enter or show autocommands
:aug[roup]       | select the autocommand group to use
:aun[menu]       | remove menu for all modes
:b[uffer]        | go to specific buffer in Buffer List
:bN[ext]         | go to previous buffer in Buffer List
:ba[ll]          | open a window for each buffer in Buffer List
:bad[d]          | add buffer to Buffer List
:balt            | like ":badd" but also set the alternate file
:bd[elete]       | remove a buffer from Buffer List
:be[have]        | set mouse and selection behavior
:bel[owright]    | make split window appear right or below
:bf[irst]        | go to first buffer in Buffer List
:bl[ast]         | go to last buffer in Buffer List
:bm[odified]     | go to next buffer in Buffer List that has been modified
:bn[ext]         | go to next buffer in Buffer List
:bo[tright]      | make split window appear at bottom or far right
:bp[revious]     | go to previous buffer in Buffer List
:br[ewind]       | go to first buffer in Buffer List
:brea[k]         | break out of while loop
:breaka[dd]      | add a debugger breakpoint
:breakd[el]      | delete a debugger breakpoint
:breakl[ist]     | list debugger breakpoints
:bro[wse]        | use file selection dialog
:bufdo           | execute command in each listed buffer
:buffers         | list all files in Buffer List
:bun[load]       | unload a specific buffer
:bw[ipeout]      | really delete a buffer
:c[hange]        | replace a line or series of lines
:cN[ext]         | go to previous error
:cNf[ile]        | go to last error in previous file
:ca[bbrev]       | like ":abbreviate" but for Command-line mode
:cabc[lear]      | clear all abbreviations for Command-line mode
:cabo[ve]        | go to error above current line
:cad[dbuffer]    | add errors from buffer
:cadde[xpr]      | add errors from expr
:caddf[ile]      | add error message to current Quickfix List
:caf[ter]        | go to error after current cursor
:cal[l]          | call a function
:cat[ch]         | part of a :try command
:cbef[ore]       | go to error before current cursor
:cbel[ow]        | go to error below current line
:cbo[ttom]       | scroll to the bottom of the quickfix window
:cb[uffer]       | parse error messages and jump to first error
:cc              | go to specific error
:ccl[ose]        | close quickfix window
:cd              | change directory
:cdo             | execute command in each valid Error List entry
:cfd[o]          | execute command in each file in Error List
:ce[nter]        | format lines at the center
:cex[pr]         | read errors from expr and jump to first
:cf[ile]         | read file with error messages and jump to first
:cfir[st]        | go to the specified error, default first one
:cgetb[uffer]    | get errors from buffer
:cgete[xpr]      | get errors from expr
:cg[etfile]      | read file with error messages
:changes         | print the change list
:chd[ir]         | change directory
:che[ckpath]     | list included files
:checkt[ime]     | check timestamp of loaded buffers
:chi[story]      | list the Error Lists
:class           | start of a class specification
:cla[st]         | go to the specified error, default last one
:cle[arjumps]    | clear the jump list
:cl[ist]         | list all errors
:clo[se]         | close current window
:cm[ap]          | like ":map" but for Command-line mode
:cmapc[lear]     | clear all mappings for Command-line mode
:cme[nu]         | add menu for Command-line mode
:cn[ext]         | go to next error
:cnew[er]        | go to newer Error List
:cnf[ile]        | go to first error in next file
:cno[remap]      | like ":noremap" but for Command-line mode
:cnorea[bbrev]   | like ":noreabbrev" but for Command-line mode
:cnoreme[nu]     | like ":noremenu" but for Command-line mode
:co[py]          | copy lines
:col[der]        | go to older Error List
:colo[rscheme]   | load a specific color scheme
:com[mand]       | create user-defined command
:comc[lear]      | clear all user-defined commands
:comp[iler]      | do settings for a specific compiler
:con[tinue]      | go back to :while
:conf[irm]       | prompt user when confirmation required
:cons[t]         | create a variable as a constant
:cope[n]         | open quickfix window
:cp[revious]     | go to previous error
:cpf[ile]        | go to last error in previous file
:cq[uit]         | quit Vim with an error code
:cr[ewind]       | go to the specified error, default first one
:cs[cope]        | execute cscope command
:cst[ag]         | use cscope to jump to a tag
:cu[nmap]        | like ":unmap" but for Command-line mode
:cuna[bbrev]     | like ":unabbrev" but for Command-line mode
:cunme[nu]       | remove menu for Command-line mode
:cw[indow]       | open or close quickfix window
:d[elete]        | delete lines
:deb[ug]         | run a command in debugging mode
:debugg[reedy]   | read debug mode commands from normal input
:def             | define a Vim9 user function
:defc[ompile]    | compile Vim9 user functions in current script
:defer           | call function when current function is done
:delc[ommand]    | delete user-defined command
:delf[unction]   | delete a user function
:delm[arks]      | delete marks
:dif[fupdate]    | update 'diff' buffers
:diffg[et]       | remove differences in current buffer
:diffo[ff]       | switch off diff mode
:diffp[atch]     | apply a patch and show differences
:diffpu[t]       | remove differences in other buffer
:diffs[plit]     | show differences with another file
:diffthis        | make current window a diff window
:dig[raphs]      | show or enter digraphs
:di[splay]       | display registers
:disa[ssemble]   | disassemble Vim9 user function
:dj[ump]         | jump to #define
:dl              | short for :delete with the 'l' flag
:dli[st]         | list #defines
:do[autocmd]     | apply autocommands to current buffer
:doautoa[ll]     | apply autocommands for all loaded buffers
:d[elete]p       | short for :delete with the 'p' flag
:dr[op]          | jump to window editing file or edit file in current window
:ds[earch]       | list one #define
:dsp[lit]        | split window and jump to #define
:e[dit]          | edit a file
:ea[rlier]       | go to older change, undo
:ec[ho]          | echoes the result of expressions
:echoc[onsole]   | like :echomsg but write to stdout
:echoe[rr]       | like :echo, show like an error and use history
:echoh[l]        | set highlighting for echo commands
:echom[sg]       | same as :echo, put message in history
:echon           | same as :echo, but without <EOL>
:echow[indow]    | same as :echomsg, but use a popup window
:el[se]          | part of an :if command
:elsei[f]        | part of an :if command
:em[enu]         | execute a menu by name
:endclass        | end of a class specification
:enddef          | end of a user function started with :def
:en[dif]         | end previous :if
:endfo[r]        | end previous :for
:endf[unction]   | end of a user function started with :function
:endt[ry]        | end previous :try
:endw[hile]      | end previous :while
:ene[w]          | edit a new, unnamed buffer
:ev[al]          | evaluate an expression and discard the result
:ex              | same as ":edit"
:exe[cute]       | execute result of expressions
:exi[t]          | same as ":xit"
:exp[ort]        | Vim9: export an item from a script
:exu[sage]       | overview of Ex commands
:f[ile]          | show or set the current file name
:files           | list all files in Buffer List
:filet[ype]      | switch file type detection on/off
:filt[er]        | filter output of following command
:fin[d]          | find file in 'path' and edit it
:final           | declare an immutable variable in Vim9
:fina[lly]       | part of a :try command
:fini[sh]        | quit sourcing a Vim script
:fir[st]         | go to the first file in the Argument List
:fix[del]        | set key code of <Del>
:fo[ld]          | create a fold
:foldc[lose]     | close folds
:foldd[oopen]    | execute command on lines not in a closed fold
:folddoc[losed]  | execute command on lines in a closed fold
:foldo[pen]      | open folds
:for             | for loop
:fu[nction]      | define a user function
:g[lobal]        | execute commands for matching lines
:go[to]          | go to byte in the buffer
:gr[ep]          | run 'grepprg' and jump to first match
:grepa[dd]       | like :grep, but append to current list
:gu[i]           | start the GUI
:gv[im]          | start the GUI
:ha[rdcopy]      | send text to the printer
:h[elp]          | open a help window
:helpc[lose]     | close one help window
:helpf[ind]      | dialog to open a help window
:helpg[rep]      | like ":grep" but searches help files
:helpt[ags]      | generate help tags for a directory
:hi[ghlight]     | specify highlighting methods
:hid[e]          | hide current buffer for a command
:his[tory]       | print a history list
:hor[izontal]    | following window command work horizontally
:i[nsert]        | insert text
:ia[bbrev]       | like ":abbrev" but for Insert mode
:iabc[lear]      | like ":abclear" but for Insert mode
:if              | execute commands when condition met
:ij[ump]         | jump to definition of identifier
:il[ist]         | list lines where identifier matches
:im[ap]          | like ":map" but for Insert mode
:imapc[lear]     | like ":mapclear" but for Insert mode
:ime[nu]         | add menu for Insert mode
:imp[ort]        | Vim9: import an item from another script
:ino[remap]      | like ":noremap" but for Insert mode
:inorea[bbrev]   | like ":noreabbrev" but for Insert mode
:inoreme[nu]     | like ":noremenu" but for Insert mode
:int[ro]         | print the introductory message
:is[earch]       | list one line where identifier matches
:isp[lit]        | split window and jump to definition of identifier
:iu[nmap]        | like ":unmap" but for Insert mode
:iuna[bbrev]     | like ":unabbrev" but for Insert mode
:iunme[nu]       | remove menu for Insert mode
:j[oin]          | join lines
:ju[mps]         | print the jump list
:k               | set a mark
:keepa[lt]       | following command keeps the alternate file
:kee[pmarks]     | following command keeps marks where they are
:keepj[umps]     | following command keeps jumplist and marks
:keepp[atterns]  | following command keeps search pattern history
:lN[ext]         | go to previous entry in location list
:lNf[ile]        | go to last entry in previous file
:l[ist]          | print lines
:lab[ove]        | go to location above current line
:lad[dexpr]      | add locations from expr
:laddb[uffer]    | add locations from buffer
:laddf[ile]      | add locations to current location list
:laf[ter]        | go to location after current cursor
:la[st]          | go to the last file in the Argument List
:lan[guage]      | set the language (locale)
:lat[er]         | go to newer change, redo
:lbef[ore]       | go to location before current cursor
:lbel[ow]        | go to location below current line
:lbo[ttom]       | scroll to the bottom of the location window
:lb[uffer]       | parse locations and jump to first location
:lc[d]           | change directory locally
:lch[dir]        | change directory locally
:lcl[ose]        | close location window
:lcs[cope]       | like ":cscope" but uses location list
:ld[o]           | execute command in valid location list entries
:lfd[o]          | execute command in each file in location list
:le[ft]          | left align lines
:lefta[bove]     | make split window appear left or above
:leg[acy]        | make following command use legacy script syntax
:let             | assign a value to a variable or option
:lex[pr]         | read locations from expr and jump to first
:lf[ile]         | read file with locations and jump to first
:lfir[st]        | go to the specified location, default first one
:lgetb[uffer]    | get locations from buffer
:lgete[xpr]      | get locations from expr
:lg[etfile]      | read file with locations
:lgr[ep]         | run 'grepprg' and jump to first match
:lgrepa[dd]      | like :grep, but append to current list
:lh[elpgrep]     | like ":helpgrep" but uses location list
:lhi[story]      | list the location lists
:ll              | go to specific location
:lla[st]         | go to the specified location, default last one
:lli[st]         | list all locations
:lmak[e]         | execute external command 'makeprg' and parse error messages
:lm[ap]          | like ":map!" but includes Lang-Arg mode
:lmapc[lear]     | like ":mapclear!" but includes Lang-Arg mode
:lne[xt]         | go to next location
:lnew[er]        | go to newer location list
:lnf[ile]        | go to first location in next file
:ln[oremap]      | like ":noremap!" but includes Lang-Arg mode
:loadk[eymap]    | load the following keymaps until EOF
:lo[adview]      | load view for current window from a file
:loc[kmarks]     | following command keeps marks where they are
:lockv[ar]       | lock variables
:lol[der]        | go to older location list
:lope[n]         | open location window
:lp[revious]     | go to previous location
:lpf[ile]        | go to last location in previous file
:lr[ewind]       | go to the specified location, default first one
:ls              | list all buffers
:lt[ag]          | jump to tag and add matching tags to the location list
:lu[nmap]        | like ":unmap!" but includes Lang-Arg mode
:lua             | execute Lua command
:luad[o]         | execute Lua command for each line
:luaf[ile]       | execute Lua script file
:lv[imgrep]      | search for pattern in files
:lvimgrepa[dd]   | like :vimgrep, but append to current list
:lw[indow]       | open or close location window
:m[ove]          | move lines
:ma[rk]          | set a mark
:mak[e]          | execute external command 'makeprg' and parse error messages
:map             | show or enter a mapping
:mapc[lear]      | clear all mappings for Normal and Visual mode
:marks           | list all marks
:mat[ch]         | define a match to highlight
:me[nu]          | enter a new menu item
:menut[ranslate] |  add a menu translation item
:mes[sages]      | view previously displayed messages
:mk[exrc]        | write current mappings and settings to a file
:mks[ession]     | write session info to a file
:mksp[ell]       | produce .spl spell file
:mkv[imrc]       | write current mappings and settings to a file
:mkvie[w]        | write view of current window to a file
:mod[e]          | show or change the screen mode
:mz[scheme]      | execute MzScheme command
:mzf[ile]        | execute MzScheme script file
:nbc[lose]       | close the current Netbeans session
:nb[key]         | pass a key to Netbeans
:nbs[art]        | start a new Netbeans session
:n[ext]          | go to next file in the Argument List
:new             | create a new empty window
:nm[ap]          | like ":map" but for Normal mode
:nmapc[lear]     | clear all mappings for Normal mode
:nme[nu]         | add menu for Normal mode
:nn[oremap]      | like ":noremap" but for Normal mode
:nnoreme[nu]     | like ":noremenu" but for Normal mode
:noa[utocmd]     | following commands don't trigger autocommands
:no[remap]       | enter a mapping that will not be remapped
:noh[lsearch]    | suspend 'hlsearch' highlighting
:norea[bbrev]    | enter an abbreviation that will not be remapped
:noreme[nu]      | enter a menu that will not be remapped
:norm[al]        | execute Normal mode commands
:nos[wapfile]    | following commands don't create a swap file
:nu[mber]        | print lines with line number
:nun[map]        | like ":unmap" but for Normal mode
:nunme[nu]       | remove menu for Normal mode
:ol[dfiles]      | list files that have marks in the viminfo file
:o[pen]          | start open mode (not implemented)
:om[ap]          | like ":map" but for Operator-pending mode
:omapc[lear]     | remove all mappings for Operator-pending mode
:ome[nu]         | add menu for Operator-pending mode
:on[ly]          | close all windows except the current one
:ono[remap]      | like ":noremap" but for Operator-pending mode
:onoreme[nu]     | like ":noremenu" but for Operator-pending mode
:opt[ions]       | open the options-window
:ou[nmap]        | like ":unmap" but for Operator-pending mode
:ounme[nu]       | remove menu for Operator-pending mode
:ow[nsyntax]     | set new local syntax highlight for this window
:pa[ckadd]       | add a plugin from 'packpath'
:packl[oadall]   | load all packages under 'packpath'
:pc[lose]        | close preview window
:ped[it]         | edit file in the preview window
:pe[rl]          | execute Perl command
:p[rint]         | print lines
:profd[el]       | stop profiling a function or script
:prof[ile]       | profiling functions and scripts
:pro[mptfind]    | open GUI dialog for searching
:promptr[epl]    | open GUI dialog for search/replace
:perld[o]        | execute Perl command for each line
:po[p]           | jump to older entry in tag stack
:popu[p]         | popup a menu by name
:pp[op]          | ":pop" in preview window
:pre[serve]      | write all text to swap file
:prev[ious]      | go to previous file in Argument List
:ps[earch]       | like ":ijump" but shows match in preview window
:pt[ag]          | show tag in preview window
:ptN[ext]        | :tNext in preview window
:ptf[irst]       | :trewind in preview window
:ptj[ump]        | :tjump and show tag in preview window
:ptl[ast]        | :tlast in preview window
:ptn[ext]        | :tnext in preview window
:ptp[revious]    | :tprevious in preview window
:ptr[ewind]      | :trewind in preview window
:pts[elect]      | :tselect and show tag in preview window
:public          | prefix for a class or object member
:pu[t]           | insert contents of register in the text
:pw[d]           | print current directory
:py3             | execute Python 3 command
:python3         | same as :py3
:py3d[o]         | execute Python 3 command for each line
:py3f[ile]       | execute Python 3 script file
:py[thon]        | execute Python command
:pyd[o]          | execute Python command for each line
:pyf[ile]        | execute Python script file
:pyx             | execute python_x command
:pythonx         | same as :pyx
:pyxd[o]         | execute python_x command for each line
:pyxf[ile]       | execute python_x script file
:q[uit]          | quit current window (when one window quit Vim)
:quita[ll]       | quit Vim
:qa[ll]          | quit Vim
:r[ead]          | read file into the text
:rec[over]       | recover a file from a swap file
:red[o]          | redo one undone change
:redi[r]         | redirect messages to a file or register
:redr[aw]        |   force a redraw of the display
:redraws[tatus]  |   force a redraw of the status line(s)
:redrawt[abline] |   force a redraw of the tabline
:reg[isters]     | display the contents of registers
:res[ize]        | change current window height
:ret[ab]         | change tab size
:retu[rn]        | return from a user function
:rew[ind]        | go to the first file in the Argument List
:ri[ght]         | right align text
:rightb[elow]    | make split window appear right or below
:rub[y]          | execute Ruby command
:rubyd[o]        | execute Ruby command for each line
:rubyf[ile]      | execute Ruby script file
:rund[o]         | read undo information from a file
:ru[ntime]       | source vim scripts in 'runtimepath'
:rv[iminfo]      | read from viminfo file
:s[ubstitute]    | find and replace text
:sN[ext]         | split window and go to previous file in Argument List
:san[dbox]       | execute a command in the sandbox
:sa[rgument]     | split window and go to specific file in Argument List
:sal[l]          | open a window for each file in Argument List
:sav[eas]        | save file under another name.
:sb[uffer]       | split window and go to specific file in Buffer List
:sbN[ext]        | split window and go to previous file in Buffer List
:sba[ll]         | open a window for each file in Buffer List
:sbf[irst]       | split window and go to first file in Buffer List
:sbl[ast]        | split window and go to last file in Buffer List
:sbm[odified]    | split window and go to modified file in Buffer List
:sbn[ext]        | split window and go to next file in Buffer List
:sbp[revious]    | split window and go to previous file in Buffer List
:sbr[ewind]      | split window and go to first file in Buffer List
:scr[iptnames]   | list names of all sourced Vim scripts
:scripte[ncoding | ]  encoding used in sourced Vim script
:scriptv[ersion] |    version of Vim script used
:scs[cope]       | split window and execute cscope command
:se[t]           | show or set options
:setf[iletype]   | set 'filetype', unless it was set already
:setg[lobal]     | show global values of options
:setl[ocal]      | show or set options locally
:sf[ind]         | split current window and edit file in 'path'
:sfir[st]        | split window and go to first file in the Argument List
:sh[ell]         | escape to a shell
:sim[alt]        | Win32 GUI: simulate Windows ALT key
:sig[n]          | manipulate signs
:sil[ent]        | run a command silently
:sl[eep]         | do nothing for a few seconds
:sl[eep]!        | do nothing for a few seconds, without the cursor visible
:sla[st]         | split window and go to last file in the Argument List
:sm[agic]        | :substitute with 'magic'
:smap            | like ":map" but for Select mode
:smapc[lear]     | remove all mappings for Select mode
:sme[nu]         | add menu for Select mode
:smi[le]         | make the user happy
:sn[ext]         | split window and go to next file in the Argument List
:sno[magic]      | :substitute with 'nomagic'
:snor[emap]      | like ":noremap" but for Select mode
:snoreme[nu]     | like ":noremenu" but for Select mode
:sor[t]          | sort lines
:so[urce]        | read Vim or Ex commands from a file
:spelld[ump]     | split window and fill with all correct words
:spe[llgood]     | add good word for spelling
:spelli[nfo]     | show info about loaded spell files
:spellra[re]     | add rare word for spelling
:spellr[epall]   | replace all bad words like last z=
:spellu[ndo]     | remove good or bad word
:spellw[rong]    | add spelling mistake
:sp[lit]         | split current window
:spr[evious]     | split window and go to previous file in the Argument List
:sre[wind]       | split window and go to first file in the Argument List
:st[op]          | suspend the editor or escape to a shell
:sta[g]          | split window and jump to a tag
:star[tinsert]   | start Insert mode
:startg[replace] |  start Virtual Replace mode
:startr[eplace]  | start Replace mode
:static          | prefix for a class member or function
:stopi[nsert]    | stop Insert mode
:stj[ump]        | do ":tjump" and split window
:sts[elect]      | do ":tselect" and split window
:sun[hide]       | same as ":unhide"
:sunm[ap]        | like ":unmap" but for Select mode
:sunme[nu]       | remove menu for Select mode
:sus[pend]       | same as ":stop"
:sv[iew]         | split window and edit file read-only
:sw[apname]      | show the name of the current swap file
:sy[ntax]        | syntax highlighting
:synti[me]       | measure syntax highlighting speed
:sync[bind]      | sync scroll binding
:t               | same as ":copy"
:tN[ext]         | jump to previous matching tag
:tabN[ext]       | go to previous tab page
:tabc[lose]      | close current tab page
:tabdo           | execute command in each tab page
:tabe[dit]       | edit a file in a new tab page
:tabf[ind]       | find file in 'path', edit it in a new tab page
:tabfir[st]      | go to first tab page
:tabl[ast]       | go to last tab page
:tabm[ove]       | move tab page to other position
:tabnew          | edit a file in a new tab page
:tabn[ext]       | go to next tab page
:tabo[nly]       | close all tab pages except the current one
:tabp[revious]   | go to previous tab page
:tabr[ewind]     | go to first tab page
:tabs            | list the tab pages and what they contain
:tab             | create new tab when opening new window
:ta[g]           | jump to tag
:tags            | show the contents of the tag stack
:tc[d]           | change directory for tab page
:tch[dir]        | change directory for tab page
:tcl             | execute Tcl command
:tcld[o]         | execute Tcl command for each line
:tclf[ile]       | execute Tcl script file
:te[aroff]       | tear-off a menu
:ter[minal]      | open a terminal window
:tf[irst]        | jump to first matching tag
:th[row]         | throw an exception
:tj[ump]         | like ":tselect", but jump directly when there is one match
:tl[ast]         | jump to last matching tag
:tlm[enu]        | add menu for Terminal-Job mode
:tln[oremenu]    | like ":noremenu" but for Terminal-Job mode
:tlu[nmenu]      | remove menu for Terminal-Job mode
:tmapc[lear]     | remove all mappings for Terminal-Job mode
:tma[p]          | like ":map" but for Terminal-Job mode
:tm[enu]         | define menu tooltip
:tn[ext]         | jump to next matching tag
:tno[remap]      | like ":noremap" but for Terminal-Job mode
:to[pleft]       | make split window appear at top or far left
:tp[revious]     | jump to previous matching tag
:tr[ewind]       | jump to first matching tag
:try             | execute commands, abort on error or exception
:ts[elect]       | list matching tags and select one
:tunma[p]        | like ":unmap" but for Terminal-Job mode
:tu[nmenu]       | remove menu tooltip
:u[ndo]          | undo last change(s)
:undoj[oin]      | join next change with previous undo block
:undol[ist]      | list leafs of the undo tree
:una[bbreviate]  | remove abbreviation
:unh[ide]        | open a window for each loaded file in Buffer List
:unl[et]         | delete variable
:unlo[ckvar]     | unlock variables
:unm[ap]         | remove mapping
:unme[nu]        | remove menu
:uns[ilent]      | run a command not silently
:up[date]        | write buffer if modified
:v[global]       | execute commands for not matching lines
:var             | variable declaration in Vim9
:ve[rsion]       | print version number and other info
:verb[ose]       | execute command with 'verbose' set
:vert[ical]      | make following command split vertically
:vim9[cmd]       | make following command use Vim9 script syntax
:vim9s[cript]    | indicates Vim9 script file
:vim[grep]       | search for pattern in files
:vimgrepa[dd]    | like :vimgrep, but append to current list
:vi[sual]        | same as ":edit", but turns off "Ex" mode
:viu[sage]       | overview of Normal mode commands
:vie[w]          | edit a file read-only
:vm[ap]          | like ":map" but for Visual+Select mode
:vmapc[lear]     | remove all mappings for Visual+Select mode
:vme[nu]         | add menu for Visual+Select mode
:vne[w]          | create a new empty window, vertically split
:vn[oremap]      | like ":noremap" but for Visual+Select mode
:vnoreme[nu]     | like ":noremenu" but for Visual+Select mode
:vs[plit]        | split current window vertically
:vu[nmap]        | like ":unmap" but for Visual+Select mode
:vunme[nu]       | remove menu for Visual+Select mode
:windo           | execute command in each window
:w[rite]         | write to a file
:wN[ext]         | write to a file and go to previous file in Argument List
:wa[ll]          | write all (changed) buffers
:wh[ile]         | execute loop for as long as condition met
:wi[nsize]       | get or set window size (obsolete)
:winc[md]        | execute a Window (CTRL-W) command
:winp[os]        | get or set window position
:wn[ext]         | write to a file and go to next file in Argument List
:wp[revious]     | write to a file and go to previous file in Argument List
:wq              | write to a file and quit window or Vim
:wqa[ll]         | write all changed buffers and quit Vim
:wu[ndo]         | write undo information to a file
:wv[iminfo]      | write to viminfo file
:x[it]           | write if buffer changed and close window
:xa[ll]          | same as ":wqall"
:xmapc[lear]     | remove all mappings for Visual mode
:xm[ap]          | like ":map" but for Visual mode
:xme[nu]         | add menu for Visual mode
:xr[estore]      | restores the X server connection
:xn[oremap]      | like ":noremap" but for Visual mode
:xnoreme[nu]     | like ":noremenu" but for Visual mode
:xu[nmap]        | like ":unmap" but for Visual mode
:xunme[nu]       | remove menu for Visual mode
:y[ank]          | yank lines into a register
:z               | print some lines
:~               | repeat last ":substitute"
