# Ejecución
    $ su
    $ spawn-fcgi -a 127.0.0.1 -p 9001 -u www-data -f /usr/sbin/fcgiwrap

En **/etc/nginx/conf/nginx.conf**

    fastcgi_pass 127.0.0.1:9001;
    fastcgi_param SCRIPT_FILENAME /srv/http/werc/bin/werc.rc;

# Instalación y configuración
    # instalado en /src/http
    
    $ cd /srv/http/werc/sites
    $ sudo cp -r default.cat-v.org/ localhost
    $ echo '# Hello World!' > /tmp/index.md
    $ sudo mv /tmp/index.md localhost
    
    # You probably will want to to use fcgiwrap, called from spawn-fcgi or 
    # similar.
    
    $ sudo pacman -S fcgiwrap
    
    # incluye spawn-fcgi por lo que supongo que puedo desinstalar fcgi
    # y usar spawn-fcgi en lugar de cgi-fcgi, aunque de momento...
    
    $ cgi-fcgi -start -connect localhost:9001 /usr/sbin/fcgiwrap
    
    # actualmente uso spawn-fcgi, pero no puedo desinstalar fcgi ya que es una
    # dependencia de fcgiwrap
    
    $ spawn-fcgi -a 127.0.0.1 -p 9001 -u www-data -f /usr/sbin/fcgiwrap
    
    # desabilitar debug
    #   en werc/etc/initrc:
    #     sustituir debug=true
    #           por debug=( )
    
    # eliminar cabecera y barra de navegacion superior
    
    $ echo > _werc/lib/top_bar.inc
    $ echo > _werc/lib/headers.inc
    
    # crear titulo y subtitulo
    # en _werc/config:
    
    siteTitle='titulo'
    siteSubTitle='subtitulo largo descriptivo'
    
    # habilitar wiki y comentarios
    # en _werc/config:
    
    conf_enable_comments
    conf_enable_wiki
    
    # eliminar la busqueda en google y alinear 'powered by werc' a la derecha
    
    $ echo '
        <div class="right">
            <a href="http://werc.cat-v.org/">Powered by werc</a>
        </div>
    ' > _werc/lib/footer.inc
    
    # werc/README
    #
    # It is recommended that you make werc.rc handle all non-static files (this can
    # be done by setting it up as your 404 handler) and setup your virtual hosts to
    # handle static files by setting the document root for the domain to
    # /path-to-werc-installation/sites/yourdomain.com/
    #
    # If you will want to allow updates via the web interface (eg., for wiki or
    # comments apps) make sure all files under sites/ are writable by the user your
    # cgi will run as, usually www-data, for example by doing:
    
    $ cd /srv/http/werc
    $ sudo chown -R :www-data sites/
    $ sudo chmod -R g+w sites/

**[TODO]**

*   source /etc/profile.d/plan9.sh en daemon fcgiwrap
*   <https://bbs.archlinux.org/viewtopics.php?id=93418>
    
## dirdir
    # All needed to setup diridiri is to set a flag in your _werc/config file.
    # Just login, go to any page, and click the Edit button.
    # To create a new page, go to the address where you want to create the new
    # page, click Edit, enter the initial contents, Save, and you are done.


## user account
    # A user account consists of a directory under etc/users/ that contains files
    # with that users account information, the only required file is password
    # containing a password for the user
    # The group 'admin' is 'built-in' and any members in that group will have admin
    # privileges for most werc apps by default.
    
    # Para logarse hay que acceder a la web _users/login
    # Para crear un enlace en la barra de navegacion superior a la pagina de login
    # hay que añadir a _werc/lib/top_bar.inc:
    
    <div class="right">
        <a href="_users/login">login</a>
    </div>
    
    # He habilitado la cuenta de administrador:
    # user: admin
    # pass: admin
    
    # como no se como hacer que cgi-fcgi se lance con  un usuario y grupo concreto
    # voy a probar con spawn-cgi, el cual (aparte de tener una bonita man page)
    # tiene opciones para especificarlo
    
    $ sudo groupadd www-data
    $ sudo useradd -g www-data www-data
    $ spawn-fcgi -a 127.0.0.1 -p 9001 -u www-data -f /usr/sbin/fcgiwrap
    
    # la edicion funciona si se lanza spawn-fcgi desde root (con su, no con sudo),
    # ademas no es necesario especificar usuario, por lo que se puede volver a
    # dejar el directorio con permisos root:root aunque supongo que sera mas seguro
    # lanzarlo como www-data

# Links
- <http://werc.cat-v.org>

# Tips
- Al crear los archivos separando las palabras con '\ ', no aparecen; pero con '_' aparecen con espacios

# Preguntas
## cómo crear páginas desde el interfaz web
## cómo crear índices automáticamente
## cómo crear extensiones
## cómo cambiar css
### cómo indentar más las listas anidadas
## cómo crear carpetas desde el interfaz web
## como editar sólo una sección














