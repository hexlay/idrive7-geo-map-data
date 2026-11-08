# idrive7-geo-map-data

Map packs for [hexlay/idrive7-geo-map](https://github.com/hexlay/idrive7-geo-map) (`osm_nav`, offline navigation for BMW iDrive 7), kept out of that repo's git so it stays small enough for the MGU Store (the store downloads the whole app repo, at most 64 MB, and builds on the head unit in at most 200 MB).

> [!CAUTION]
> The app these maps are for is **EXTREMELY EXPERIMENTAL** and has not been run in a car. See its README.

## Releases

Each release holds one map pack, gzipped, as `kit/tools/pack_osm.py` writes it. The app's `apps/osm_nav/app.json` (`maps`) names the file it builds with, by URL, size and SHA-256; the build checks both before the map goes into the package.

| Release | File | Region | Made from | Gzipped | Unpacked |
| :--- | :--- | :--- | :--- | ---: | ---: |
| `georgia-2026-11-07` | `georgia-2026-11-07.pack.gz` | Georgia | Geofabrik `georgia-latest.osm.pbf`, 2026-11-07 | 60,652,345 B | 121,838,184 B |

SHA-256 of `georgia-2026-11-07.pack.gz`: `43df3d70b08b0644f1909db2eec90b28d9010af61c3e412e7c0cc3e1463f1d83`
SHA-256 unpacked: `b799e304ad01f36e3a5d15100bf60ac1cedaf400c9a2b09d197da68e3fe919e6`

## A new map

```bash
python3 kit/tools/pack_osm.py --fetch georgia -o georgia.pack
```
in the app repo, then a new release here with the gzipped pack, and its URL, sizes and SHA-256 sums in `apps/osm_nav/app.json`.

## License

The map data is © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors and available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/). These packs are a derived database of it (extracts by [Geofabrik](https://download.geofabrik.de/)) and are offered under the same licence: you may share and adapt them, with attribution to OpenStreetMap contributors, and a derived database you share must be under the ODbL too.
