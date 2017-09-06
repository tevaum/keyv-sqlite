# keyv-sqlite-shrink [<img width="100" align="right" src="https://rawgit.com/lukechilds/keyv/master/media/logo.svg" alt="keyv">](https://github.com/lukechilds/keyv)

Fork of the SQLite storage adapter for [Keyv](https://github.com/lukechilds/keyv) that supports removing expired data.

[![Build Status](https://travis-ci.org/MySidesTheyAreGone/keyv-sqlite-shrink.svg?branch=master)](https://travis-ci.org/MySidesTheyAreGone/keyv-sqlite-shrink)
[![Coverage Status](https://coveralls.io/repos/github/MySidesTheyAreGone/keyv-sqlite-shrink/badge.svg?branch=master)](https://coveralls.io/github/MySidesTheyAreGone/keyv-sqlite-shrink?branch=master)
[![npm](https://img.shields.io/npm/v/keyv-sqlite-shrink.svg)](https://www.npmjs.com/package/keyv-sqlite-shrink)

## Install

```shell
npm install --save keyv keyv-sqlite-shrink
```

## Usage

```js
const Keyv = require('keyv');
const KeyvSqliteAdapter = require('keyv-sqlite-shrink');

const storage = new KeyvSqliteAdapter({
  uri: 'sqlite://path/to/database.sqlite',
  table: 'myappcache',
  busyTimeout: 10000
});

const keyv = new Keyv({
  store: storage,
  namespace: 'myapp'
});

keyv.on('error', handleConnectionError);
```

About the `busyTimeout` option: [read](https://sqlite.org/c3ref/busy_timeout.html).


## License

MIT © MySidesTheyAreGone

MIT © Luke Childs
