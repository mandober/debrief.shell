# Command-line editing

https://vimhelp.org/index.txt.html#ex-edit-index

Get to the command-line with the ':', '!', '/' or '?' commands.
Normal characters are inserted at the current cursor position.
"Completion" below refers to context-sensitive completion.  It will complete
file names, tags, commands etc. as appropriate.


```
tag		command		action in Command-line editing mode	
------------------------------------------------------------------------------
		CTRL-@		not used
c_CTRL-A  	CTRL-A		do completion on the pattern in front of the
				cursor and insert all matches
c_CTRL-B  	CTRL-B		cursor to begin of command-line
c_CTRL-C  	CTRL-C		same as <Esc>
c_CTRL-D  	CTRL-D		list completions that match the pattern in
				front of the cursor
c_CTRL-E  	CTRL-E		cursor to end of command-line
'cedit'  	CTRL-F		default value for 'cedit': opens the
				command-line window; otherwise not used
c_CTRL-G  	CTRL-G		next match when 'incsearch' is active
c_<BS>  	<BS>		delete the character in front of the cursor
c_digraph  	{char1} <BS> {char2}
				enter digraph when 'digraph' is on
c_CTRL-H  	CTRL-H		same as <BS>
c_<Tab>  	<Tab>		if 'wildchar' is <Tab>: Do completion on
				the pattern in front of the cursor
c_<S-Tab>  	<S-Tab>		same as CTRL-P
c_wildchar  	'wildchar'	Do completion on the pattern in front of the
				cursor (default: <Tab>)
c_CTRL-I  	CTRL-I		same as <Tab>
c_<NL>  	<NL>		same as <CR>
c_CTRL-J  	CTRL-J		same as <CR>
c_CTRL-K  	CTRL-K {char1} {char2}
				enter digraph
c_CTRL-L  	CTRL-L		do completion on the pattern in front of the
				cursor and insert the longest common part
c_<CR>  	<CR>		execute entered command
c_CTRL-M  	CTRL-M		same as <CR>
c_CTRL-N  	CTRL-N		after using 'wildchar' with multiple matches:
				go to next match, otherwise: recall older
				command-line from history.
		CTRL-O		not used
c_CTRL-P  	CTRL-P		after using 'wildchar' with multiple matches:
				go to previous match, otherwise: recall older
				command-line from history.
c_CTRL-Q  	CTRL-Q		same as CTRL-V, unless it's used for terminal
				control flow
c_CTRL-R  	CTRL-R {regname}
				insert the contents of a register or object
				under the cursor as if typed
c_CTRL-R_CTRL-R CTRL-R CTRL-R {regname}
c_CTRL-R_CTRL-O CTRL-R CTRL-O {regname}
				insert the contents of a register or object
				under the cursor literally
		CTRL-S		not used, or used for terminal control flow
c_CTRL-T  	CTRL-T		previous match when 'incsearch' is active
c_CTRL-U  	CTRL-U		remove all characters
c_CTRL-V  	CTRL-V		insert next non-digit literally, insert three
				digit decimal number as a single byte.
c_CTRL-W  	CTRL-W		delete the word in front of the cursor
		CTRL-X		not used (reserved for completion)
		CTRL-Y		copy (yank) modeless selection
		CTRL-Z		not used (reserved for suspend)
c_<Esc>  	<Esc>		abandon command-line without executing it
c_CTRL-[  	CTRL-[		same as <Esc>
c_CTRL-\_CTRL-N CTRL-\ CTRL-N  	go to Normal mode, abandon command-line
c_CTRL-\_CTRL-G CTRL-\ CTRL-G  	go to mode specified with 'insertmode',
				abandon command-line
		CTRL-\ a - d	reserved for extensions
c_CTRL-\_e  	CTRL-\ e {expr} replace the command line with the result of
				{expr}
		CTRL-\ f - z	reserved for extensions
		CTRL-\ others	not used
c_CTRL-]  	CTRL-]		trigger abbreviation
c_CTRL-^  	CTRL-^		toggle use of :lmap mappings
c_CTRL-_  	CTRL-_		when 'allowrevins' set: change language
				(Hebrew, Farsi)
c_<Del>  	<Del>		delete the character under the cursor

c_<Left>  	<Left>		cursor left
c_<S-Left>  	<S-Left>	cursor one word left
c_<C-Left>  	<C-Left>	cursor one word left
c_<Right>  	<Right>		cursor right
c_<S-Right>  	<S-Right>	cursor one word right
c_<C-Right>  	<C-Right>	cursor one word right
c_<Up>  	<Up>		recall previous command-line from history that
				matches pattern in front of the cursor
c_<S-Up>  	<S-Up>		recall previous command-line from history
c_<Down>  	<Down>		recall next command-line from history that
				matches pattern in front of the cursor
c_<S-Down>  	<S-Down>	recall next command-line from history
c_<Home>  	<Home>		cursor to start of command-line
c_<End>  	<End>		cursor to end of command-line
c_<PageDown>  	<PageDown>	same as <S-Down>
c_<PageUp>  	<PageUp>	same as <S-Up>
c_<Insert>  	<Insert>	toggle insert/overstrike mode
c_<LeftMouse>  	<LeftMouse>	cursor at mouse click

commands in wildmenu mode (see 'wildmenu')

		<Up>		move up to parent / select the previous match
		<Down>		move down to submenu / select the next match
		<Left>		select the previous match / move up to parent
		<Right>		select the next match / move down to submenu
		<CR>		move into submenu when doing menu completion
		CTRL-E		stop completion and go back to original text
		CTRL-Y		accept selected match and stop completion
		other		stop completion and insert the typed character

commands in wildmenu mode with 'wildoptions' set to "pum"

		<PageUp>	select a match several entries back
		<PageDown>	select a match several entries forward
```
