Windows Postinstall
===================

Package manager
---------------

<https://chocolatey.org/>

```
choco install git meld nodejs yarn
choco install [notepadplusplus atom visualstudiocode lighttable brackets]
choco install 7zip adobereader teamviewer skype libreoffice
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
[credential]
    helper = manager
    modalPrompt = false
[core]
    askPass = ""
    longpaths = true
    excludesfile = ~/.gitignore
```

**$HOME/.gitignore**
# vim swap files
*.swp
```

```
