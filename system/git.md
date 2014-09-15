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

### Git diff

    meld .

Bash aliases
------------

**~/.bashrc**

```
alias ga='git add --all .'
alias gc='ga && git commit'
alias gd='git diff'
alias gg='gc && gp'
alias gl='git log --oneline --decorate --graph'
alias gp='gum && git push origin master && git push origin --tags'
alias gr='git remote -v'
alias gs='git status'
alias gu='git pull origin'
alias gum='gu master'
alias gz='git reset HEAD .'
```

Keep directory structures
-------------------------

Create empty .keep files to add a directory structure to git

**~/.bashrc**

    alias gk='find . -type d -empty -exec touch {}/.keep \;'

*   http://stackoverflow.com/a/21422128/1815446
*   http://stackoverflow.com/a/5871742/1815446

Clone a github repo
-------------------

**~/.bashrc**

```
function ghc () {
    account=$1
    repo=$2

    if test -n "$MANTAINER"
    then user="$MANTAINER@"
    fi

    git clone https://"$user"github.com/${account}/${repo}.git
}
```

Clone a github own repo
-----------------------

**~/.bashrc**

```
function ghco () {
    repo=$1

    git clone https://pfraces@github.com/pfraces/${repo}.git
}
```

Github export
-------------

**~/.bashrc**

```
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
