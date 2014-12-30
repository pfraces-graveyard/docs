tmux
====

*   [the tao of tmux](http://tmuxp.readthedocs.org/en/latest/about_tmux.html)
*   [archlinux wiki](https://wiki.archlinux.org/index.php/tmux)
*   [tmux crash course](http://robots.thoughtbot.com/a-tmux-crash-course)

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

### modes

*   command mode: `Ctrl-b :` (exit with `[Esc]`)
*   scroll mode: `Ctrl-b [` (exit with `q`)

### windows

*   new window: `Ctrl-b c`
*   select window: `Ctrl-b [0..9]`
*   move pane to new window: `Ctrl-b !`
*   select window by name: `Ctrl-b f`
*   rename window: `Ctrl-b ,`
*   swap windows: `swap-window -s 3 -t 1`
*   swap current window: `swap-window -t 0`

### panes

*   split pane vertical: `Ctrl-b %`
*   split pane horizontal: `Ctrl-b "`
*   move between panes: `Ctrl-b [Left|Right|Up|Down]`
*   resize panes: `Ctrl-b Ctrl-[Left|Right|Up|Down]`
*   swap panes: `Ctrl-b o`

#### layout

Tmux has several layout presets. (**Meta** is `[Alt]` on my system)

*   `Ctrl-b [Space]`: switch between them)
*   `Ctrl-b Meta-1`: (even vertical) vertical split, all panes same width
*   `Ctrl-b Meta-2`: (Even horizontal) horizontal split, all panes same height
*   `Ctrl-b Meta-3`: (Main horizontal) horizontal split, main pane on top,
    other panes on bottom, vertically split, all same width
*   `Ctrl-b Meta-4`: (Main vertical) vertical split, main pane left, other
    panes right, horizontally split, all same height
*   `Ctrl-b Meta-5`: (Tiled) tile, new panes on bottom, same height before
    same width

system integration
------------------

### start tmux on every login shell

In `~/.bashrc`:

```
if [[ -z "$TMUX" ]]
then (tmux attach || tmux new-session)
fi
```
