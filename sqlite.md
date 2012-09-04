# sqlite

[http://www.sqlite.org/]()

# instalar conector

    $ npm install sqlite3

# migración desde informix se

## exportar base de datos informix se

    $ cd /path/to/database
    $ dbexport database

## schema

### limpiar schema

    $ cat database.exp/database.sql | 
        grep -v '^{' | 
        tr '\n' ' ' | 
        sed -r 's/[ ]+/ /g' | 
        sed 's/; /;\n/g' | 
        grep -v '^[ ]*grant' | 
        grep -v '^[ ]*revoke' | 
        grep -v '^[ ]*create unique'| 
        grep -v '^[ ]*create index'| 
        sed 's/"reset"[.]//g' | 
        sed 's/, /,\n  /g' | 
        sed 's/ );/\n);/g' | 
        sed 's/ ( / (\n  /g' |
        sed 's/datetime.*,$/text,/' |
        sed 's/datetime.*$/text/' |
        sed 's/default.*,$/,/' | 
        sed 's/default.*$//' |
        sed 's/not null.*,$/,/' |
        sed 's/not null.*$//' |
        sed 's/^[^}]*}//' > schema.sql

### volcar schema en nueva base de datos sqlite3

    $ cat schema.sql | sqlite3 newdb

## datos

### mapear archivos a tablas

    $ cat database.exp/database.sql |
        grep '^{' | 
        sed 's/{ TABLE //' | 
        sed 's/ row size.*$//' | 
        sed 's/{ unload file name = //' | 
        sed 's/ number of rows.*$//'  | 
        tr '\n' ' ' | 
        sed 's/[.]unl /.unl\n/g' | 
        grep -v DATABASE | 
        sed 's/^".*"[.]//' > map

### preparar datos

Se crea un directorio para los datos retocados

    $ mkdir raw.data

Dentro se irán poniendo los datos con el nombre de tabla que les corresponde
según el mapeo

    $ cp raw.exp/file.unl raw.data/table.unl

Luego se intenta importar el fichero y se va modificando si hay errores

La carpeta raw.exp no debe ser modificada para mantener el estado original
de la exportación de datos

### importar fichero

    $ echo .import raw.data/ffclient.unl ffclient | sqlite3 raw.sqlite
