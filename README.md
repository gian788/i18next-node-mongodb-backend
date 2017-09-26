# Introduction

This is a i18next backend to be used node.js. It will load resources from a [mongoDB](https://www.mongodb.org) database.

# Getting started

Source can be loaded via [npm](https://www.npmjs.com/package/i18next-node-mongodb-backend).

```
$ npm install i18next-node-mongodb-backend
```

Wiring up:

```js
var i18next = require('i18next');
var Backend = require('i18next-node-mongodb-backend');

i18next
  .use(Backend)
  .init(i18nextOptions);
```

As with all modules you can either pass the constructor function (class) to the i18next.use or a concrete instance.

## Backend Options

```js
{
  host: 'localhost',
  port: 27017,
  db: 'i18next-mongodb-test',

  // or
  uri: 'mongodb://localhost:27017/i18next-mongodb-test',

  // collection containing i18next data
  collection: 'i18next',

  // optional mongoDB connection options
  options: {}
}
```

Options can be passed in:

**preferred** - by setting options.backend in i18next.init:

```js
var i18next = require('i18next');
var Backend = require('i18next-node-mongodb-backend');

i18next
  .use(Backend)
  .init({
    backend: options
  });
```

on construction:

```js
var Backend = require('i18next-node-mongodb-backend');
var backend = new Backend(null, options);
```

by calling init:

```js
var Backend = require('i18next-node-mongodb-backend');
var backend = new Backend();
backend.init(options);
```
