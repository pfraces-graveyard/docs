# Ejecución

    $ rc.d [start|stop|restart] nginx

# Instalación y configuración

    $ packer -S nginx

## ficheros de configuración

*   /etc/nginx/conf/nginx.conf
*   /etc/hosts

## virtual hosts

<http://blog.martinfjordvald.com/2010/07/nginx-primer/>

*   **server_name:** use this server block when the HOST header matches the value
*   **root:** what to use when looking for files.

Nginx will always choose the most specific match

He conseguido virtual hosts en localhost poniendo cada subdominio en /etc/hosts



