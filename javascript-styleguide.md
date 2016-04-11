JavaScript styleguide
=====================

Must Have
---------

  * Use semicolons
  * Always use `{}` in blocks
  * No newline before `{`
  * Newline before `}`. Same indentation as `{` line
  * Spaces between operators and operands
  * Spaces after semicolon, colon, comma
  * Spaces before and after grouping
  * Spaces between block delimiters and block content

### Avoid function one-liners

They are hard to debug since one cannot place a breakpoint inside the function body

**do**

```js
var foo = function () {
  return 'foo';
};
```

**don't**

```js
var foo = function () { return 'foo'; };
```

Nice To Have
------------


  * 2-spaces indentation
  * Single quotes
