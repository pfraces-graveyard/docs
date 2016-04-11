Functional Programming with JavaScript
======================================

Interfaces
----------

An **interface** is a [JSON Schema][1] definition with the required fields

A data structure or primitive **implements** an interface if at least owns that interface schema

A **function interface** defines a schema for its params and a schema for its returned value

Filters
-------

A filter is a *function interface* which:

*   receives the standard array callback arguments `(item, index, arr)`
*   returns a `boolean`

The verb ***filter*** is related to passing through values

A filter returns:

*   `true` for the values to be passed through
*   `false` for the values to be filtered out

### Odd

Filters odd values. *(filters out even values)*

```js
var odd = function (item) {
    return item % 2;
}
```

Filter modifiers
----------------

A filter modifier is a *function interface* which:

*   receives a *filter*
*   returns a *filter*

### Not

Negate a filter.

Returns a new filter which filters out the values that will be passed through the original filter

```js
var not = function (filter) {
    return function () {
        return !filter.apply(null, arguments);
    };
};
```

Filter composition
------------------

```js
var even = not(odd);
```

[1]: http://json-schema.org/
