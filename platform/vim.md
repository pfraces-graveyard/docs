# Vim

## [TODO] 

Buscar otro syntax highlighter para markdown:

*   que no haga fold por defecto
*   que coloree los títulos de diferente modo

## Configuración básica para gvim

`~/.vimrc`

    set nocompatible

    set ruler
    set showmode
    set showmatch

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

## Highlight overflow

Colorear el exceso de 79 caracteres

Para una correcta visualización de código fuente se recomienda que se use
una fuente monoespaciada y no superar los 80 caracteres. Debido a que hay
algunos terminales que usan el 80º caracter como caracter de control, se
coloreará a partir de 79 caracteres asegurando así la correcta
visualización en cualquier medio

`~/.vimrc`

    highlight OverLength ctermbg=red ctermfg=white guibg=red guifg=white
    match OverLength /\%>79v.\+/

## Cursor

### Color

`~/.vimrc`

    highlight Cursor guifg=#404040 guibg=#A9A9A9

### Fijar (evitar parpadeo)

`~/.vimrc`

    set guicursor+=a:blinkon0

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

    $ git clone https://github.com/plasticboy/vim-markdown.git
    $ git clone https://github.com/pangloss/vim-javascript.git
    $ git clone https://github.com/MSch/vim-tamejs.git
    $ git clone https://github.com/digitaltoad/vim-jade.git
    $ git clone https://github.com/wavded/vim-stylus.git

`~/.vimrc`

    syntax on
    filetype plugin indent on

### Powerline

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Lokaltog/vim-powerline.git

`~/.vimrc`

    set laststatus=2
    let g:Powerline_symbols = 'fancy'

#### Terminus-Powerline.ttf

    $ sudo pacman -S terminus-font
    $ cd ~/.fonts
    $ wget https://gist.github.com/mikkeloscar/2416601/raw/18badb5d7af64b350c2864e548d5bc3912dffcac/Terminus-Powerline.ttf
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

### Command-T

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/wincent/Command-T.git
    $ cd command-t/ruby/Command-T
    $ ruby extconf.rb
    $ make

`~/.vimrc`

    call pathogen#helptags()

## Referencias

*   http://vim.wikia.com/wiki/Folding
*   https://gist.github.com/mikkeloscar/2416601
