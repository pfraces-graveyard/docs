Ubuntu Mate
===========

System upgrade
--------------

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get autoremove

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

    curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
    sudo apt-get install -y nodejs

Source: <https://github.com/nodesource/distributions#installation-instructions>

### Z

    Z_PATH=$HOME/alien/z/z.sh
    curl -fLo $Z_PATH --create-dirs https://raw.githubusercontent.com/rupa/z/master/z.sh
    echo "source $Z_PATH" >> ~/.bashrc

### Grip

    sudo apt-get install python-pip
    sudo pip install grip

Source: <http://stackoverflow.com/a/13781363/1815446>

### Docker

    sudo apt-get install \
        linux-image-extra-$(uname -r) \
        linux-image-extra-virtual \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    sudo apt-get update
    sudo apt-get install docker-ce

Source: <https://docs.docker.com/engine/installation/linux/ubuntu/>

Terminal multiplexer
--------------------

### Terminator

    sudo apt-get install terminator

Text editor
-----------

### Visual Studio Code

Install `ubuntu-make`

    sudo add-apt-repository ppa:ubuntu-desktop/ubuntu-make
    sudo apt-get update && sudo apt-get install ubuntu-make

Install VSCode using `ubuntu-make`

    umake web visual-studio-code

Source: <http://www.omgubuntu.co.uk/2015/05/how-to-install-microsoft-visual-studio-code-in-ubuntu>

File manager
------------

### Thunar

    sudo apt-get install thunar gnome-icon-theme-full

  * [Replace Nautilus with Thunar](http://ubuntuguide.net/install-thunar-file-browser-and-make-default-in-gnome)
