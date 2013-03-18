# Git

Distributed version control system

# General workflow

## Check status

### Show working directory status

    $ git status

`git status` muestra mucha información útil:

* ficheros no versionados
* ficheros versionados con modificaciones pendientes de versionar
* ficheros renombrados o eliminados

Además en cada sección indica los comandos que se deben usar para configurar el
siguiente commit

### Show differences between working directory and stage

    $ git diff <file>

## Commit

### Prepare stage

Track untracked files and add modifications to the stage

    $ git add .

Este comando añadirá **todos** los ficheros nuevos (no ignorados) y todos los 
modificados desde el último commit al stage, lo que significa que se subirán
al repositorio local con el siguiente commit

Se pueden elegir parte de los archivos nuevos o modificados para subir con el
siguiente commit, dejándo los otros pendientes. Para conseguirlo, se deben
especificar los archivos que se desean añadir al stage individualmente

    $ git add path/to/file path/to/anotherfile

### Commit changes to local repository

Upload staged modifications and new tracked files to local repo

    $ git commit

Se abrirá vim mostrando la parte de `git status` que afecta al commit, es
decir, las modificaciones añadidas al stage mediante `git add`

Se debe introducir el mensaje de commit a partir de la 1era linea, dejando
el log de modificaciones por debajo

Se pueden añadir todas las modificaciones al stage sin hacer previamente
`git add` mediante el flag `-a`, aunque esto no añadirá los untracked files
(ficheros del working dir que no están la última revisión del repo)

    $ git commit -a

Se puede pasar el mensaje directamente por linea de comandos pero no es una
práctica recomendada

    $ git commit -m 'mensaje de commit'

Se recomienda crear mensajes de commit de máximo 50 caracteres con una breve
descripción de las modificaciones del commit

Se recomienda usar imperativos (`fix something` sobre `fixed something`)

Si se requiere aportar una descripción mas detallada se debe hacer en un
parrafo aparte, dejando una linea en blanco de separación. Este párrafo puede
tener hasta un máximo de 72 caracteres por linea.

## Sync repos

### Upload local modification to a remote repo

    $ git push <remote> <branch>

Example:

    $ git push origin master

### Download modifications from a remote repo

    $ git pull <remote>

# Configuration

## Prepare environment

Gvim (a diferencia de vim) necesita el flag `-f` para mantenerse en foreground 
y hacer que git espere a que finalice la edición del mensaje de commit. De lo
contrario git abortará por mensaje vacio

    $ git config --global core.editor "gvim -f"
    $ git config --global user.email "you@example.com"
    $ git config --global user.name "Your Name"

## Overriding settings in individual repos

    $ cd my_repo/
    $ git config user.name "Different Name"
    $ git config user.email "different@email.com"

## Password catching

Only works when you clone an HTTPS repo URL.

    $ git config --global credential.helper "cache"

By default git will cache your password for 15 minutes. You can change this if
you like (setting is in seconds).

    $ git config --global credential.helper "cache --timeout=3600"

## Shortcuts

`~/.bashrc

    # git aliases

    alias gs='git status'
    alias gl='git log --oneline'
    alias gc='git add . && git commit'

    alias gh='git push gh master && git push gh --tags'
    alias bb='git push bb master && git push bb --tags'

## External tools

### meld

Ver diferencias con meld

#### Instalar meld

    $ sudo pacman -S meld pygtksourceview2

#### Cambiar el programa que usa git para mostrar diferencias

`/usr/local/bin/gitdiff`

    #!/bin/bash
    /usr/bin/meld "$2" "$5" 2> /dev/null

Hacer ejecutable y configurar git

    $ sudo chmod +x /usr/local/bin/gitdiff
    $ git config --global diff.external gitdiff


# Creating a new repository

## From scratch

    $ mkdir /path/to/repo
    $ cd /path/to/repo
    $ git init

## Clone an existing one

    $ git clone https://github.com/<repo_owner>/<repo_name>
    $ cd <repo_name>

**https** is the recommended protocol for using with git

It is easier to work by including your user in the following manner

    $ git clone https://<your_user_name>@github.com/<repo_owner>/<repo_name>

Tested on:

* github
* bitbucket

# Remotes

Repositorios remotos vinculados

## Show remotes

    $ git remote

## Change remotes

    $ git remote set-url origin git://new.url.here

# Ignoring files

If you create a file in your repo named **.gitignore** git will use its rules
when looking at files to commit. Note that git will not ignore a file that was
already tracked before a rule was added to this file to ignore it. In such a
case the file must be un-tracked, usually with 

    $ git rm --cached filename
 
A global **.gitignore** file can also be used by adding one to your global git
config. For example, you might create the file
 
    ~/.gitignore_global 
 
and add some rules to it. To add this to your config, run
 
    $ git config --global core.excludesfile ~/.gitignore_global

# Branching

Create and switch to a new branch

    $ git checkout -b 'newBranch'

Switch to an existing branch

    $ git checkout 'oldBranch'

# Tagging

Listing the available tags

    $ git tag

Create annotated tag

    $ git tag -a v1.4 -m 'my version 1.4'

Sharing tags

    $ git push origin --tags

See tag info

    $ git show v1.4

Tagging later

    $ git tag -a v1.2 9fceb02

# Submodules

Repositorios anidados

## Create submodule

    $ git submodule add https://repo.git git_modules/repo

## Remove submodule

1.  Delete the relevant section from the .gitmodules file.
2.  Delete the relevant section from .git/config.
3.  Run git rm --cached path_to_submodule (no trailing slash).
4.  Commit and delete the now untracked submodule files.

# Merging

## Merge branch to master

    $ git checkout master
    $ git merge <branch>

# Recomendaciones

* Renombrar archivos en commits separados de los commits de modificación

  Al consultar un commit, se deben ver claramente las modificaciones hechas.
  Pero los archivos renombrados aparecen como eliminados y creados, haciéndo
  dificil encontrar las modificaciones de código en ese commit. Especialmente
  las modificaciones hechas en archivos renombrados se han de encontrar
  buscando manualmente las diferencias entre el archivo eliminado y el nuevo
  creado

# References

*   http://book.git-scm.com
*   https://help.github.com/articles/set-up-git
*   http://stackoverflow.com/questions/1260748/how-do-i-remove-a-git-submodule
*   https://help.github.com/articles/ignoring-files
*   http://wiki.domain.com/diaries/20120311_trac
*   http://git-scm.com/book/en/Git-Basics-Tagging
*   http://stackoverflow.com/questions/2432764 
*   http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
