javascript unit testing environment
===================================

pre-requisites
--------------

*   nodejs
*   gulp CLI `[sudo] npm install -g gulp`

setup `package.json`
--------------------

    npm init

install stack
-------------

### gulp

    npm install gulp --save-dev

### mocha

    npm install gulp-mocha --save-dev

### expect.js

    npm install expect.js --save-dev

setup `gulpfile.js`
-------------------

```js
var gulp = require('gulp');
var mocha = require('gulp-mocha');

gulp.task('test', function () {
  return gulp.src('**/*.spec.js', { read: false })
    .pipe(mocha({ reporter: 'list' }));
});
```

run tests
---------

    gulp test

create a failing test
---------------------

**sample.spec.js**

```js
var expect = require('expect.js'),
    sample = require('./sample');

describe('sample', function () {
  it('should be a function', function () {
    expect(sample).to.be.a('function');
  });
});
```

pass the test
-------------

**sample.js**

```js
module.exports = function () {};
```
