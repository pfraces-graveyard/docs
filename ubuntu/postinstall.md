Ubuntu (16.04) Postinstall
===========================

System upgrade
--------------

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get autoremove

Desktop Environment
-------------------

There are specific documentation for tested desktop environments

  * [Unity](unity.md)
  * [i3](i3.md)
  * [Mate](mate.md)

Install utilities
-----------------

    sudo apt-get install \
        git \
        gitg \
        silversearcher-ag \
        meld \
        xclip \
        gpick \
        vim-nox-py2 \
        mousepad

### Synaptic

    sudo apt-get install synaptic
    sudo apt-get install gksu
    cp /usr/share/applications/synaptic.desktop ~/.local/share/applications

Edit `~/.local/share/applications`

    Exec=gksudo synaptic-pkexec

Source: http://askubuntu.com/a/68023

### Chromium

    sudo apt-get install \
        chromium-browser \
        pepperflashplugin-nonfree

**Extensions**

  * Adblock Plus / uBlock Origin
  * Hide My AdBlocker
  * Postman
  * Web Developer Form Filler
  * Screenshot Webpages

### NodeJS

    curl -sL https://deb.nodesource.com/setup_4.x | sudo bash -
    sudo apt-get install nodejs

Source: https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories

### Z

    Z_PATH=$HOME/alien/z/z.sh
    curl -fLo $Z_PATH --create-dirs https://raw.githubusercontent.com/rupa/z/master/z.sh
    echo "source $Z_PATH" >> ~/.bashrc

### Grip

    sudo apt-get install python-pip
    sudo pip install grip

Source: http://stackoverflow.com/a/13781363/1815446

Terminal multiplexer
--------------------

### St

    sudo apt-get install stterm tmux

### Terminator

    sudo apt-get install terminator

Text editor
-----------

### Atom

    sudo add-apt-repository ppa:webupd8team/atom
    sudo apt-get update
    sudo apt-get install atom

Source: http://www.webupd8.org/2014/05/install-atom-text-editor-in-ubuntu-via-ppa.html

### Neovim

    sudo add-apt-repository ppa:neovim-ppa/unstable
    sudo apt-get update
    sudo apt-get install neovim
    
Python modules

    sudo apt-get install python-dev python-pip python3-dev python3-pip
    pip install --user neovim
    pip3 install --user neovim

Source: <https://github.com/neovim/neovim/wiki/Installing-Neovim#ubuntu>

File manager
------------

### Nautilus

It comes with the Unity desktop environment by default

### Thunar

    sudo apt-get install thunar gnome-icon-theme-full

  * [Replace Nautilus with Thunar](http://ubuntuguide.net/install-thunar-file-browser-and-make-default-in-gnome)
