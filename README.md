# svg-text-to-vector

> ### A powerful tool for runtime text to vector conversion of complex SVG files.

**- Inkscape like Conversion:** An efficient solution to more traditional alternatives like Inkscape.

**- Supported Tags:** Supports both **<text** and **<tspan** tags.

**- Color Fills:** Supports **Solid Fill, Linear and Radial Gradients**.

**- Attributes:** Supports attributes **x, y, opacity, stroke, stroke-width, stroke-dasharray, stroke-linecap, stroke-miterlimit**.

**- Easy to Use:** Provides a simple API to convert text to vector format with just a few lines of code.

**- High performance:** The package ensures fast and efficient performance.

**- Compatibility:** Fully compatible with all the popular Node.js frameworks.


## Installation

```bash
npm install --save svg-text-to-vector
```

## Usage

### Load & Save as Files

```javascript

var svgTextPath = require('svg-text-to-vector');

var options={
load:'file.svg',
save:'file-convert.svg'
}	

const convert = await svgTextPath.getPath(options);

```
### As Buffer

```javascript

var svg = fs.readFileSync('file.svg');
svg=Buffer.from(svg);

var options={
load:svg, 
save:'buffer' 
}	

const convert = await svgTextPath.getPath(options);

```
### As Base64

```javascript

var svg = fs.readFileSync('file.svg','base64');

var options={
load:svg, 
save:'base64' 
}	

const convert = await svgTextPath.getPath(options);

```
### As SVG String (utf-8)

```javascript

var svg = fs.readFileSync('file.svg',{encoding:'utf8'});

var options={
load:svg,
save:'utf8' | 'utf-8'
}	

const convert = await svgTextPath.getPath(options);
```
## Add Fonts

- All font names / paths load from **svg-text-to-vector/config/fonts.json** file

### Runtime

- Dynamically add fonts with json key / values {"name", "path"}. Each font needs to be added one time only for all future use.

```javascript
var font={"name":"Lexend Tera","path": "/lexend_tera.ttf"};

const addFonts = await svgTextPath.push(font);

```

### Manual

- Open **svg-text-to-vector/config/fonts.json**

```javascript
{
   "font":[
      {
         "name":"Times New Roman",
         "path":"./public/fonts/times.ttf"
      }
   ]
}

```

- Simply add more fonts to json 

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

## svgTextPath(options)


Params | &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;&nbsp;  Data Type &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;  | Description
--- | --- | ---
**options.load** | {String - Buffer - Base64 - UTF-8} | Contains SVG object that needs to be converted. Loads from a **Local Directory** or from type **Buffer** - **Base64** - **SVG String**
**options.save** | {String} | Returns the convert to path SVG object. Saves to a **Local Directory** or returns type **Buffer** - **Base64** - **SVG String**
**options.font** | {String} | **Optional** - Param for default font. Applicable if unable to find the relevant font. Default is **Times New Roman**
**options.fontPath** | {String} | **Optional** - Param for default font path. Applicable if unable to find relevant fonts and **options.font** param is defined. Default is **svg-text-to-vector/config/fonts/times.ttf**
**options.fontSize** | {Number} | **Optional** - Param for default font size. Applicable if no font size is defined within SVG text tag. Default is **16**

## Convert to Path SVG Sample

<img src="https://raw.githubusercontent.com/javedblch/svg-text-to-vector/main/public/convert/convert-to-path.svg">


# License

MIT
