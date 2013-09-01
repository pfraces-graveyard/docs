# enlaces

[1]: http://daringfireball.net/projects/markdown/syntax#link
[1] <http://daringfireball.net/projects/markdown/syntax#link>  

# convenciones

*   escribir las cabeceras con '#', en lugar de '=' o '-'. rápido y elegante
*   linea en blanco al final de cada sección
*   negritas y cursivas con '*' en lugar de '_'
*   listas no numeradas con * y 3 espacios (4 caracteres)
*   listas numeradas con numero correcto, punto y los espacios que falten hasta 
    usar 4 caracteres
*   saltos de linea acabando con dos espacios
*   enlaces al principio de documento y abreviaciones a esos enlaces dentro del
    documento
*   código de ejemplo con 4 espacios al principio de linea
*   sin puntos al final de párrafo
*   sin mayúsculas
*   cuando haya overflow de linea, poner el excedente en otra linea con
    espacios al principio para mantener el sangrado

# tips

*   al poner dos espacios al final de linea, hace un salto de linea al renderizar

# preguntas

## cómo se hacen cuadros de código de ejemplo

*   empezando cada linea con 4 espacios

## cómo se evita la interpretación de su sintaxis para mostrarla en el navegador

## negritas y cursivas

    **negritas**
    *cursivas*

*   ejemplo

    *   **negritas**
    *   *cursivas*

## links

### externos

    [foo](http://www.foo.com)
    <http://www.foo.com> # sin http no vá

### internos

    [foo](demo) # relativa a la localización del documento en que se encuentra
    [foo](/demo) # relativa al document root

### [[1][]] reference-style links

*   para definirlo:

    [id]: http://sample.url

*   para llamarlo

    \[id][]




