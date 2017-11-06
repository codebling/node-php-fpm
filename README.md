# node-php-fpm

[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][downloads-url]


## Install

This is a [Node.js](https://nodejs.org/en/) module available through the
[npm registry](https://www.npmjs.com/). Installation is done using the
[`npm install` command](https://docs.npmjs.com/getting-started/installing-npm-packages-locally):

```sh
$ npm install php-fpm
```

## Example

```js
const path = require('path')
const http = require('http')
const phpFpm = require('php-fpm')
const serveStatic = require('serve-static')

const php = phpFpm() // Optional: parameters can be given for fastcgi-client
const serve = serveStatic(__dirname)

const httpServer = http.createServer(function (req, res) {
  if (req.url.match(/\.php(\?.*)?$/) {
    php(req, res)
  } else {
    serve(req, res)
  }
})

httpServer.listen(8080)
```

## API

Parameters for `fastcgi-client` are available [here](https://github.com/LastLeaf/node-fastcgi-client#api). The default parameters set by `php-fpm` are:

```js
{
  host: '127.0.0.1',
  port: 9000,
  documentRoot: __dirname,
  skipCheckServer: true
}
```

## License

[MIT](LICENSE)

[npm-image]: https://img.shields.io/npm/v/php-fpm.svg
[npm-url]: https://npmjs.org/package/php-fpm
[downloads-image]: https://img.shields.io/npm/dm/php-fpm.svg
[downloads-url]: https://npmjs.org/package/php-fpm
