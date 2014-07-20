# Gvim

## Install pathogen

    $ mkdir -p ~/.vim/autoload ~/.vim/bundle
    $ curl -LSso ~/.vim/autoload/pathogen.vim \
      https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim

### Install a theme

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Lokaltog/vim-distinguished.git 

## Basic configuration

`~/.vimrc`

```vimL
```

## Extras

### Code highlight plugins

*   [javascript](https://github.com/pangloss/vim-javascript.git)
*   [markdown](https://github.com/hallison/vim-markdown.git)

### Current line and pos highlight

`~/.vimrc`

    au WinLeave * set nocursorline nocursorcolumn
    au WinEnter * set cursorline cursorcolumn
    set cursorline cursorcolumn

### Powerline

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Lokaltog/vim-powerline.git

`~/.vimrc`

    set laststatus=2
    let g:Powerline_symbols = 'fancy'

#### Terminus-Powerline.ttf

    $ sudo pacman -S terminus-font
    $ mkdir ~/.fonts
    $ curl -Sso ~/.fonts/Terminus-Powerline.ttf https://gist.github.com/mikkeloscar/2416601/raw/18badb5d7af64b350c2864e548d5bc3912dffcac/Terminus-Powerline.ttf
    $ fc-cache -vf

`~/.vimrc`

    set guifont=Terminus\ 15

### YouCompleteMe

CMake is required

    $ pacman -S cmake

Installation

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Valloric/YouCompleteMe.git
    $ cd YouCompleteMe
    $ ./install.sh

### Fontsize

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/resetcontrol/vim-fontsize.git

### Command-T

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/wincent/Command-T.git
    $ cd command-t/ruby/Command-T
    $ ruby extconf.rb
    $ make

`~/.vimrc`

    call pathogen#helptags()

### Fugitive

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/tpope/vim-fugitive.git
