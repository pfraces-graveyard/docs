vim from the terminal
=====================

running vim from the terminal has the advantage of being executed under a
terminal multiplexer such as `screen` or `tmux`

config
------

we need to configure several components to accomplish this setup:

*   graphical terminal emulator: `xterm` or `rxvt` or `st`
*   terminal multiplexer: `screen` or `tmux`
*   vim

### xterm

In `~/.Xresources`:

    xterm*faceName: Terminus
    xterm*faceSize: 13

In `~/.bashrc`:

    xrdb -merge ~/.Xresources

### st (xterm alternative)

Ubuntu has named it as `stterm` for suckless tools terminal

In `~/.bashrc`:

    alias st='stterm -f "DejaVu Sans Mono:pixelsize=15"'

Desktop file (`./local/share/applications/st.desktop`)

```
[Desktop Entry]
Name=st
GenericName=Terminal
Comment=simple terminal
Exec=/usr/bin/stterm -f "DejaVu Sans Mono:pixelsize=15"
Terminal=false
Type=Application
Icon=utilities-terminal
Categories=System;TerminalEmulator;Utility;
OnlyShowIn=GNOME;Unity;
Actions=New
StartupWMClass=stterm-256color

[Desktop Action New]
Name=New Terminal
Exec=/usr/bin/stterm -f "DejaVu Sans Mono:pixelsize=15"
OnlyShowIn=Unity
```

### tmux

In `~/.tmux.conf

    set -g default-terminal "screen-256color"

TODO
----

### bugs

*   backquote is not shown under st
*   escape key takes too much time

### integration

*   start tmux automatically when using st
*   tmux powerline (tmuxline?)
*   add shortcut to launch st (win+return?)

### vim config

*   hlsearch
*   highlight current line
*   show different background color for colums >80 chars
*   change cursor: block in normal, pipe in insert
*   key map to switch line numbers on and off
*   do not save backup files (check tmux can recover a session first)
*   add vim plugins (unite, ...)

### update documentation

*   improve vimrecover bash function: store backup files in the same place or
    disable backups at all (can tmux recover a crashed session?)
*   remove graphical vim tweaks from documentation
*   check if its needed to replace default terminal with tmux
*   remove xterm info if st is suitable enough
*   test and update git integration
