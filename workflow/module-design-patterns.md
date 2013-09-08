# background

## `this`

*   sólo se puede usar dentro de una función
*   si la función es un método (es miembro de un objeto)
    *   `this` es una referencia al objeto

## constructores

*   funciones (que no métodos) que definen propiedades en `this`
*   si creamos funciones en `this` desde constructores
    *   cada instancia lleva una copia

# constructor patterns

## classic

    var YourModule = function (foo, bar) {
      this.foo = foo;
      this.bar = bar;
    }

    YourModule.prototype.x = function () {
      ...
    }

    ...

    module.exports = YourModule;

...

    var YourModule = require('ym');
    
    var ym = new YourModule("FOO", "BAR");

    console.log(ym.foo); // "FOO"
    console.log(ym.bar); // "BAR"

### benefits

*   clean and simple
*   performant prototype inheritance
*   instances share reference to methods

### drawbacks

*   cannot forget `new`
    *   exception only in `"strict mode";`
    *   global object reference otherwise
    *   *UpperCammelCase* annotations
