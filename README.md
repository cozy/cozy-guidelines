# Cozy Code Guidelines

## Generic code style

```
"eslintConfig": {
    "extends": ["eslint-config-cozy-app"]
  },
  "prettier": {
    "semi": false,
    "singleQuote": true
  },
```

Let the formatters do their jobs.

# JavaScript

## Promises vs async/await

Always use async / await when applicable, instead of Promises and `then()` chains.

> Why ? Cleaner, Clearer, more readable, easier for handling errors
> See https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9

# React

## Class constructors

Avoid `constructor` if you can by leveraging [`transform-class-properties`](transform-class-properties).

> Why ? Less lines, easier to read, no need to call `super()`.

❌  Bad :

```
class MyComponent extends Component {
  constructor () {
    super()
    this.state = { counter: 0 }
  }
}
```

✅  Good

```
class MyComponent extends Component {
  state = { counter: 0 }
}
```

## Binding event handlers

Avoid binding event handlers in `constructor`, leverage `transform-class-properties`
and arrow functions.

> Why ? The [transform-class-properties](transform-class-properties)
way makes it easy to see, when the method is defined, that it is bound to the class
(whereas when using the constructor, you have to check the `constructor` to see if it is correctly bound).

❌  Bad :

```
class MyComponent extends Component {
  constructor () {
    super()
    this.onClick = this.onClick.bind(this)
  }

  onClick (ev) {
    ...
  }
}
```

✅  Good

```
class MyComponent extends Component {
  onClick = ev => {
    ...
  }
}
```

## What is Cozy?

![Cozy Logo](https://cdn.rawgit.com/cozy/cozy-guidelines/master/templates/cozy_logo_small.svg)

[Cozy](http://cozy.io) is a platform that brings all your web services in the
same private space.  With it, your web apps and your devices can share data
easily, providing you with a new experience. You can install Cozy on your own
hardware where no one profiles you.

## Community

You can reach the Cozy Community by:

* Chatting with us on IRC #cozycloud on irc.freenode.net
* Posting on our [Forum](https://forum.cozy.io)
* Posting issues on the [Github repos](https://github.com/cozy/)
* Mentioning us on [Twitter](http://twitter.com/mycozycloud)

[transform-class-properties]: https://babeljs.io/docs/plugins/transform-class-properties/
