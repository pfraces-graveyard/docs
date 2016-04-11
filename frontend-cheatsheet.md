frontend cheatsheet
===================

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
