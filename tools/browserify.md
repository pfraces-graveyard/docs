# browserify

[https://github.com/substack/node-browserify]()

Convierte código de node.js a código que se ejecuta en el navegador

# instalación

    # npm install -g browserify

# uso
    
    $ browserify client.js |
        uglifyjs > public/javascripts/client.min.js
