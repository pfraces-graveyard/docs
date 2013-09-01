# playground

Lugar para pruebas cgi.

## Crear una prueba nueva:

*   crear un ejecutable y guardarlo en /srv/http/playground
*   se podrá acceder a él poniendo en el navegador: playground.domain.com/<ejecutable>
*   usa el puerto 9001 (esto se especifica en nginx.conf), donde escucha fcgiwrap (rc.conf DAEMONS), por tanto sólo se pueden crearpruebas cgi.

