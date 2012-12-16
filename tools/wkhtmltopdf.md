# wkhtmltopdf

Convierte páginas web a pdf

Se usa para generar facturas en pdf:

1.  Se genera una web con la factura
2.  Se convierte a pdf
3.  Se envia al destino elegido (impresora, fax, email, ...)

**Nota:** phantomjs hace lo mismo y ofrece mayor control, es conveniente
tenerlo en cuenta para futuras versiones

# Instalar

## Archlinux

    $ pacman -S wkhtmltopdf

## OpenSUSE

Método agnóstico a distribuciones. Binario provisto por los devs

    $ cd $HOME
    $ mkdir wkhtmltopdf
    $ cd wkhtmltopdf
    $ wget http://wkhtmltopdf.googlecode.com/files/wkhtmltopdf-0.11.0_rc1-static-i386.tar.bz2
    $ tar xjf wkhtmltopdf-0.11.0_rc1-static-i386.tar.bz2
    $ mv wkhtmltopdf-i386 wkhtmltopdf

# Modo de empleo

Dá errores (Qpixmap) si no se tiene X levantado, pero aún así, el pdf se genera
correctamente

    $ ./wkhtmltopdf www.google.com output.pdf
