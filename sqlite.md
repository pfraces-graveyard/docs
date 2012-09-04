# sqlite

[http://www.sqlite.org/]()

# migración desde informix se

## exportar base de datos informix se

    $ cd /path/to/database
    $ dbexport database

## limpiar schema

    $ cat database.exp/database.sql | 
        tr '\n' ' ' | 
        sed -r 's/[ ]+/ /g' | 
        sed 's/; /;\n/g' | 
        grep -v '^{' | 
        grep -v '^grant' | 
        grep -v '^revoke' | 
        grep -v '^create index'| 
        sed 's/"reset"[.]//g' | 
        sed 's/, /,\n  /g' | 
        sed 's/ );/\n);/g' | 
        sed 's/ ( / (\n  /g' > schema.sql

## volcar schema en nueva base de datos sqlite3

    $ cat schema.sql | sqlite3 newdb
