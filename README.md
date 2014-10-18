# bmfont-lato

[![experimental](http://badges.github.io/stability-badges/dist/experimental.svg)](http://github.com/badges/stability-badges)

Lato packed as a [BMFont JSON object](https://github.com/mattdesl/bmfont2json), so it can be required for testing. 

This also exports an `images` field, which is an array of [ndpack-images](https://www.npmjs.org/package/ndpack-image) parallel to the `pages` array. 

```js
var Lato = require('bmfont-lato')

//do something with the ndarrray image
var shape = Lato.images[0].shape.slice(0, 3))

//e.g. image shape is 750x512x4
console.log(shape)

//BMFont fields..
console.log(Lato.info)
console.log(Lato.chars)
console.log(Lato.kernings)
```

The `paths` and `images` array will have a length of 1. 

The image contains 4 fonts packed with [gdx-fontpack](https://github.com/mattdesl/gdx-fontpack), each of which can be required separately:

- `require('bmfont-lato/regular-32')`
- `require('bmfont-lato/regular-64')`
- `require('bmfont-lato/bold-32')`
- `require('bmfont-lato/bold-64')`

The default exported font is `regular-32` (the size is in px).

## Usage

[![NPM](https://nodei.co/npm/bmfont-lato.png)](https://nodei.co/npm/bmfont-lato/)

## Build

See `package.json` scripts on how to build. You need these tools:

`npm install ndpack-image bmfont2json module-exports -g`

Then:

```sh
#first you need to build an atlas with BMFont or gdx-fontpack..
# ...

#then pack it with ndpack-image
npm run pack

#then export all fonts as CommonJS
npm run fonts
```

## License

MIT, see [LICENSE.md](http://github.com/mattdesl/bmfont-lato/blob/master/LICENSE.md) for details.