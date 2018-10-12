Manjaro i3
==========

Install packages
----------------

### Package Manager

**yay**

```sh
git clone https://aur.archlinux.org/yay $HOME/build/yay
cd $HOME/build/yay
makepkg -si
```

### Bash helpers

```sh
yay -S tmux bash-completion z-git the_silver_searcher xclip
```

### Fonts

```sh
yay -S ttf-freefont
yay -S ttf-arphic-uming ttf-baekmuk
yay -S terminus-font ttf-inconsolata
```

### Error proof

```
yay -S downgrade numlockx
```

### Web Browser

**Chromium**

```sh
yay -S chromium
```

### JavaScript Development

```sh
yay -S nodejs npm visual-studio-code-bin
yay -S docker docker-compose
```

Config
------

### NTP (fixes date and time)

```sh
sudo timedatectl set-ntp true
```

### Z

**$HOME/.bashrc**

```sh
# z
source /usr/lib/z.sh 
```

### Visual Studio Code

**Extensions:**

  * EditorConfig
  * GitLens
