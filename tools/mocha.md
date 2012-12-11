# Mocha

http://visionmedia.github.com/mocha/

> _Mocha is a feature-rich JavaScript test framework running on node and the 
  browser, making asynchronous testing simple and fun. Mocha tests run serially, 
  allowing for flexible and accurate reporting, while mapping uncaught exceptions 
  to the correct test cases_

# Installation

    $ npm install -g mocha

# Assertions

> _Mocha allows you to use any assertion library you want, if it throws an error, 
  it will work! This means you can utilize libraries such as should.js, node’s 
  regular assert module, or others._

## Assertion libraries

*   https://github.com/visionmedia/should.js
*   http://chaijs.com/

Pensaba empezar probando **should.js** (usada en los ejemplos de mocha) ya que 
sólo contiene el api should (mientras que chai tiene should, expect y assert) por
que encuentro el api should el más elegante y por aquello de mantener un 
minimalismo en el código propio y en el de las librerias elegidas...

Pero he visto el potencial de sinon.js y por el momento no he encontrado un api más
elegante que usándolo con chai mediante sinon-chai.

*   https://github.com/visionmedia/mocha/wiki
*   http://sinonjs.org/
*   https://github.com/domenic/sinon-chai
*   https://gist.github.com/1394528 (cómo preparar entorno de tests en node)

Así que empezaré con:

*   mocha
*   chai (should style assertions)
*   sinon
*   sinon-chai

Aunque no he visto cómo correr tests en el navegador y reportar desde consola (a 
la buster) con mocha, por lo que buster sigue siendo una opción a tener en cuenta

*   

# Examples

## Synchronous code

> _Omit the callback and Mocha will automatically continue on to the next test._

    describe("Array", function(){
      describe("#indexOf()", function(){
        it("should return -1 when the value is not present", function(){
          [1,2,3].indexOf(5).should.equal(-1);
          [1,2,3].indexOf(0).should.equal(-1);
        })
      })
    })

## Asynchronous code

> _Invoke the callback when your test is complete. By adding a callback (usually 
  named **done**) to `it()` Mocha will know that it should wait for completion._

> _The `done()` callback accepts an error, so we may use this directly_

    describe("User", function(){
      describe("#save()", function(){
        it("should save without error", function(done){
          var user = new User("Luna");
          user.save(done);
        })
      })
    })

## Hooks

> _All hooks may be sync or async as well, behaving much like a regular test-case. 
  For example you may wish to populate database with dummy content before each 
  test_

    describe("Connection", function(){
      var db = new Connection
        , tobi = new User("tobi")
        , loki = new User("loki")
        , jane = new User("jane");
    
      beforeEach(function(done){
        db.clear(function(err){
          if (err) return done(err);
          db.save([tobi, loki, jane], done);
        });
      })
    
      describe("#find()", function(){
        it("respond with matching records", function(done){
          db.find({ type: "User" }, function(err, res){
            if (err) return done(err);
            res.should.have.length(3);
            done();
          })
        })
      })
    })

## Pending tests

> _Pending test-cases are simply those without a callback_

    describe("Array", function(){
      describe("#indexOf()", function(){
        it("should return -1 when the value is not present")
      })
    })

## Exclusive tests

> _The exclusivity feature allows you to run only the specified suite or test-case 
  by appending .only() to the call_

    describe("Array", function(){
      describe.only("#indexOf()", function(){
        ...
      })
    })

> _Or a specific test-case_

    describe("Array", function(){
      describe("#indexOf()", function(){
        it.only("should return -1 unless present", function(){
          ...
        })

        it("should return the index when present", function(){
          ...
        })
      })
    })

> _Note that currently only one `.only()` call is respected_

## Inclusive tests

> _This feature is similar to `.only()`, however by appending `.skip()` you may 
  tell Mocha to simply ignore these suite(s) and test-case(s). This puts them in a 
  pending state, and **is favoured over commenting out tests which you may forget 
  to uncomment**_

    describe("Array", function(){
      describe.skip("#indexOf()", function(){
        ...
      })
    })
