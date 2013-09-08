# Gvim

## Habilitar toda la funcionalidad de vim

`~/.vimrc`

    set nocompatible

## Encoding

`~/.vimrc`

    set encoding=utf-8

## Learning motions

    noremap <Up> <NOP>
    noremap <Down> <NOP>
    noremap <Left> <NOP>
    noremap <Right> <NOP>

### Motions

In NORMAL mode:

    <h> Move left
    <j> Move down
    <k> Move up
    <l> Move right

    <Ctrl+B> Move a page back
    <Ctrl+F> Move a page forward

    <b> Move to the start of the previous word
    <w> Move to the start of the next word

    <zt> Move current line to the top of the display
    <zz> Move current line to the middle of the display
    <zb> Move current line to the bottom of the display

## Custom motions

### Centered search

`~/.vimrc`

    nnoremap n nzz
    nnoremap N Nzz

## Resaltar caracteres de cierre

`~/.vimrc`

    set showmatch

## Ignorar mayúsculas al buscar

`~/.vimrc`

    set ignorecase
    set smartcase

## Indentación

A 2 espacios

`~/.vimrc`

    set autoindent
    set expandtab
    set smarttab
    set tabstop=2
    set shiftwidth=2

## Ocultar barras de menú

`~/.vimrc`

    set guioptions-=m
    set guioptions-=T

## Numeros de linea y 80 caracteres por linea

Como los numeros de linea ocupan 4 caracteres, se configura a 84 columnas

`~/.vimrc`

    set number
    au BufRead * let &numberwidth = float2nr(log10(line("$"))) + 2
          \| let &columns = &numberwidth + 80

## Cursor

### Fijar color (evitar parpadeo)

`~/.vimrc`

    set guicursor+=a:blinkon0

## Restore cursor to file position

`~/.vimrc`

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

## Plugins

### Pathogen

Instalador de plugins

    $ mkdir -p ~/.vim/autoload ~/.vim/bundle
    $ curl -Sso ~/.vim/autoload/pathogen.vim \
      https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim

`~/.vimrc`

    call pathogen#infect()

### Themes

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Lokaltog/vim-distinguished.git 

`~/.vimrc`

    colorsheme distinguished

### Code highlight

    $ cd ~/.vim/bundle/

    $ git clone https://github.com/hallison/vim-markdown.git
    $ git clone https://github.com/pangloss/vim-javascript.git
    $ git clone https://github.com/MSch/vim-tamejs.git
    $ git clone https://github.com/digitaltoad/vim-jade.git
    $ git clone https://github.com/wavded/vim-stylus.git

`~/.vimrc`

    syntax on
    filetype plugin indent on

    highlight Cursor guifg=#404040 guibg=#A9A9A9
    highlight OverLength ctermbg=red ctermfg=white guibg=red guifg=white
    match OverLength /\%>79v.\+/

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

## Plugins recomendados (pendientes de probar)

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
