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
"
let &columns = &nuw + 80

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
