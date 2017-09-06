# keyv-sqlite-shrink [<img width="100" align="right" src="https://rawgit.com/lukechilds/keyv/master/media/logo.svg" alt="keyv">](https://github.com/lukechilds/keyv)

Fork of the SQLite storage adapter for [Keyv](https://github.com/lukechilds/keyv) that supports removing expired data.

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
