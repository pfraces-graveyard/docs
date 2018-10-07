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
yay -S tmux z-git the_silver_searcher
yay -S downgrade bash-completion
yay -S numlockx
yay -S scrot xclip
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
yay -S chromium chromium-pepper-flash
```
