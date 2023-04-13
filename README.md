# @chloris-geospatial/maplibre-gl-draw

Adds support for drawing and editing features on [mapbox-gl.js](https://www.mapbox.com/mapbox-gl-js/) or [maplibre-gl-js](https://maplibre.org/maplibre-gl-js-docs/api/) maps. Forked from [@mapbox/mapbox-gl-draw](https://github.com/mapbox/mapbox-gl-draw) to maintain support with the (still in development) version 3 of maplibre-js. No official affiliation with maplibre or mapbox.

This repository will loosely track the official mapbox repository SEMVER minor releases. We do not currently plan to implement new functionality beyond what is needed to maintain compatibility with maplibre-gl-js.

### Installing

```
npm install @chloris-geospatial/maplibre-gl-draw
```

Draw ships with CSS, make sure you include it in your build.

### Usage in your application

#### JavaScript

**When using modules**

```js
import mapboxgl from 'mapbox-gl';
import MapboxDraw from "@mapbox/mapbox-gl-draw";
```

#### CSS

**When using modules**
 ```js
import '@mapbox/mapbox-gl-draw/dist/mapbox-gl-draw.css'
 ```


### Example usage

```js
mapboxgl.accessToken = 'YOUR_ACCESS_TOKEN';

var map = new mapboxgl.Map({
  container: 'map',
  style: 'mapbox://styles/mapbox/streets-v12',
  center: [40, -74.50],
  zoom: 9
});

var Draw = new MapboxDraw();

// Map#addControl takes an optional second argument to set the position of the control.
// If no position is specified the control defaults to `top-right`. See the docs
// for more details: https://docs.mapbox.com/mapbox-gl-js/api/#map#addcontrol

map.addControl(Draw, 'top-left');

map.on('load', function() {
  // ALL YOUR APPLICATION CODE
});
```

https://www.mapbox.com/mapbox-gl-js/example/mapbox-gl-draw/

### See [API.md](https://github.com/mapbox/mapbox-gl-draw/blob/main/docs/API.md) for complete reference.


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
