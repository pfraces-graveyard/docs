Windows Postinstall
===================

Package manager
---------------

<https://chocolatey.org/>

```
choco install git
choco install meld
choco install nodejs
choco install notepadplusplus
choco install 7zip
```

Terminal emulator
-----------------

Use `git-bash` which comes with git package

Git config
----------

**$HOME/.gitconfig**

```
[user]
    name = <username>
    email = <email>
[merge]
    tool = meld
[mergetool "meld"]
    path = C:\\Program Files (x86)\\Meld\\Meld.exe
[mergetool]
    keepBackup = false
```
