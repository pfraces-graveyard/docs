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
"
" misc
"
set nocompatible
set encoding=utf-8
set ignorecase
set smartcase

"
" indentation
"
set autoindent
set expandtab
set smarttab
set tabstop=2
set shiftwidth=2

"
" centered search
"
nnoremap n nzz
nnoremap N Nzz

"
" hide menu bars
"
set guioptions-=m
set guioptions-=T

"
" linenumbers
"
set number
set nuw=5

"
" 80 characters width
" 24 lines height
"
let &columns = &nuw + 80
set lines=24

"
" disable cursor blink
"
set guicursor+=a:blinkon0

"
" restore cursor to file position
"
set viminfo='10,"100,:20,%,n~/.viminfo

function! ResCur()
  if line("'\"") <= line("$")
    normal! g`"zz
    return 1
  endif
endfunction

augroup resCur
  autocmd!
  autocmd BufWinEnter * call ResCur()
augroup END

"
" pathogen
"
call pathogen#infect()

"
" theme
"
colorscheme distinguished

"
" code highlight
"
syntax on
filetype plugin indent on

highlight Cursor guifg=#404040 guibg=#A9A9A9
highlight OverLength ctermbg=red ctermfg=white guibg=red guifg=white

"
" 80 characters warning
"
match OverLength /\%79v./
```

## System integration

### Bash

**~/.bashrc**

```
function vim () {
    (gvim -f "$@" &)
}
```

[snippet and explanation source](http://askubuntu.com/questions/132977/how-to-get-global-application-menu-for-gvim#comment503002_132993)

>   The bug is related to gvim's way of going into background mode. gvim -f
    keeps gvim in the foreground. To make the shell run gvim in the background
    we add an &. The parenthesis in (foo &) runs the command in a subshell, so
    that gvim does not become a background process of the current shell. Without
    parenthesis, closing the terminal by clicking the X would also kill gvim.
    function foo () { ... } creates a shell function. We must add /usr/bin/ to
    gvim, otherwise we will get an infinitely recursive function. "$@" passes
    all arguments.

### Git

**~/.gitconfig**

```
[core]
 	editor = gvim -f
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
