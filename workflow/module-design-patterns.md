# background

## `this`

*   we can use it only inside a **function**
*   if the function is a **member** of object *x*, `this` becomes a reference
    to *x*
*   if not, `this` is a reference to **global object** except in
    `"strict mode";` where an exception is launched

## constructores

*   they are functions (not methods) where we can attach properties to `this`
    and they become properties of the instance object created when the
    constructor is called using `new`
    
*   avoid attaching methods to `this`. Every instance gets a copy of that
    methods using memory for it what can be easily avoided attaching methods
    to the `prototype` constructor property

# constructor patterns

## collection

A collection of decoupled functions.

The functions doesn't make use of `this` so the user does not need to call
`new`. Is possible to call directly from `prototype` and is also possible to
copy the function reference without using `bind`

*   example of implementation: `shelljs/prj/lib.js`
*   example of use: `shelljs/prj/prj-init.js`
    *   why is possible to access module properties without accessing through
        `prototype` when no instance is created with `new`?

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

## call `new` at `require` time

*   antipattern?
*   explain differences: single instance vs multiple instances
*   example of implementation: `shelljs/prj/prj-work.js`

## singleton

*   how to implement it?

## use a closure instead of `this`

*   pattern name: reveal, module, ...?
*   example of implementation: `corejs/lup/lup.js`

## exception when `new` not used

*   stackoverflow thread?

## autoinstatiate when `new` not used

*   stackoverflow thread? (same as above)

## autoinstantiate with arguments

*   [use of apply with new ooperator][1]
*   this is useful when the constructor is overloaded

[1]: http://stackoverflow.com/questions/1606797/use-of-apply-with-new-operator-is-this-possible
