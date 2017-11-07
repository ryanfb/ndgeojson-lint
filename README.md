# ndgeojson-lint

A lint tool for [newline-delimited](http://ndjson.org/) [GeoJSON](https://tools.ietf.org/html/rfc7946) streams. Based on [`geojsonhint`](https://github.com/mapbox/geojsonhint).

## Install

    npm install --global ndgeojson-lint

## Usage

    ndgeojson-lint filename.ndgeojson

You can also pipe newline-delimited GeoJSON to `ndgeojson-lint` on STDIN, e.g.:

    find . -name '*.geojson' -exec cat {} \; | jq -c . | ndgeojson-lint

## Alternatives

* You could use [`geojson-merge`](https://github.com/mapbox/geojson-merge) to create a single GeoJSON file/`FeatureCollection`, but this is tricky to do if you have more GeoJSON files than what your shell's argument length limits will allow..
* You could invoke `geojsonhint` on each individual GeoJSON file, but this is relatively slow for a large number of files.
