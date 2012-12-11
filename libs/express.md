# express

[http://expressjs.com/api.html]()

# instalación

Primero se debe instalar de forma global

    # npm install -g express

Luego, desde la carpeta raíz de cada proyecto en el que se quiera usar express

    $ express --css stylus
    $ npm install

Esto creará una aplicación express por defecto con jade y stylus

# levantar el servidor

    $ node app.js

# Variables de entorno

Para cambiar de entorno (development, production) se debe usar la varable de 
entorno NODE_ENV

    $ NODE_ENV=production node app.js
    
>   **env** Environment mode, defaults to process.env.NODE_ENV or "development"

Igualmente con el puerto, que por defecto es el 3000, puede cambiarse con
la variable de entorno PORT

    $ PORT=8080 node app.js
