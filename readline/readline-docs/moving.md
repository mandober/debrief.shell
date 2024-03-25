 bash | man | readline



Commands for Moving

beginning-of-line (C-a)	Move to the start of the current line.
end-of-line (C-e)		Move to the end of the line.
forward-char (C-f)		Move forward a character.
backward-char (C-b)		Move back a character.

forward-word (M-f)		Move forward to the end of the next word *
backward-word (M-b)		Move back to the start of the current or previous word *
shell-forward-word 		Move forward to the end of the next word **
shell-backward-word		Move back to the start of the current or previous word **

clear-screen (C-l)		Clear screen leaving current line at top of the screen. With an argument, refresh current line without clearing screen.
redraw-current-line		Refresh the current line.

* Words are composed of alphanumeric characters (letters and digits).
** Words are delimited by non-quoted shell metacharacters.

