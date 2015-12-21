Ubuntu (14.04) Postinstall
===========================

System upgrade
--------------

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get autoremove

Install utilities
-----------------

    sudo apt-get install \
        stterm \
        tmux \
        git \
        gitg \
        silversearcher-ag \
        meld \
        xclip \
        gpick

### Synaptic

    sudo apt-get install synaptic
    sudo apt-get install gksu
    cp /usr/share/applications/synaptic.desktop ~/.local/share/applications

Edit `~/.local/share/applications`

    Exec=gksudo synaptic-pkexec

Source: http://askubuntu.com/a/68023

### Vim (with Lua support)

    sudo apt-get install \
        liblua5.1-dev \
        luajit \
        libluajit-5.1 \
        python-dev \
        ruby-dev \
        libperl-dev \
        mercurial \
        libncurses5-dev \
        libgnome2-dev \
        libgnomeui-dev \
        libgtk2.0-dev \
        libatk1.0-dev \
        libbonoboui2-dev \
        libcairo2-dev \
        libx11-dev \
        libxpm-dev \
        libxt-dev
    
    sudo mkdir /usr/include/lua5.1/include
    sudo ln -s /usr/include/luajit-2.0 /usr/include/lua5.1/include
     
    mkdir ~/build
    cd ~/build
    
    git clone https://github.com/vim/vim.git
    cd ~/build/vim/src
    
    ./configure \
        --with-features=huge \
        --enable-rubyinterp \
        --enable-largefile \
        --disable-netbeans \
        --enable-pythoninterp \
        --with-python-config-dir=/usr/lib/python2.7/config-x86_64-linux-gnu \
        --enable-perlinterp \
        --enable-luainterp \
        --with-luajit \
        --enable-gui=auto \
        --enable-fail-if-missing \
        --with-lua-prefix=/usr/include/lua5.1 \
        --enable-cscope 
    
    make 
    sudo make install
    
    sudo mkdir /usr/share/vim
    sudo mkdir /usr/share/vim/vim74
    
    cd ~/build/vim
    sudo cp -fr runtime/* /usr/share/vim/vim74/

Source: https://gist.github.com/akolosov/cedaac86b333a4ced95f

### Chromium

    sudo apt-get install \
        chromium-browser \
        pepperflashplugin-nonfree

**Extensions**

  * Adblock Plus
  * Postman
  * Web Developer Form Filler
  * Webpage Screenshot

### Unity

    sudo apt-get install \
        dconf-editor \
        unity-tweak-tool \
        compizconfig-settings-manager \
        compiz-plugins

### i3

    echo "deb http://debian.sur5r.net/i3/ $(lsb_release -c -s) universe" | sudo tee -a /etc/apt/sources.list
    sudo apt-get update
    sudo apt-get --allow-unauthenticated install sur5r-keyring
    sudo apt-get update
    sudo apt-get install i3

Source: https://i3wm.org/docs/repositories.html

### i3 desktop environment

    sudo apt-get install \
        i3lock \
        suckless-tools \
        lxappearance \
        scrot \
        feh \
        gsimplecal

**Note:** `suckless-tools` is needed for `dmenu`

### nodejs

    sudo apt-get update
    sudo apt-get install -y python-software-properties python g++ make
    sudo add-apt-repository ppa:chris-lea/node.js
    sudo apt-get update
    sudo apt-get install nodejs

Source: https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#ubuntu-mint-elementary-os

### sublime text 3

    sudo add-apt-repository ppa:webupd8team/sublime-text-3
    sudo apt-get update
    sudo apt-get install sublime-text-installer

Source: http://www.webupd8.org/2013/07/sublime-text-3-ubuntu-ppa-now-available.html

### atom

    sudo add-apt-repository ppa:webupd8team/atom
    sudo apt-get update
    sudo apt-get install atom

Source: http://www.webupd8.org/2014/05/install-atom-text-editor-in-ubuntu-via-ppa.html

### grip

    sudo apt-get install python-pip
    sudo pip install grip

Source: http://stackoverflow.com/a/13781363/1815446

### thunar

    sudo apt-get install thunar gnome-icon-theme-full

Unity setup
-----------

### Unlock `Ctrl+Space` keybinding

Remove keybindings from `ibus`

    dconf-editor > desktop > ibus > general > hotkey

  > The trigger and triggers setting will still show 'control+space'. 
    Edit these settings out, being careful to leave empty brackets [] in triggers.

Source: http://askubuntu.com/a/243653

### Disable Unity online Search

    unity-control-center > Security & Privacy > Search > Include online search: off

Source: http://www.unixmen.com/disable-unity-online-search-feature-ubuntu-14-10/

### Avoid double-typing password in lock screen

    unity-control-center > Brightness and Lock > Lock: off

Source: http://simionbaws.ro/linux/ubuntu-14-04-lock-screen-asking-password-twice/

### Change number of workspaces

    unity-tweak-tool > Window Manager > Workspace Settings

Source: http://askubuntu.com/a/108306

### Remove 'show desktop' from window switcher

*(Ignore this step if you are going to disable window grouping as shown below)*

    unity-tweak-tool > Unity > Switcher > Display "Show Desktop" icon

Source: http://askubuntu.com/a/174457

### Disable window grouping in window switcher

*   Disable the keyboard shortcuts for Unity's switcher by unchecking:

        ccsm > Desktop > Ubuntu Unity Plugin > Switcher > Key to start the switcher > Enabled
        ccsm > Desktop > Ubuntu Unity Plugin > Switcher > Key to start the switcher in reverse > Enabled

*   Enable the Static Application Switcher by checking:

       ccsm >  Window Management > Static Application Switcher > Enable Static Application Switcher

Source: http://askubuntu.com/questions/68151

i3 setup
--------

### keybindings

`$HOME/.i3/config`

```
bindsym $mod+Return exec XMODIFIERS= stterm -f inconsolata:pixelsize=15
bindsym $mod+z exec i3lock --color 000000
```

### gtk theme

Launch `lxappearance` and choose your preferred theme

### notifications

**Remove `dunst`:**

In Ubuntu, `i3` comes with `dunst` notifications system

    sudo apt-get purge dunst
    killall dunst

Source: http://askubuntu.com/a/383930

**Replace ubuntu's `notify-osd` with gnome's `notification-daemon`**

    sudo apt-get install notification-deamon

Edit `/usr/share/dbus-1/services/org.freedesktop.Notifications.service`:

  * replace: `Exec=/usr/lib/x86_64-linux-gnu/notify-osd`
  * with: `Exec=/usr/lib/notification-daemon/notification-daemon`

Source: http://ubuntuforums.org/showthread.php?t=1663840