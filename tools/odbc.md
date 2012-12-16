# informix client sdk

## descargar

*   fuente

    *   [http://www14.software.ibm.com/webapp/download/search.jsp?rs=ifxdl]()

*   cambiar el filtro de OS a "linux x86"
*   descargar

## instalar

requiere usuario y grupo "informix"

    $ sudo groupadd informix
    $ sudo useradd \
      -g informix \
      -G users,audio,lp,optical,storage,video,wheel,games,power,scanner \
      -s /bin/bash \
      -m \
      informix

requiere bc

    $ sudo pacman -S bc

ir a directorio de descargas

    $ mkdir csdk
    $ cd csdk
    $ tar xf ../clientsdk<tab>
    $ sudo ./installclientsdk

*   default install folder: /opt/IBM/informix
*   como solo quiero el odbc driver, desmarco todo excepto 9
*   GLS es necesario, asi que marco 12

una vez instalado se puede instalar el directorio de instalacion

    $ cd ..
    $ rm -r csdk

si hay errores con el instalador, se puede recurrir al método manual:

1.  Obtener una copia del tar con el directorio ya instalado (hay una copia en
    el ftp de la dmz, en el directorio /pau)

2.  Descomprimir el paquete

        $ sudo mkdir /opt/IBM
        $ cd /opt/IBM
        $ sudo tar xzf /path/to/informix-client.tar.gz
    
# unixodbc

## instalar

### Archlinux

    $ sudo pacman -S unixodbc

### OpenSUSE

    $ sudo zypper in unixodbc

## configurar

*   info

    *   [http://www.unixodbc.org/doc/informix.html]()

*   $HOME/.bashrc:

        export INFORMIXDIR=/opt/IBM/informix
        export ODBCINI=/etc/odbc.ini

*   /etc/hosts

        <db_server_ip> <db_server_hostname>

    Ej:

        192.168.0.3 SrvLinux

*   $INFORMIXDIR/etc/sqlhosts

        <service_name> <conn_type> <db_server_hostname> <service_app>

    Ej:

        sr_linux sesoctcp SrvLinux sqlexec

*   /etc/ld.so.conf.d/informix.conf

        /opt/IBM/informix/lib
        /opt/IBM/informix/lib/cli
        /opt/IBM/informix/lib/esql

*   reconfigurar loader

        $ sudo ldconfig

*   /etc/odbcinst.ini

        [Informix]
        Description=Informix SE
        Driver=/opt/IBM/informix/lib/cli/libifcli.so
        APILevel=1
        ConnectFunctions=YYY
        DriverODBCVer=03.00
        FileUsage=0
        SQLLevel=1
        smProcessPerConnect=Y

*   /etc/odbc.ini

        [<odbc_name>]
        Driver=Informix
        Server=<service_name>
        Database=<db_path>/<db_name>
        LogonID=<user>
        Pwd=<pass>
        CLIENT_LOCALE=en_us.cp1252
        DB_LOCALE=en_us.cp1252
        TRANSLATIONDLL=/opt/IBM/informix/lib/esql/igo4a304.so

    Ej: (frutinter)

        [frutinter]
        Driver=Informix
        Server=sr_linux
        Database=/disk2/primer/tmp/reset/frutinter/fruita
        LogonID=reset
        pwd=<pass de reset en la 0.3>
        CLIENT_LOCALE=en_us.cp1252
        DB_LOCALE=en_us.cp1252
        TRANSLATIONDLL=/opt/IBM/informix/lib/esql/igo4a304.so

*   /etc/services

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
