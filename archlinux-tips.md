Archlinux tips
==============

aurvote
-------

    sudo packer -S --noconfirm aurvote

### configuration

    aurvote --configure

**NOTE:** Aurvote stores an unencrypted password so better if you use directly the AUR page to vote for packages

### list of voted packages

*   https://aur.archlinux.org/packages/?SB=w&SO=d&O=0&PP=50

### vote/unvote

    aurvote --vote <package>
    aurvote --unvote <package>

Also you can vote/unvote from the package's web page (`https://aur.archlinux.org/packages/<package>`)
