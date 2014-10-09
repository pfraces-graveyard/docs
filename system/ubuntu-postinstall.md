Ubuntu (14.04) Post-Install
===========================

Create custom launchers with super user privileges
--------------------------------------------------

Install `gksudo` command

    sudo apt-get install gksu

Copy the launcher you want to edit to your user defined launchers directory

    cp /usr/share/applications/synaptic.desktop ~/.local/share/applications

Edit the launcher by adding `gksudo` before the launcher command in the `Exec` directive

    Exec=gksudo synaptic-pkexec

Source: http://askubuntu.com/a/68023

Change number of workspaces
---------------------------

Install unity-tweak-tool

    sudo apt-get install unity-tweak-tool

Edit the number of workspaces in:

    Window Manager > Workspace Settings

Source: http://askubuntu.com/a/108306

Remove 'show desktop' from window switcher
------------------------------------------

Install unity-tweak-tool

    sudo apt-get install unity-tweak-tool

Disable 'show desktop'

    Unity > Switcher > Display "Show Desktop" icon

Source: http://askubuntu.com/a/174457

Disable window grouping in window switcher
------------------------------------------

    sudo apt-get install compizconfig-settings-manager
    sudo apt-get install compiz-plugins
    ccsm

*   Disable the keyboard shortcuts for Unity's switcher by unchecking:

        Desktop > Ubuntu Unity Plugin > Switcher > Key to start the switcher > Enabled
        Desktop > Ubuntu Unity Plugin > Switcher > Key to start the switcher in reverse > Enabled

*   Enable the Static Application Switcher by checking:

        Window Management ▸ Static Application Switcher ▸ Enable Static Application Switcher

Source: http://askubuntu.com/questions/68151/how-do-i-revert-alt-tab-behavior-to-switch-between-windows-on-the-current-worksp
