Emacs Standard bindings for CTRL+x+KEY
"C-x"  <keyseq intro key>:

"\C-xe": call-last-kbd-macro
"\C-xg": glob-list-expansions
"\C-x(": start-kbd-macro
"\C-x)": end-kbd-macro
"\C-x/": possible-filename-completions
"\C-x~": possible-username-completions
"\C-x!": possible-command-completions
"\C-x@": possible-hostname-completions
"\C-x$": possible-variable-completions
"\C-x*": glob-expand-word


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


remove all do-lowercase-version bindings: 
bind -r \"\\C-x{A..Z}\"
bind -r \"\\e{A..Z}\"

