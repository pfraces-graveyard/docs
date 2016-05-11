frontend cheatsheet
===================

eslint
------

### rules

<http://eslint.org/docs/rules/>

### ignore line

```js
console.log('foo'); // eslint-disable-line
```
<http://eslint.org/docs/user-guide/configuring.html#configuring-rules>

jshint
------

### rules

<http://jshint.com/docs/options/>

### ignore line

```js
console.log('foo'); // jshint ignore:line
```

bootstrap css
-------------

bootstrap 3 mobile first breakpoints

```css
/* Custom, iPhone Retina */ 
@media only screen and (min-width : 320px) { }

/* Extra Small Devices, Phones */ 
@media only screen and (min-width : 480px) { }

/* Small Devices, Tablets */
@media only screen and (min-width : 768px) { }

/* Medium Devices, Desktops */
@media only screen and (min-width : 992px) { }

/* Large Devices, Wide Screens */
@media only screen and (min-width : 1200px) { }
```

angular
-------

### di from devtools

```js
window.require = function (service) {
  var appElement = document.querySelector('[ng-app]');
  return angular.element(appElement).injector().get(service);
};
```

### controller scope from devtools

**Using $0**

`$0` returns the most recently selected element

```js
angular.element($0).scope()
```

**Using querySelector**

```js
window.scope = function (ctrl, alias) {
  if (alias) { ctrl += ' as ' + alias; }
  var ctrlElement = document.querySelector('[ng-controller="' + ctrl + '"]');
  var scope = angular.element(ctrlElement).scope();
  if (alias) { scope = scope[alias]; }
  return scope;
};
```

```js
ctrl('myCtrl').exposedFunction();       // ng-controller="myCtrl"
ctrl('myCtrl', 'vm').exposedFunction(); // ng-controller="myCtrl as vm"
```

Reference: <http://stackoverflow.com/a/13744085/1815446>
