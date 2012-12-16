# informix client sdk

## descargar

*   fuente: http://www14.software.ibm.com/webapp/download/search.jsp?rs=ifxdl
*   cambiar el filtro de OS a `linux x86` o `linux x86_64`
*   descargar la version `3.50`

También se puede descargar desde bitbucket como se muestra en el ejemplo mas
abajo

## Requerimientos

Usuario y grupo `informix`

    $ sudo groupadd informix
    $ sudo useradd \
      -g informix \
      -G users,audio,lp,optical,storage,video,wheel,games,power,scanner \
      -s /bin/bash \
      -m \
      informix

Añadir programadores a grupo informix

    $ sudo usermod -g users -G audio,lp,optical,storage,video,wheel,games,power,scanner,informix pau

Instalar `bc` y `java`

    $ sudo pacman -S bc jre7-openjdk

## Instalación

ir a directorio de descargas

    $ su -l informix
    $ mkdir csdk
    $ cd csdk
    $ wget http://bitbucket.org/resetcontrol/downloads/clientsdk.3.50.FC9.LINUX_x86_64.tar
    $ tar xf clientsdk.3.50.FC9.LINUX_x86_64.tar
    $ sudo ./installclientsdk

Se aceptan los valores por defecto

# unixodbc

## Instalación

### Archlinux

    $ sudo pacman -S unixodbc

### OpenSUSE

    $ sudo zypper in unixodbc

## Configuración

info: http://www.unixodbc.org/doc/informix.html

`$HOME/.bashrc`

    export INFORMIXDIR=/home/informix/csdk
    export ODBCINI=/etc/odbc.ini

`/etc/hosts`

    <db_server_ip> <db_server_hostname>

Ej:

    192.168.0.3 SrvLinux

`$INFORMIXDIR/etc/sqlhosts`

    <service_name> <conn_type> <db_server_hostname> <service_app>

Ej:

    sr_linux sesoctcp SrvLinux sqlexec

`/etc/ld.so.conf.d/informix.conf`

    /home/informix/csdk/lib
    /home/informix/csdk/lib/cli
    /home/informix/csdk/lib/esql

reconfigurar loader

    $ sudo ldconfig

`/etc/odbcinst.ini`

    [Informix]
    Description=Informix SE
    Driver=/home/informix/csdk/lib/cli/libifcli.so
    APILevel=1
    ConnectFunctions=YYY
    DriverODBCVer=03.00
    FileUsage=0
    SQLLevel=1
    smProcessPerConnect=Y

`/etc/odbc.ini`

    [<odbc_name>]
    Driver=Informix
    Server=<service_name>
    Database=<db_path>/<db_name>
    LogonID=<user>
    Pwd=<pass>
    CLIENT_LOCALE=en_us.cp1252
    DB_LOCALE=en_us.cp1252
    TRANSLATIONDLL=/home/informix/csdk/lib/esql/igo4a304.so

Ej: (frutinter)

    [frutinter]
    Driver=Informix
    Server=sr_linux
    Database=/disk2/primer/tmp/reset/frutinter/fruita
    LogonID=reset
    pwd=<pass de reset en la 0.3>
    CLIENT_LOCALE=en_us.cp1252
    DB_LOCALE=en_us.cp1252
    TRANSLATIONDLL=/home/informix/csdk/lib/esql/igo4a304.so

`/etc/services`

*   eliminar las lineas de sqlexec
*   hacer entrada en 1525

        <service_name>         <port>/tcp    # informix se

    Ej:

        sqlexec 1525/tcp # informix se

# node-odbc

    $ npm install odbc
    $ cd node_modules/odbc
    $ ln -s build/Release/odbc_bindings.node .

# tutorial source

[http://blogabill.billiouw.com/nodejs-node-odbc-module-with-native-sql-server-driver-for-linux-2/]()

# odbc.js

    #!/usr/bin/node

    var sys = require("util"),
        odbc = require("odbc"),
        db = new odbc.Database(),
        syntax = "SELECT * FROM table";

    db.open("DSN=<odbc_name>", function (err) {
        db.query(syntax, function (err, rows, moreResultSets) {
        console.log(rows[0].YourFieldName);
        sys.debug(sys.inspect(rows));
        db.close(function () {});
        });
    });
