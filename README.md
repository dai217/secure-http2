# secure-spdy

With this module you can create HTTP2/SPDY servers
in node.js with natural http module interface and fallback to regular https
(for browsers that don't support neither HTTP2, nor SPDY yet).

## Description 
This module is based on 'node-spdy' module.

## Usage
Server:
```javascript
var secureSpdy = require('secure-spdy'),
    fs = require('fs');

var options = {
  key: fs.readFileSync(__dirname + '/keys/spdy-key.pem'),
  cert: fs.readFileSync(__dirname + '/keys/spdy-cert.pem'),
  ca: fs.readFileSync(__dirname + '/keys/spdy-ca.pem'),
};

var server = secureSpdy.createServer(options, function(req, res) {
  res.writeHead(200);
  res.end('hello world!');
});

server.listen(3000);
```


#### LICENSE

This software is licensed under the MIT License.

secure-spdy  
Copyright Suzuki Daisaku, 2015.

Includes node-spdy  
Copyright Fedor Indutny, 2015.  
Released under the MIT Licenses.

Includes mobile-detect.js  
Copyright Heinrich Goebl, Agenda Software GmbH & Co. KG, 2013.  
Released under the MIT Licenses.


Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the
following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN
NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE
USE OR OTHER DEALINGS IN THE SOFTWARE.
