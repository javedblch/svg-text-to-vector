# SVG Text to Vector

> ### A powerful tool for runtime text to vector conversion of complex SVG files.

## Features:

**- Supported Tags:** 'text | tspan'.

**- Attributes:** Supports all major attributes including  x, y, dx, dy, opacity, stroke, transform, class-based styling etc.

**- Colors:** Supports Solid Fill, Linear and Radial Gradients.

**- Dynamic Font Handling:** Offers dynamic runtime addition of fonts to its native config/fonts.json file.  

## Installation

```bash
npm install --save svg-text-to-vector
```

## Usage

```bash
const svgTextPath = require('svg-text-to-vector');
```

### Load | Save as Files

```javascript

var svgTextPath = require('svg-text-to-vector');

var options={
load:'file.svg',
save:'file-convert.svg'
}	

const convert = await svgTextPath.getPath(options);

```

### Load | Save as Buffer

```javascript

var svg = fs.readFileSync('./public/file.svg');
svg=Buffer.from(svg);

var options={
load:svg,
save:'buffer'
}

const convert = await ConvertToPath.getPath(options);

```

### Load | Save as Base64

```javascript

var svg = fs.readFileSync('./public/file.svg','base64');

var options={
load:svg,
save:'base64'
}

const convert = await ConvertToPath.getPath(options);

```

### Load | Save as SVG String (utf-8)

```javascript

var svg = fs.readFileSync('./public/file.svg',{encoding:'utf8'});

var options={
load:svg,
save:'utf8' | 'utf-8'
}

const convert = await ConvertToPath.getPath(options);

```
## Fonts Handling

- All dynamically added & built-in font names & paths load from **svg-text-to-vector/config/fonts.json** file

### Dynamically Add Fonts

- Dynamically add fonts with json key & value pair {“name”, “path”}. Each font needs to be added one time only for all future purposes.

```javascript
var font={"name":"Lexend Tera","path": "/lexend_tera.ttf"};

const addFonts = await ConvertToPath.push(font);

```

### Add Fonts Manually

- Open **svg-text-to-vector/config/fonts.json** and simply add more fonts.

```javascript

{
   "font":[
      {
         "name":"Times New Roman",
         "path":"./public/fonts/times.ttf"
      },
      {
         "name":"Anton",
         "path":"./public/fonts/anton.ttf"
      }	  
   ]
}

```
## API

## Options


Params | &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  Data Type &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;  | Description
--- | --- | ---
**options.load** | {String - Buffer - Base64 - UTF-8} | Contains SVG object that needs to be converted. Loads from a **Local Directory** or from type **Buffer** - **Base64** - **SVG String**
**options.save** | {String} | Returns the convert to path SVG object. Saves to a **Local Directory** or returns type **Buffer** - **Base64** - **SVG String**
**options.font** | {String} | **Optional** - Param for default font. Applicable if unable to find the relevant font. Default is **Times New Roman**
**options.fontPath** | {String} | **Optional** - Param for default font path. Applicable if unable to find relevant fonts and **options.font** param is defined. Default is **svg-text-to-vector/config/fonts/times.ttf**
**options.fontSize** | {Number} | **Optional** - Param for default font size. Applicable if no font size is defined within SVG text tag. Default is **16**

# Performance & Compatibility
The package ensures fast and efficient performance and is fully compatible with all the popular Node.js frameworks.

# License

MIT
