# geojson-leaflet
Minimal example to serve static geoJSON on a Leaflet map

We assume you have your project files in [QGis](https://qgis.org) and want to put them on a webpage. This should get you started, without the need for any plugin. 
The project is not aiming at production-ready geodata deployments, but to showcase a project before the heavy development starts off.

You can export the the desired layers in QGis into geojson format. The file will look similar to:

```json
{
  "type": "FeatureCollection",
  "name": "data"
  ...
}
```

Simply add
```json
var data = {
  "type": "FeatureCollection",
  "name": "data"
  ...
}
```

This makes the geojson available in javascript, without asynchrounous requests. The advantage is that the file can be opened by the browser,
without the need for a webserver.
In production, it is highly recommended to install apache or nginx to serve the files, or even better run a Flask server to request only 
the needed data. To be fully scalable, you can replace the whole data management as implemented here by [GeoServer](http://geoserver.org/) or [Mapserver](https://mapserver.org/).

We tried to put as many comments into the files as possible, to get you as easily started as possible.
