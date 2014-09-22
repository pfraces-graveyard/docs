Git
===

User
----

**~/.gitconfig**

    [user]
      email = pfraces@gmail.com
      name = Pau Fracés

Editor
------

**~/.gitconfig**

    [core]
      editor = gvim -f

Global ignores
--------------

**~/.gitconfig**

    [core]
      excludesfile = ~/.gitignore

**~/.gitignore**

    # vim temporary files
    .*.swp
    
    # gedit temporary files
    *~
    
    # logs
    *.log

Cache password
--------------

**~/.gitconfig**

    [credential]
      helper = cache --timeout=3600

Meld
----

    pacman -S meld pygtksourceview2

### Config

**Edit > Preferences**

*   Enable syntax highlight
*   Enable line numbers
*   Enable highlight current line

Bash aliases
------------

**~/.bashrc**

```sh
function error () {
  echo $@ >&2
  (exit 1)
}

errMaster="unable to commit to master branch"

alias ga='git add --all .'
alias gaz='git reset HEAD .'
alias gb='git checkout -b'
alias gbc='git rev-parse --abbrev-ref HEAD'
alias gc='test $(gbc) != master && ga && git commit || error $errMaster'
alias gd='(meld . &)'
alias gdz='git checkout .'
alias gg='gc && gp'
alias gi='git update-index --assume-unchanged'
alias gil='git ls-files -v | grep "^[[:lower:]]"'
alias giz='git update-index --no-assume-unchanged'
alias gk='find . -type d -empty -exec touch {}/.keep \;'
alias gl='git log --oneline --decorate --graph'
alias gp='gu && git push origin $(gbc) && git push origin --tags'
alias gr='git remote -v'
alias gs='git status'
alias gu='git pull origin master'
alias gz='gaz && gmz'
```

### Clone a github repo

**~/.bashrc**

```sh
function ghc () {
    account=$1
    repo=$2

    git clone https://github.com/${account}/${repo}.git
}
```

### Clone a github own repo

**~/.bashrc**

```sh
function ghco () {
    repo=$1
    org=$2
    
    if test -z org
    then org=pfraces
    fi

    git clone https://pfraces@github.com/${org}/${repo}.git
}
```

### Github export

**~/.bashrc**

```sh
function ghe () {
    account=$1
    repo=$2

    git clone --depth=1 https://github.com/${account}/${repo}.git
    rm -rf ${repo}/.git
}
```

Online books
------------

*   http://git-scm.com/book
*   http://alx.github.io/gitbook/
