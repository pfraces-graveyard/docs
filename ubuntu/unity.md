Unity (for Ubuntu)
==================

Install utilities
-----------------

    sudo apt-get install \
        dconf-editor \
        unity-tweak-tool \
        compizconfig-settings-manager \
        compiz-plugins

Setup
-----

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
