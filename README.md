Clientlinker-flow-logger
========================

[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Coveralls][coveralls-image]][coveralls-url]
[![NPM License][license-image]][npm-url]
[![Install Size][install-size-image]][install-size-url]


# Install

Install `clientlinker` pkg

```shell
npm i clientlinker --save
```

Install flow pkg

```shell
npm i clientlinker-flow-logger --save
```


# Useage

```javascript
var clientlinker = require('clientlinker');
var linker = clientlinker({
  flows: ['logger', 'confighandler'],
  clients: {
    client: {
      logger: function(runtime, err, data){},
      confighandler: {
        clientHanlder: function(query, body, callback, options) {
          return Promise.resolve({result: {}});
        },
      }
    }
  }
});

linker.flow('confighandler', require('clientlinker-flow-confighandler'));
linker.flow('logger', require('clientlinker-flow-logger'));

// use
linker.run('client.clientHanlder', null, {id: 13})
  .then(function(){});
```


[npm-image]: http://img.shields.io/npm/v/clientlinker-flow-logger.svg
[downloads-image]: http://img.shields.io/npm/dm/clientlinker-flow-logger.svg
[npm-url]: https://www.npmjs.org/package/clientlinker-flow-logger
[travis-image]: http://img.shields.io/travis/Bacra/node-clientlinker-flow-logger/master.svg?label=linux
[travis-url]: https://travis-ci.org/Bacra/node-clientlinker-flow-logger
[coveralls-image]: https://img.shields.io/coveralls/Bacra/node-clientlinker-flow-logger.svg
[coveralls-url]: https://coveralls.io/github/Bacra/node-clientlinker-flow-logger
[license-image]: http://img.shields.io/npm/l/clientlinker-flow-logger.svg
[install-size-url]: https://packagephobia.now.sh/result?p=clientlinker-flow-logger
[install-size-image]: https://packagephobia.now.sh/badge?p=clientlinker-flow-logger
