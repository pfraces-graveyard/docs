# Fastcgi
*   dejar las pruebas de fastcgi para mas adelante, de momento tiraremos con cgi
*   un par de ejemplos simples de como usar c con fastcgi está en /home/pau/dev/test/fcgi
*   para probar un programa fastcgi:
    *   lanzarlo con spawn-fcgi contra un puerto: 9002, 9003, ... con usuario www-data y desde rc.conf DAEMONS array.
    *   Consultar el script /etc/rc.d/fcgiwrap
    *   crear un server en /etc/nginx/conf/nginx.conf que escuche al  puerto usado
    *   atacar al server desde un navegador web

