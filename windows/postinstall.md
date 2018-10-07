Windows Postinstall
===================

Package manager
---------------

<https://chocolatey.org/>

### Installation

From PowerShell with administrative rights

```ps
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

### Config

```
choco feature enable -n allowGlobalConfirmation
```

### Install packages

```
choco install git meld nodejs
choco install notepadplusplus visualstudiocode
choco install rosaimagewriter docker-for-windows
choco install 7zip adobereader teamviewer skype libreoffice
```

Terminal emulator
-----------------

Use `git-bash` which comes with git package

**$HOME/.bash_profile**

```sh
source $HOME/.bashrc
```

**$HOME/.bashrc**

```sh
source $HOME/build/z/z.sh
source $HOME/.bashrc.npm
```

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

```
# vim swap files
*.swp
```

NPM completion
--------------

```sh
npm completion > $HOME/.bashrc.npm
```

z
-

```sh
mkdir $HOME/build
cd $HOME/build
git clone https://github.com/rupa/z
```
