Ven Stream
==========

Installation
------------

```
npm install venstream
```

Usage
-----

```javascript
var file1 = fs.createReadStream('...');
var file2 = fs.createReadStream('...');
var ven = require('venstream');

var union = fs.createWriteStream('union.out');

var handles = ven(union);
file1.pipe(handles[0]).pipe(fs.createWriteStream('file1only.out');
file2.pipe(handles[1]).pipe(fs.createWriteStream('file2only.out');

union.on('finish', function () {
  console.log('Stream Processing Finished!');
});
```
