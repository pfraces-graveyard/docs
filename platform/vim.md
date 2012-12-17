# Vim

# folding zr

*   `zr` open all folds
*   `zm` close all folds
*   `za` open or close current fold

# pathogen.vim

Instalador de plugins

    $ mkdir -p ~/.vim/autoload ~/.vim/bundle
    $ curl -Sso ~/.vim/autoload/pathogen.vim \
      https://raw.github.com/tpope/vim-pathogen/master/autoload/pathogen.vim

`~/.vimrc`

    call pathogen#infect()
    syntax on
    filetype plugin indent on

# plugins

*   git clone https://github.com/plasticboy/vim-markdown.git
*   git clone https://github.com/pangloss/vim-javascript.git
*   git clone https://github.com/digitaltoad/vim-jade.git
*   git clone https://github.com/wavded/vim-stylus.git

# Highlight

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
