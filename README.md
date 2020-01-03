# jimp-watermark
A powerful watermark library based on Jimp for node.js. This can be used to overlay a "image" watermark in another image.

### Installation

	'npm install jimp-watermark'

### Server-side usage

```javascript
var watermark = require('jimp-watermark');

watermark.addWatermark('/path/to/image/file','/path/to/image/watermark', options);

watermark.addTextWatermark('/path/to/image/file', options);
```

### API

#### addWatermark(imageSource, watermarkSource, options)

API to overlay watermark in given image. It takes three arguments : 
1. path of the image
2. path of the watermark
2. options object. This argument is optional


**Options**

Various options supported by this API are :
- **ratio** - To specify watermark text. Default is 'Sample watermark'.
- **opacity** - To specify color of watermark text. Default is 'Grey'.
- **dstPath** - To specify the output path. Default is 'watermark.{sourceFile ext}'.

**Example**

```javascript
var watermark = require('jimp-watermark');

watermark.addWatermark('./img/main.jpg', './img/logo.png').then(data => {
    console.log(data);
}).catch(err => {
    console.log(err);
});
```

**Different Options**

```javascript

//
// Options to specify output path
//
var watermark = require('jimp-watermark');
var options = {
	'ratio': 0.6,// Should be less than one
    'opacity': 0.6, //Should be less than one
    'dstPath' : './watermark.jpg'
};
watermark.addWatermark('./img/main.jpg', './img/logo.png', options);

```

#### addTextWatermark(imageSource, options)

API to overlay watermark in given image. It takes two arguments : 
1. path of the image
2. options object. This argument is optional


**Options**

Various options supported by this API are :
- **text** - To specify the text to be overlaid on the main image.
- **textSize** - To specify size of text over the main image, value ranged from 1 to 8.
- **dstPath** - To specify the output path. Default is 'watermark.{sourceFile ext}'.

**Example**

```javascript
var watermark = require('jimp-watermark');

watermark.addTextWatermark('./img/main.jpg').then(data => {
    console.log(data);
}).catch(err => {
    console.log(err);
});
```

**Different Options**

```javascript

//
// Options to specify output path
//
var watermark = require('jimp-watermark');
var options = {
	'text': 'watermark-test',
    'textSize': 6, //Should be between 1-8
    'dstPath' : './watermark.jpg'
};
watermark.addTextWatermark('./img/main.jpg', options);
```

### Inspiration
[https://github.com/luthraG/image-watermark](https://github.com/luthraG/image-watermark)

[Image Processing in NodeJS with Jimp - Medium](https://medium.com/@rossbulat/image-processing-in-nodejs-with-jimp-174f39336153)

### License(MIT)

Copyright (c) 2019 Sushant Paudel

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.    
