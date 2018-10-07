Manjaro i3
==========

Package Manager
---------------

**yay**

```sh
git clone https://aur.archlinux.org/yay $HOME/build/yay
cd $HOME/build/yay
makepkg -si
```

### Install packages

```sh
yay -S tmux z-git the_silver_searcher xclip
yay -S downgrade bash-completion
yay -S numlockx
```

**Fonts**

```sh
yay -S ttf-freefont
yay -S ttf-arphic-uming ttf-baekmuk
yay -S terminus-font ttf-inconsolata
```

Terminal
--------

**$HOME/.bashrc**

```sh
# z
source /usr/lib/z.sh 
```

Web Browser
-----------

**Chromium**

```sh
yay -S chromium
```

JavaScript Development
----------------------

```sh
yay -S nodejs visual-studio-code-bin
yay -S docker docker-compose
```
