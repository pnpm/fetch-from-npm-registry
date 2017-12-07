# fetch-from-npm-registry

[![Greenkeeper badge](https://badges.greenkeeper.io/pnpm/fetch-from-npm-registry.svg)](https://greenkeeper.io/)

> A fetch lib specifically for using with the npm registry

<!--@shields('npm', 'travis')-->
[![npm version](https://img.shields.io/npm/v/fetch-from-npm-registry.svg)](https://www.npmjs.com/package/fetch-from-npm-registry) [![Build Status](https://img.shields.io/travis/pnpm/fetch-from-npm-registry/master.svg)](https://travis-ci.org/pnpm/fetch-from-npm-registry)
<!--/@-->

## Installation

```sh
npm i -S fetch-from-npm-registry
```

## Usage

<!--@example('./example.js')-->
```js
'use strict'
const createFetcher = require('fetch-from-npm-registry').default

const fetchFromNpmRegistry = createFetcher({userAgent: 'fetch-from-npm-registry'})

fetchFromNpmRegistry('https://registry.npmjs.org/is-positive')
  .then(res => res.json())
  .then(metadata => console.log(JSON.stringify(metadata.versions['1.0.0'], null, 2)))
  //> {
  //    "name": "is-positive",
  //    "version": "1.0.0",
  //    "devDependencies": {
  //      "ava": "^0.0.4"
  //    },
  //    "_hasShrinkwrap": false,
  //    "directories": {},
  //    "dist": {
  //      "shasum": "88009856b64a2f1eb7d8bb0179418424ae0452cb",
  //      "tarball": "https://registry.npmjs.org/is-positive/-/is-positive-1.0.0.tgz"
  //    },
  //    "engines": {
  //      "node": ">=0.10.0"
  //    }
  //  }
```
<!--/@-->

## License

[MIT](./LICENSE) © [Zoltan Kochan](https://www.kochan.io/)
