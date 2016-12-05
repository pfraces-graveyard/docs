Archlinux install
=================

Official guides

*   https://wiki.archlinux.org/index.php/installation_guide
*   https://wiki.archlinux.org/index.php/beginners

Mailing lists

*   https://mailman.archlinux.org/mailman/listinfo/arch-announce

Helpers

*   https://github.com/helmuthdu/aui

Download
--------

CPU architecture

```
cat /proc/cpuinfo | sed -nr 's/.*(lm).*/\1/p' | sed 1q |
  test $(cat) == 'lm' && echo 'x86_64' || echo 'i686'
```

Archlinux ISO (**netinstall**)

*   http://www.archlinux.org/download/

Install
-------

Add users

    useradd -m -g users \
      -G audio,optical,power,storage,wheel \
      -s /bin/bash \
      <username>

    passwd root
    passwd <username>

Update `pacman`

    wget --no-check-certificate -q -O - \
      "https://www.archlinux.org/mirrorlist/?country=ES&protocol=http&ip_version=4" |
      sed -n '/^#Server/ s/^#//' |
      tee /etc/pacman.d/mirrorlist

    pacman -Syy
    pacman -S --noconfirm pacman
    pacman-key --init
    pacman-key --populate archlinux

Install `sudo`

    pacman -S --noconfirm sudo

Switch to a non-privileged user

    exit

Install `reflector`

    sudo pacman -S --noconfirm reflector

Install `packer`

    sudo pacman -S --noconfirm base-devel wget jshon expac
    mkdir -p ~/.build/packer
    cd ~/.build/packer
    wget https://aur.archlinux.org/packages/pa/packer/PKGBUILD 
    makepkg
    sudo pacman -U packer-*.pkg.tar.xz

Update system

```
sudo reflector --verbose -l 3 --sort rate --save /etc/pacman.d/mirrorlist
sudo packer -Syu --noconfirm
```
