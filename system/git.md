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

Bash aliases
------------

**~/.bashrc**

```
## git

alias ga='git add --all .'
alias gb='git branch'
alias gc='ga && git commit'
alias gd='git diff'
alias gg='gc && gp'
alias gl='git log --oneline --decorate --graph'
alias gm='gd | meld -'
alias gp='gu && git push origin master && git push origin --tags'
alias gr='git remote -v'
alias gs='git status'
alias gt='git tag'
alias gu='git pull origin'
alias gum='gu master'
alias gz='git reset HEAD .'

### gk: git keep
###
### create empty .keep files to add a directory structure to git
###
### - http://stackoverflow.com/a/21422128/1815446
### - http://stackoverflow.com/a/5871742/1815446
alias gk='find . -type d -empty -exec touch {}/.keep \;'

### ghc - github clone
function ghc () {
    account=$1
    repo=$2

    git clone https://github.com/${account}/${repo}.git
}

### ghco - github clone own repo
function ghco () {
    repo=$1

    git clone https://pfraces@github.com/pfraces/${repo}.git
}

### ghe - github export
function ghe () {
    account=$1
    repo=$2

    git clone --depth=1 https://github.com/${account}/${repo}.git
    rm -rf ${repo}/.git
}
```

Meld
----

    pacman -S meld pygtksourceview2

### Config

**Edit > Preferences**

*   Enable syntax highlight
*   Enable line numbers
*   Enable highlight current line

### Git diff

    meld .

Online books
------------

*   http://git-scm.com/book
*   http://alx.github.io/gitbook/
