# SOCKS5 HTTP Client #

[![Build Status](https://travis-ci.org/mattcg/socks5-http-client.png?branch=master)](https://travis-ci.org/mattcg/socks5-http-client)

SOCKS v5 HTTP client implementation in JavaScript for Node.js.

```js
var shttp = require('socks5-http-client');

shttp.get('http://www.google.com/', function(res) {
	res.setEncoding('utf8');
	res.on('readable', function() {
		console.log(res.read()); // Log response to console.
	});
});
```

## Using with Tor ##

Works great for making HTTP requests through [Tor](https://www.torproject.org/) (see bundled example).

## HTTPS ##

This client only provides support for making HTTP requests. See [socks5-https-client](https://github.com/mattcg/socks5-https-client) for an HTTPS implementation.

## License ##

Copyright © 2013 [Matthew Caruana Galizia](http://twitter.com/mcaruanagalizia), licensed under an [MIT license](http://mattcg.mit-license.org/).
