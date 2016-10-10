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
        git \
        gitg \
        silversearcher-ag \
        meld \
        xclip \
        gpick

### Terminal multiplexer

Choose one of the following:

  *  `sudo apt-get install stterm tmux`
  *  `sudo apt-get install terminator`

### Synaptic

    sudo apt-get install synaptic
    sudo apt-get install gksu
    cp /usr/share/applications/synaptic.desktop ~/.local/share/applications

Edit `~/.local/share/applications`

    Exec=gksudo synaptic-pkexec

Source: http://askubuntu.com/a/68023

### neovim

    sudo add-apt-repository ppa:neovim-ppa/unstable
    sudo apt-get update
    sudo apt-get install neovim
    
Python modules

    sudo apt-get install python-dev python-pip python3-dev python3-pip
    pip install --user neovim
    pip3 install --user neovim

Source: <https://github.com/neovim/neovim/wiki/Installing-Neovim#ubuntu>

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

    curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -
    sudo apt-get install -y nodejs

Source: https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories

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

  * [Replace Nautilus with Thunar](http://ubuntuguide.net/install-thunar-file-browser-and-make-default-in-gnome)

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
