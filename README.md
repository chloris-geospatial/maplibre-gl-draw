# @chloris-geospatial/maplibre-gl-draw

Adds support for drawing and editing features on [mapbox-gl.js](https://www.mapbox.com/mapbox-gl-js/) or [maplibre-gl-js](https://maplibre.org/maplibre-gl-js-docs/api/) maps. Forked from [@mapbox/mapbox-gl-draw](https://github.com/mapbox/mapbox-gl-draw) to maintain support with the (still in development) version 3 of maplibre-js. No official affiliation with maplibre or mapbox.

This repository will loosely track the official mapbox repository SEMVER minor releases. We do not currently plan to implement new functionality beyond what is needed to maintain compatibility with maplibre-gl-js.

### Installing

```
// install from github, npm package coming soon.
npm install git@github.com:chloris-geospatial/maplibre-gl-draw.git
```


Draw ships with CSS, make sure you include it in your build.

### Usage in your application

#### JavaScript

**When using modules**

```js
import mapboxgl from 'mapbox-gl';
import MapboxDraw from "@chloris-geospatial/maplibre-gl-draw";
// or
import maplibregl from 'maplibre-gl';
import maplibreGlDraw from "@chloris-geospatial/maplibre-gl-draw";
MapboxDraw.enableMapLibre();
```

#### CSS

**When using modules**
 ```js
import '@chloris-geospatial/maplibre-gl-draw/dist/mapbox-gl-draw.css'
// or
import '@chloris-geospatial/maplibre-gl-draw/dist/maplibre-gl-draw.css'
 ```


### Example usage

```js
var map = new maplibregl.Map({
  container: 'map',
  style: 'https://demotiles.maplibre.org/style.json',
  center: [-74.5, 40], // starting position [lng, lat]
  zoom: 9
});
MapboxDraw.enableMapLibre(); // not needed if you are using mapbox-gl-js

var Draw = new MapboxDraw();

// Map#addControl takes an optional second argument to set the position of the control.
// If no position is specified the control defaults to `top-right`. See the docs
// for more details: https://docs.mapbox.com/mapbox-gl-js/api/#map#addcontrol

map.addControl(Draw, 'top-left');

map.on('load', function() {
  // ALL YOUR APPLICATION CODE
});
```

### See also [API.md](https://github.com/mapbox/mapbox-gl-draw/blob/main/docs/API.md).


### Developing and testing

Install dependencies, build the source files and crank up a server via:

```
git clone git@github.com:chloris-geospatial/maplibre-gl-draw.git
yarn install
yarn start & open "http://localhost:9967/debug/?access_token=<token>"
```

### Testing

```
npm run test
```


Update the version number in [the GL JS example](https://github.com/mapbox/mapbox-gl-js/blob/publisher-production/docs/pages/example/mapbox-gl-draw.html).
