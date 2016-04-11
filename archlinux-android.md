Android SDK on ArchLinux
========================

Prerequisites
-------------

`pacman -S lib32-openal lib32-libstdc++5 lib32-ncurses lib32-sdl swt`

Ensure enough space for the build
---------------------------------

```
cd ~
mkdir tmp
alias packer='TMPDIR=~/tmp packer'
``` 

Install
-------

`packer -S --noconfirm android-sdk android-udev`

Add tools to `$PATH`
--------------------

`PATH=$PATH:/opt/android-sdk/tools`
