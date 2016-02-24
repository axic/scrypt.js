# scrypt.js

This purpose of this library is to provide a single interface to both a C and a pure Javascript based scrypt implementation.
Supports browserify and will select the best option when running under Node or in the browser.

It is using the following two underlying implementations:
- [scryptsy](https://github.com/cryptocoinjs/scryptsy) for the pure Javascript implementation
- [scrypt](https://www.npmjs.com/package/scrypt) for the C version

It only supports hashing. Doesn't offer an async option and doesn't implement the HMAC format. If you are looking for those,
please use the Node `scrypt` library.

## Example usage

```js
// Load default implementation
var scrypt = require('scrypt.js')

// Load specific version
var scrypt = require('scrypt.js/js') // pure Javascript
var scrypt = require('scrypt.js/node') // C on Node

scrypt(key, salt, n, r, p, dklen, progressCb) // returns Buffer
```

Note, the `progressCb` is not available on Node.

## Other scrypt implementations

- https://www.npmjs.com/package/scrypt: Uses the C implementation (version 1.2.0), both async and async.
- https://www.npmjs.com/package/scrypt-hash: Uses the C implementation and offers only an async option.
- https://www.npmjs.com/package/scryptsy: A pure Javacript implementation. Offers a progress callback.
- https://www.npmjs.com/package/scrypt256-hash: Another C implementation. Doesn't seem to be maintained.
- https://www.npmjs.com/package/scrypt-jane-hash: Uses an alternative C implementation (called scrypt-jane). Doesn't seem to be maintained.
- https://www.npmjs.com/package/js-scrypt-em: Emscripten-compiled scrypt 1.1.6. Doesn't seem to be maintained.
- https://www.npmjs.com/package/js-scrypt: Wraps `js-scrypt-em` and offers sync and async options. Doesn't seem to be maintained.
