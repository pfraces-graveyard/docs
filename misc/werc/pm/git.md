# enlaces

[1]: http://book.git-scm.com
[2]: http://wiki.domain.com/diaries/20120311_trac

[1] <http://book.git-scm.com>  
[2] <http://wiki.domain.com/diaries/20120311_trac>  

# objetivo

Poder versionar los proyectos desde el principio

# propuesta

*   Crear un workflow lo mas sencillo posible e ir mejorándolo con la práctica
*   No se debe leer más de lo requerido para empezar a hacer revisiones
*   Sólo cuando se esté familiarizado con el workflow básico, se leerá [git]

# requerimientos

## crear repositorio

*   Debe ser accesible desde:
    *   la carpeta personal de cada usuario
    *   trac
    *   gitweb
    *   la red local
    *   internet
*   El esquema mas sencillo posible
*   Se creará un repo central y el resto de repos atacarán a él en estrella

# workflow

El repo central estará aislado, no se trabajará en su misma carpeta

El resto de repos que atacan al central serán repos locales y estarán en las
carpetas de desarrollo, donde los fuentes son modficados

# comandos

## crear un repo central

        $ cd /srv/http/git
        $ sudo mkdir playground.git
        $ sudo git init --bare playground.git/

>   Initialized empty Git repository in /srv/http/git/playground.git/

## clonar del repo central a una carpeta personal en el mismo servidor

        $ cd ~/dev
        $ git clone /srv/http/git/playground

>   Cloning into 'playground'...  
>   done.  
>   warning: You appear to have cloned an empty repository.  

## agregar todo al control de versiones local

        $ cd ~/dev/playground
        $ git add .

## subir modificaciones al repo local

        $ cd ~/dev/playground
        $ git commit -am <msg>

## comprobar estado de la copia de trabajo

        $ cd ~/dev/playground
        $ git status

>   # On branch master
>   nothing to commit (working directory clean)

## comprobar estado del repo local

### modo gráfico

        $ cd ~/dev/playground
        $ gitk


### de dónde ha sido clonado

        $ cd ~/dev/playground
        $ git config --get remote.origin.url

>   /srv/http/git/playground

## subir revisiones del repo local al repo central

        $ cd ~/dev/playground
        $ sudo git push /srv/http/git/playground.git master














