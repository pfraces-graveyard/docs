# Docco

JavaScript annotated source documentation generator

# Instalar

## Archlinux

    $ pacman -S python2-pygments

# Uso

## Comentar

Poner comentarios de linea

    // Esto es un comentario de linea
    /* Esto es un comentario de bloque */

Los comentarios deben usar markdown

## Generar

    $ cd path/to/prj
    $ docco lib/*.js

>   docco: lib/index.js -> docs/index.html

Docco automáticamente genera la documentación bajo `./docs`
