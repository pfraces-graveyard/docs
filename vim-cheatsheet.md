Vim Cheatsheet
==============

Motions
-------

    [{           " jump to the beginning of a C code block
    }]           " jump to the end of a C code block
    
    [(           " jump to the beginning of a parenthesis
    )]           " jump to the end of a parenthesis

Windows
-------

    <C-w>s       " horizontal splitting
    <C-w>v       " vertical splitting

    :new <file>  " open <file> horizontal splitting
    :vnew <file> " open <file> vertical splitting

    <C-w>[hjkl]  " move between windows
    <C-w>p       " move to previous window

Buffers
-------

    :e <file>    " create a new buffer for <file>
    :b <buffer>  " show <buffer> in current window

Registers
---------

Registers are clipboards filled automátically when something is copied or deleted

    :reg         " list stored registers

Registers ids are a single character prefixed with `"`

    "xp          " paste the x register

VimFiler
--------

    <Space>      " toggle select current line
    <S-k>        " create directory
    <S-n>        " create file
    d            " delete file/selection
    r            " rename file/selection
    c            " copy file/selection to destination directory
    m            " move file/selection to destination directory
