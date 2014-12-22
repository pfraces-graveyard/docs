Use gvim like an ide
====================

*   [use vim like an IDE](http://vim.wikia.com/wiki/Use_Vim_like_an_IDE)
*   [buffers vs tabs](https://joshldavis.com/2014/04/05/vim-tab-madness-buffers-vs-tabs/)
*   [buffers](http://vim.wikia.com/wiki/Buffers)

Vim setup
---------

### auto resize

Auto resize layout proportionally when main window is resized

    :autocmd VimResized * :wincmd =

### airline

    cd ~/.vim/bundle
    git clone https://github.com/bling/vim-airline

#### Install fancy symbols

[powerline font installation](https://powerline.readthedocs.org/en/latest/installation/linux.html#font-installation)

Look for a valid font path with `xset q`

    cd <FONT_PATH>
    wget https://github.com/Lokaltog/powerline/raw/develop/font/PowerlineSymbols.otf
    fc-cache -vf <FONT_PATH>

    cd ~/.config/fontconfig/conf.d/
    wget https://github.com/Lokaltog/powerline/raw/develop/font/10-powerline-symbols.conf

#### Enable airline

```vimL
set guifont=terminus
set laststatus=2
let g:airline_powerline_fonts = 1
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#fnamemod = ':t'
```

### vimfiler

    cd ~/.vim/bundle
    git clone https://github.com/Shougo/unite.vim
    git clone https://github.com/Shougo/vimfiler.vim

#### Default profile

```vimL
call vimfiler#custom#profile('default', 'context', {
\ 'safe' : 0,
\ 'explorer' : 1,
\ 'split' : 1,
\ 'toggle' : 1,
\ 'no-quit' : 1
\ })
```

#### Open vimfiler if no file args passed

    autocmd VimEnter * if !argc() | VimFiler | endif

#### Default explorer

    let g:vimfiler_as_default_explorer = 1

#### Like Textmate icons.

```vimL
let g:vimfiler_tree_leaf_icon = ' '
let g:vimfiler_tree_opened_icon = '▾'
let g:vimfiler_tree_closed_icon = '▸'
let g:vimfiler_file_icon = '-'
let g:vimfiler_marked_file_icon = '*'
```

Project integration
-------------------

### Tabs and layouts

>   A buffer is the in-memory text of a file.
    A window is a viewport on a buffer.
    A tab page is a collection of windows.

#### Buffers

Create a new buffer

[TODO]

Open file in a new buffer

    :e filename

List buffers

    :ls

Move between buffers

*   `:bn`
*   `:bp`
*   `:b[buffer]`

Delete buffer

    :bd [buffer]

#### Windows

Create a new window

*   `:new`
*   `:vnew`

Open file in a new window

*   `:new filename`
*   `:vnew filename`

Move between windows

*   `Ctrl-W [hjkl]`

Delete window

*   `:q`

### file explorer

[vimfiler help](https://github.com/Shougo/vimfiler.vim/blob/master/doc/vimfiler.txt)

Open vimfiler

    :VimFiler

Normal mode default mappings

```
o     (vimfiler_expand_or_edit)
E     (vimfiler_split_edit_file)

~     (vimfiler_switch_to_home_directory)
\     (vimfiler_switch_to_root_directory)
&     (vimfiler_switch_to_project_directory)

r     (vimfiler_rename_file)
K     (vimfiler_make_directory)
N     (vimfiler_new_file)

<BS>  (vimfiler_switch_to_parent_directory)
.     (vimfiler_toggle_visible_ignore_files)
```
