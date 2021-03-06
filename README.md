# bitmex

[![NPM Package](https://img.shields.io/npm/v/bitmex.svg?style=flat-square)](https://www.npmjs.org/package/bitmex)
[![Dev Dependencies](https://img.shields.io/david/thofmann/bitmex.svg?style=flat-square)](https://www.npmjs.org/package/bitmex)

An unofficial node.js wrapper for the BitMEX Bitcoin derivatives exchange

Official BitMEX website: [https://www.bitmex.com](https://www.bitmex.com)

## Getting Started

Installation:

```
npm install bitmex --save
```

Usage:

```javascript
var BitMEX = require('bitmex');

BitMEX(function(bitmex) {

    bitmex.swagger.chat.get({count: 1, reverse: true}, function(response) {
        var message = JSON.parse(response.data)[0];
        console.log('Here is the most recent chat message from the Swagger API:');
        console.log(message.user + ': ' + message.message);
    });

    console.log('Asking for help on the websocket.');
    bitmex.websocket.send('"help"');

    bitmex.websocket.on('message', function(message) {
        console.log('Websocket message received:');
        console.log(message);
    });

});
```
