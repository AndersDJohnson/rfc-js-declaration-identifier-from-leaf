# rfc-js-declaration-identifier-from-leaf
A proposal for JS syntax to get declaration identifier from leaf.

Allow declaration (`const`/`let`/`var`) of variables from deep path access using the leaf identifier.

```js
const myObject.names()
```

equivalent to:

```js
const names = myObject.names()
```

And a similar syntax for object creation:

```js
const things = {
  myObject.names()
}
```

equivalent to:

```js
const things = {
  names: myObject.names()
}
```

And possibly a similar syntax for destructuring (with [rfc-js-destructuring-function-call](https://github.com/AndersDJohnson/rfc-js-destructuring-function-call) and [rfc-js-object-shorthand-path](https://github.com/AndersDJohnson/rfc-js-object-shorthand-path)):

```js
const {
  nestedObject.names(),
  other
} = myObject
```

equivalent to:

```js
const names = myObject.nestedObject.names()
const { other } = myObject
```


Could be combined with [rfc-js-destructuring-creation](https://github.com/AndersDJohnson/rfc-js-destructuring-creation).
