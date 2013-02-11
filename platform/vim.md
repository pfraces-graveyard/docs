# Vim

# folding zr

*   `zr` open all folds
*   `zm` close all folds
*   `za` open or close current fold

# Pathogen

Instalador de plugins

    $ mkdir -p ~/.vim/autoload ~/.vim/bundle
    $ curl -Sso ~/.vim/autoload/pathogen.vim \
      https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim

`~/.vimrc`

    call pathogen#infect()
    syntax on
    filetype plugin indent on

# plugins

## code highlight

    $ cd ~/.vim/bundle/

    $ git clone https://github.com/plasticboy/vim-markdown.git
    $ git clone https://github.com/pangloss/vim-javascript.git
    $ git clone https://github.com/MSch/vim-tamejs.git
    $ git clone https://github.com/digitaltoad/vim-jade.git
    $ git clone https://github.com/wavded/vim-stylus.git

## Powerline

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Lokaltog/vim-powerline

### Terminus-Powerline.ttf

    $ sudo pacman -S terminus-font
    $ cd ~/.fonts
    $ curl https://gist.github.com/mikkeloscar/2416601/raw/18badb5d7af64b350c2864e548d5bc3912dffcac/Terminus-Powerline.ttf
    $ fc-cache -vf

Add Terminus to `.vimrc`

    set guifont=Terminus\ for\ Powerline\ 8

## YouCompleteMe

CMake is required:

    $ pacman -S cmake

Install with Pathogen:

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/Valloric/YouCompleteMe.git
    $ cd YouCompleteMe
    $ ./install.sh

## Command-t

    $ cd ~/.vim/bundle/
    $ git clone https://github.com/wincent/Command-T.git
    $ cd command-t/ruby/Command-T
    $ ruby extconf.rb
    $ make

Under Pathogen it is necessary to do so explicitly from inside Vim:

    :call pathogen#helptags()

# Highlight overflow

*   Colorear el exceso de 79 caracteres

        highlight OverLength ctermbg=red ctermfg=white guibg=red guifg=white
        match OverLength /\%>79v.\+/

    Para una correcta visualización de código fuente se recomienda que se use
    una fuente monoespaciada y no superar los 80 caracteres. Debido a que hay
    algunos terminales que usan el 80º caracter como caracter de control, se
    coloreará a partir de 79 caracteres asegurando así la correcta
    visualización en cualquier medio

# Referencias

*   http://vim.wikia.com/wiki/Folding
*   https://gist.github.com/mikkeloscar/2416601
