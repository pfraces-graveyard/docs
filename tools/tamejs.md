# tamejs

JavaScript code rewriter for taming async-callback-style code

*   http://tamejs.org/
*   https://github.com/maxtaco/tamejs

# Instalación

    $ npm install tamejs

# Uso

You can their either use the tamejs compiler on the command line, or as an
extension to node's module import system

Opto por el 2o método:

    require ('tamejs').register (); // register the *.tjs suffix
    require ("mylib.tjs");          // then use node.js's import as normal

# Ejemplo

`tamejs` introduce dos directivas a javascript: `await` y `defer`

    for (var i = 0; i < 10; i++) {
        await { setTimeout (defer (), 100); }
        console.log ("hello");
    }
