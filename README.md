# secure-spdy

## Description 
With this module you can create HTTP2/SPDY-based secure session management servers
in node.js.
This module is based on indutny/[node-spdy](https://github.com/indutny/node-spdy).

## Requirement
Node.js

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
##Installation
Clone the git repository as
```
git clone https://github.com/dai217/secure-spdy.git
```
You can also use secure-spdy as an npm package. You can install it by:
```
npm install secure-spdy
```
## Acknowlidgement
We would like to offer my special thanks to indutny, Heinrich Goebl, Agenda Software GmbH & Co. KG.

## License

This software is licensed under the MIT License.

secure-spdy  
Copyright (C) Suzuki Daisaku, 2015.

Includes [node-spdy](https://github.com/indutny/node-spdy)  
Copyright (C) Fedor Indutny, 2015.  
Released under the MIT Licenses.

Includes [mobile-detect.js](https://github.com/hgoebl/mobile-detect.js)  
Copyright (C) Heinrich Goebl, Agenda Software GmbH & Co. KG, 2013.  
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
