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

URLs are parsed using `url.parse`. You may also pass an options hash as the first argument to `get` or `request`.

Specify the `socksHost` and `socksPort` options if your SOCKS server isn't running on `localhost:1080`. Tor runs its SOCKS server on port `9050` by default, for example.

## Using with Tor ##

Works great for making HTTP requests through [Tor](https://www.torproject.org/) (see bundled example).

## Using with Request ##

To use with [Request](https://github.com/mikeal/request), just pass an agent instance.

```js
var Socks5ClientHttpAgent = require('socks5-http-client/lib/Agent');

request({
	url: 'http://www.google.com/',
	agent: new Socks5ClientHttpAgent({
		socksHost: 'my-tor-proxy-host', // Defaults to 'localhost'.
		socksPort: 9050 // Defaults to 1080.
	})
}, function(err, res) {
	console.log(res);
});
```

## HTTPS ##

This client only provides support for making HTTP requests. See [socks5-https-client](https://github.com/mattcg/socks5-https-client) for an HTTPS implementation.

## License ##

Copyright © 2013 [Matthew Caruana Galizia](http://twitter.com/mcaruanagalizia), licensed under an [MIT license](http://mattcg.mit-license.org/).
