# pg-query-native [![Build Status](https://travis-ci.org/zhm/node-pg-query-native.svg?branch=master)](https://travis-ci.org/zhm/node-pg-query-native)

The real PostgreSQL parser for nodejs.

This is based on the output of [libpg_query](https://github.com/lfittl/libpg_query). This wraps the static library output and links it into a node module for use in js.

All credit for the hard problems goes to [Lukas Fittl](https://github.com/lfittl).

## How to re-buid 

```sh
git clone -b 10-latest git://github.com/lfittl/libpg_query
cd libpg_query
make
```

Then get the `.a` file and drop it in the folder in this repo.

## Installation

```sh
npm install pg-query-native-latest
```

### Documentation

### `query.parse(query)`

Parses the query and returns the parse tree.

### Parameters

| parameter            | type               | description                                               |
| -------------------- | ------------------ | --------------------------------------------------------- |
| `query`              | String             | SQL query                                                 |

Returns an object in the format:

```
{ query: <query|Object>,
  error: { message: <message|String>,
           fileName: <fileName|String>,
           lineNumber: <line|Number>,
           cursorPosition: <cursor|Number> }
```

## Example

```js
var parse = require('pg-query-native').parse;

console.log(parse('select 1').query);
```

## Related

* [libpg_query](https://github.com/lfittl/libpg_query)
* [pg_query](https://github.com/lfittl/pg_query)
* [pg_query.go](https://github.com/lfittl/pg_query.go)
