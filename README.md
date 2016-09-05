# osm-p2p-geojson

> Export GeoJSON from osm-p2p-db

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API](#api)
- [Contribute](#contribute)
- [License](#license)

## Install

```
npm install osm-p2p-geojson
```

## Usage

```js
var getGeoJSON = require('osm-p2p-geojson')
var stream = getGeoJSON(osm)
stream.pipe(process.stdout)
// pipes GeoJSON to stdout...
getGeoJSON(osm, function (err, geojson) {
  console.log(geojson)
  // outputs geojson object
})
```

## API

```js
var getGeoJSON = require('osm-p2p-geojson')
```

### var rstream = getGeoJSON(osm[, options][, callback])

Get GeoJSON from the database. GeoJSON is returned as a readable stream, or, if passed, `callback(err, geoJson)`.

- `osm` - a [`osm-p2p-db`](https://github.com/digidem/osm-p2p-db)
- `options.bbox` - bounding box to export, defaults to `[-Infinity, -Infinity, Infinity, Infinity]`
- `options.metadata` - Array of metadata properties to include as GeoJSON properties. Defaults to `['id', 'version', 'timestamp']`
- `options.objectMode` - when `true` will return a stream of GeoJSON feature objects instead of stringified JSON. Default `false`. You can also use `getGeoJSON.obj()`

## Contribute

PRs accepted.

Small note: If editing the Readme, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.

## License

MIT © Gregor MacLennan
