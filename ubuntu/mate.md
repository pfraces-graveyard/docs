Mate (for Ubuntu)
=================

Installation
------------

    sudo apt-get install --no-install-recommends ubuntu-mate-core
    sudo apt-get install --no-install-recommends ubuntu-mate-desktop

  > Then log into the MATE session and use MATE Tweak to switch away from, and then back to, the "Ubuntu MATE" interface.
  > Then Enable Indicators from MATE Tweak

Source https://ubuntu-mate.community/t/how-to-replace-unity-by-mate-in-ubuntu-xenial-16-04/5054/4

Setup
-----

### Default desktop environment

    sudo nano /usr/share/lightdm/lightdm.conf.d/50-ubuntu.conf

Change `user-session` line with the desired desktop from `ls /usr/share/xsessions`

    user-session=mate

Source: http://askubuntu.com/questions/456766/how-to-set-default-session-in-ubuntu-14-04-lts
