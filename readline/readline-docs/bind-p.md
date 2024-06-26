# Readline functions and bindings

Display readline function names and bindings formatted for re-using.


```bash
bind -p


"\C-x\C-g": abort
"\C-x\C-e": edit-and-execute-command
"\C-x\C-r": re-read-init-file
"\C-x\C-u": undo
"\C-x\C-v": display-shell-version
"\C-x\C-x": exchange-point-and-mark
"\C-x\C-?": backward-kill-line

"\C-x(": 	start-kbd-macro
"\C-x)": 	end-kbd-macro
"\C-xe": 	call-last-kbd-macro

"\C-x*": 	glob-expand-word
"\C-xg": 	glob-list-expansions
"\C-x!": 	possible-command-completions

"\C-xA": 	do-lowercase-version ...



"\C-g": abort
"\C-x\C-g": abort
"\e\C-g": abort
"\C-j": accept-line
"\C-m": accept-line
# alias-expand-line (not bound)
# arrow-key-prefix (not bound)
# backward-byte (not bound)
"\C-b": backward-char
"\eOD": backward-char
"\e[D": backward-char
"\C-h": backward-delete-char
"\C-?": backward-delete-char
"\C-x\C-?": backward-kill-line
"\e\C-_": backward-kill-line
"\e\C-h": backward-kill-word
"\C-_": backward-kill-word
"\e[1;5D": backward-word
"\eb": backward-word
"\e<": beginning-of-history
"\C-a": beginning-of-line
"\eOH": beginning-of-line
"\e[H": beginning-of-line
"\C-xe": call-last-kbd-macro
"\ec": capitalize-word
"\C-]": character-search
"\e\C-]": character-search-backward
"\C-l": clear-screen
"\e\e": complete
"\eOP": complete

"\e!": complete-command
"\e/": complete-filename
"\e@": complete-hostname
"\e{": complete-into-braces
"\e~": complete-username
"\e$": complete-variable

"\e[1;7D": copy-backward-word
# copy-forward-word (not bound)
# copy-region-as-kill (not bound)
# dabbrev-expand (not bound)
"\C-d": delete-char
"\e[3~": delete-char
# delete-char-or-list (not bound)
"\e\\": delete-horizontal-space

"\e-": digit-argument
"\e0": digit-argument
"\e1": digit-argument
"\e2": digit-argument
"\e3": digit-argument
"\e4": digit-argument
"\e5": digit-argument
"\e6": digit-argument
"\e7": digit-argument
"\e8": digit-argument
"\e9": digit-argument

"\C-x\C-v": display-shell-version

"\C-xA": do-lowercase-version
"\C-xB": do-lowercase-version
"\C-xC": do-lowercase-version
"\C-xD": do-lowercase-version
"\C-xE": do-lowercase-version
"\C-xF": do-lowercase-version
"\C-xG": do-lowercase-version
"\C-xH": do-lowercase-version
"\C-xI": do-lowercase-version
"\C-xJ": do-lowercase-version
"\C-xK": do-lowercase-version
"\C-xL": do-lowercase-version
"\C-xM": do-lowercase-version
"\C-xN": do-lowercase-version
"\C-xO": do-lowercase-version
"\C-xP": do-lowercase-version
"\C-xQ": do-lowercase-version
"\C-xR": do-lowercase-version
"\C-xS": do-lowercase-version
"\C-xT": do-lowercase-version
"\C-xU": do-lowercase-version
"\C-xV": do-lowercase-version
"\C-xW": do-lowercase-version
"\C-xX": do-lowercase-version
"\C-xY": do-lowercase-version
"\C-xZ": do-lowercase-version

"\eA": do-lowercase-version
"\eB": do-lowercase-version
"\eC": do-lowercase-version
"\eD": do-lowercase-version
"\eE": do-lowercase-version
"\eF": do-lowercase-version
"\eG": do-lowercase-version
"\eH": do-lowercase-version
"\eI": do-lowercase-version
"\eJ": do-lowercase-version
"\eK": do-lowercase-version
"\eL": do-lowercase-version
"\eM": do-lowercase-version
"\eN": do-lowercase-version
"\eP": do-lowercase-version
"\eQ": do-lowercase-version
"\eR": do-lowercase-version
"\eS": do-lowercase-version
"\eT": do-lowercase-version
"\eU": do-lowercase-version
"\eV": do-lowercase-version
"\eW": do-lowercase-version
"\eX": do-lowercase-version
"\eY": do-lowercase-version
"\eZ": do-lowercase-version

"\el": downcase-word

"\eOR": dump-functions
"\eOS": dump-macros
"\eOQ": dump-variables

"\e\C-i": dynamic-complete-history
"\C-x\C-e": edit-and-execute-command
# emacs-editing-mode (not bound)
"\C-x)": end-kbd-macro
"\e>": end-of-history
"\C-e": end-of-line
"\eOF": end-of-line
"\e[F": end-of-line
"\C-x\C-x": exchange-point-and-mark
# forward-backward-delete-char (not bound)
# forward-byte (not bound)

"\C-f": forward-char
"\eOC": forward-char
"\e[C": forward-char
"\C-s": forward-search-history

"\e[1;5C": forward-word
"\ef": forward-word
"\eg": glob-complete-word
"\C-x*": glob-expand-word
"\C-xg": glob-list-expansions

# history-and-alias-expand-line (not bound)
"\e^": history-expand-line
"\e[A": history-search-backward
"\e[B": history-search-forward
# history-substring-search-backward (not bound)
# history-substring-search-forward (not bound)
"\e#": insert-comment
"\e*": insert-completions
"\e.": insert-last-argument
"\e[1;5A": insert-last-argument
"\e_": insert-last-argument
"\C-k": kill-line
# kill-region (not bound)
"\e[1;5B": kill-whole-line
"\e[3;5~": kill-word
"\ed": kill-word
# magic-space (not bound)
"\C-i": menu-complete
"\e[Z": menu-complete-backward
"\C-n": next-history
"\eOB": next-history
"\en": non-incremental-forward-search-history
# non-incremental-forward-search-history-again (not bound)
"\ep": non-incremental-reverse-search-history
# non-incremental-reverse-search-history-again (not bound)
# old-menu-complete (not bound)
"\C-o": operate-and-get-next
# overwrite-mode (not bound)

"\C-x!": possible-command-completions
"\e=": possible-completions
"\e?": possible-completions
"\C-x/": possible-filename-completions
"\C-x@": possible-hostname-completions
"\C-x~": possible-username-completions
"\C-x$": possible-variable-completions

"\C-p": previous-history
"\eOA": previous-history
"\e[15~": print-last-kbd-macro
"\C-q": quoted-insert
"\C-v": quoted-insert
# redraw-current-line (not bound)
"\C-x\C-r": re-read-init-file
"\C-r": reverse-search-history
"\e\C-r": revert-line
"\er": revert-line

"\C-@": set-mark
"\e ": set-mark
# shell-backward-kill-word (not bound)
# shell-backward-word (not bound)
"\e\C-e": shell-expand-line
# shell-forward-word (not bound)
# shell-kill-word (not bound)
# skip-csi-sequence (not bound)
"\C-x(": start-kbd-macro
# tab-insert (not bound)
"\e&": tilde-expand
"\C-t": transpose-chars
"\et": transpose-words
# tty-status (not bound)
"\C-x\C-u": undo
"\e\C-?": undo
# universal-argument (not bound)
# unix-filename-rubout (not bound)
"\C-u": unix-line-discard
"\C-w": unix-word-rubout
"\eu": upcase-word

# vi-append-eol (not bound)
# vi-append-mode (not bound)
# vi-arg-digit (not bound)
# vi-back-to-indent (not bound)
# vi-backward-bigword (not bound)
# vi-backward-word (not bound)
# vi-bword (not bound)
# vi-bWord (not bound)
# vi-change-case (not bound)
# vi-change-char (not bound)
# vi-change-to (not bound)
# vi-char-search (not bound)
# vi-column (not bound)
# vi-complete (not bound)
# vi-delete (not bound)
# vi-delete-to (not bound)
"\e[24~": vi-editing-mode
# vi-end-bigword (not bound)
# vi-end-word (not bound)
# vi-eof-maybe (not bound)
# vi-eword (not bound)
# vi-eWord (not bound)
# vi-fetch-history (not bound)
# vi-first-print (not bound)
# vi-forward-bigword (not bound)
# vi-forward-word (not bound)
# vi-fword (not bound)
# vi-fWord (not bound)
# vi-goto-mark (not bound)
# vi-insert-beg (not bound)
# vi-insertion-mode (not bound)
# vi-match (not bound)
# vi-movement-mode (not bound)
# vi-next-word (not bound)
# vi-overstrike (not bound)
# vi-overstrike-delete (not bound)
# vi-prev-word (not bound)
# vi-put (not bound)
# vi-redo (not bound)
# vi-replace (not bound)
# vi-rubout (not bound)
# vi-search (not bound)
# vi-search-again (not bound)
# vi-set-mark (not bound)
# vi-subst (not bound)
# vi-tilde-expand (not bound)
# vi-yank-arg (not bound)
# vi-yank-to (not bound)

"\C-y": yank
"\e[1;7C": yank
"\e.": yank-last-arg
"\e[1;5A": yank-last-arg
"\e_": yank-last-arg
"\e\C-y": yank-nth-arg
"\e[1;7A": yank-pop
"\ey": yank-pop

" ": self-insert
"!": self-insert
"\"": self-insert
"#": self-insert
"$": self-insert
"%": self-insert
"&": self-insert
"'": self-insert
"(": self-insert
")": self-insert
"*": self-insert
"+": self-insert
",": self-insert
"-": self-insert
".": self-insert
"/": self-insert
"0": self-insert
"1": self-insert
"2": self-insert
"3": self-insert
"4": self-insert
"5": self-insert
"6": self-insert
"7": self-insert
"8": self-insert
"9": self-insert
":": self-insert
";": self-insert
"<": self-insert
"=": self-insert
">": self-insert
"?": self-insert
"@": self-insert
"A": self-insert
"B": self-insert
"C": self-insert
"D": self-insert
"E": self-insert
"F": self-insert
"G": self-insert
"H": self-insert
"I": self-insert
"J": self-insert
"K": self-insert
"L": self-insert
"M": self-insert
"N": self-insert
"O": self-insert
"P": self-insert
"Q": self-insert
"R": self-insert
"S": self-insert
"T": self-insert
"U": self-insert
"V": self-insert
"W": self-insert
"X": self-insert
"Y": self-insert
"Z": self-insert
"[": self-insert
"\\": self-insert
"]": self-insert
"^": self-insert
"_": self-insert
"`": self-insert
"a": self-insert
"b": self-insert
"c": self-insert
"d": self-insert
"e": self-insert
"f": self-insert
"g": self-insert
"h": self-insert
"i": self-insert
"j": self-insert
"k": self-insert
"l": self-insert
"m": self-insert
"n": self-insert
"o": self-insert
"p": self-insert
"q": self-insert
"r": self-insert
"s": self-insert
"t": self-insert
"u": self-insert
"v": self-insert
"w": self-insert
"x": self-insert
"y": self-insert
"z": self-insert
"{": self-insert
"|": self-insert
"}": self-insert
"~": self-insert
```
