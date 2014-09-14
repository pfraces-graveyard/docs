Archlinux installation
======================

Gvim
----

    sudo pacman -S gvim

Config: https://github.com/pfraces-wip/doc/blob/master/system/gvim.md

Git
---

    sudo pacman -S git

Config: https://github.com/pfraces-wip/doc/blob/master/system/git.md

Packer
------

Install dependencies

    sudo pacman -S base-devel wget jshon expac

Download and build the package

    mkdir -p ~/build/packer/
    cd ~/build/packer/
    wget https://aur.archlinux.org/packages/pa/packer/PKGBUILD 
    makepkg
    sudo pacman -U packer-*.pkg.tar.xz

Install utilities
-----------------

    sudo packer -S \
      bash-completion \
      downgrade \
      aurvote \
      the_silver_searcher \
      xclip \
      xkill \
      htop

Z
-

    sudo packer -S z-git

**~/.bashrc**

    . /usr/lib/z.sh

Chromium
--------

    sudo packer -S chromium
    sudo pacman -Rscn firefox

### Update flash plugin

    sudo packer -S chromium-pepper-flash

Restart chromium to enable the plugin

### Extensions

*   Adblock Plus
*   Postman + Postman launcher
*   Screen Capture
*   Save as PDF (from pdfcrowd.com)

### Configuration

*   **[on]** Disable cache while devtools is open
*   **[on]** Log XMLHttpRequests
*   **[off]** Enable JS source maps
*   **[off]** Enable CSS source maps

Desktop environment
-------------------

### Custom

    sudo packer -S \
      dmenu \
      slock \
      scrot

### Xfce

General key-bindings

    xfce4-keyboard-settings

*   slock (Super+Z)
*   xfce4-screenshooter (Print)
*   xfce4-terminal (Super+Return)
*   xfrun4 (Super+P)

Window manager key-bindings

**Configuration > Window Manager > Keyboard**
