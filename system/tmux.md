tmux
====

config
------

*   `/etc/tmux.conf`
*   `~/.tmux.conf`

key mappings
------------

### sessions

*   create named session: `tmux new -s <session name>`
*   restore session: `tmux attach -t <sesion name>`
*   rename session: `Ctrl-b $`
*   detach current client: `Ctrl-b d`

### panes

*   split pane vertical: `Ctrl-b %`
*   split pane horizontal: `Ctrl-b "`
*   move between panes: `Ctrl-b [left|right|up|down]`
*   resize panes: `Ctrl-b Ctrl-[left|right|up|down]`

### windows

*   new window: `Ctrl-b c`
*   select window: `Ctrl-b [0..9]`
