New approach to angular models
==============================

This approach lets you to easily identify your model properties

*(Thanks to [@maldo](https://github.com/maldo) for this great improvement!)*

What does it solve?
-------------------

The previous approach used was based on taking advantage of angular's singleton services
to simply define aliases for object references

```js
angular.module('app.model.myModel', [])

.factory('myModel', function () {
	return {};
});
```

This is a straightforward implementation but in order to know what properties are defined
in the model it requires runtime object inspection or a grep-like search in all project
sources. Both alternatives are a pain

The new approach defines a getter/setter method for each property. That way you can know
the properties used in the model by simply reading the exposed functions in your service
