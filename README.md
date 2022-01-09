# svg-text-to-path

> Converts to path all the Textfield tags within an SVG file.

## Installation

```bash
npm install --save svg-text-to-path
```

## Usage

### Load & Save as Files

```javascript

var options={
load:'/path/file.svg', // path to load svg file from
save:'/path/file-convert.svg' // path to save convert to path svg file to
}	

const file = await svgTextPath.getPath(options);

```
### As Buffer

```javascript

var data = fs.readFileSync('/path/file.svg');
data=Buffer.from(buffer);

var options={
load:data, // load svg file as buffer
save:'buffer' // string value as 'buffer' returns convert to path svg as type buffer
}	

const file = await svgTextPath.getPath(options);

```
### As Base64

```javascript

var data = fs.readFileSync(loadPath,'base64');

var options={
load:data, // load svg file as base64
save:'base64' // string value as 'base64' returns convert to path svg as type base64
}	

const file = await svgTextPath.getPath(options);

```
### As SVG String (utf-8)

```javascript

var data = fs.readFileSync(loadPath,{encoding:'utf8'});

var options={
load:data, // load svg file as SVG string
save:'utf8' | 'utf-8' // string value as 'utf8' | 'utf-8' returns convert to path svg as SVG string
}	

const file = await svgTextPath.getPath(options);
```
## Add Fonts

- All font names / paths load from **svg-text-to-path/config/fonts.json** file

### Runtime

- Dynamically add fonts with json key / values {"name", "path"}. Each font needs to be added one time only for all future use.

```javascript
var font={"name":"Lexend Tera","path": "./public/fonts/lexend_tera.ttf"};

const addFonts = await svgTextPath.push(font); // adds font to svg-text-to-path/config/fonts.json file on runtime

```

### Manual

- Open **svg-text-to-path/config/fonts.json**

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
**options.fontPath** | {String} | **Optional** - Param for default font path. Applicable if unable to find relevant fonts and **options.font** param is defined. Default is **./public/fonts/times.ttf**
**options.fontSize** | {Number} | **Optional** - Param for default font size. Applicable if no font size is defined within SVG text tag. Default is **16**

## Convert to Path SVG Sample

- https://raw.githubusercontent.com/javedblch/svg-text-to-path/main/public/convert/convert-to-path.svg

# License

MIT
