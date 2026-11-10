# Context place packs

Offline place packs for the Context iPhone app: named restaurants, cafes, bars, pubs, fast food, music venues,
theatres, cinemas, nightclubs, arts centres, museums, hotels, stadiums, airports, clinics, doctors and dentists of a
country, taken from OpenStreetMap.

Each release holds one gzip file per country (`poi-<code>.json.gz`) and `catalog.json` with the size and the SHA-256
of every file. The app downloads a pack only after the user confirms it, and installs it only if the size and the
checksum match the catalog.

## Data and licence

The packs are a database derived from OpenStreetMap data: © OpenStreetMap contributors. They are available under the
[Open Database License 1.0](https://opendatacommons.org/licenses/odbl/1-0/) — see
[openstreetmap.org/copyright](https://www.openstreetmap.org/copyright) and [LICENSE.md](LICENSE.md).

Source: the daily country extracts of OpenStreetMap France (`download.openstreetmap.fr/extracts`); the date of the
extract is in every pack (`extractedAt`) and in the catalog.

## Format

A pack is a JSON object:

```json
{"format": "context-poi-pack", "version": 1, "region": "nl", "country": "NL", "title": "Нидерланды",
 "attribution": "© участники OpenStreetMap, ODbL", "license": "ODbL-1.0", "source": "…", "extractedAt": "2026-11-09",
 "bbox": [minLat, minLon, maxLat, maxLon], "count": 49837, "categories": {"restaurant": 18521, …},
 "pois": [["osm:n123", "Name", "restaurant", 52.37, 4.88, ["Alternative name"]], …]}
```

Only named objects are kept. A point is the node itself or the centroid of the outer ring of an area. Alternative
names are `name:ru`, `name:en`, `old_name` and `brand`. Ids are OpenStreetMap ids: `osm:n…` (node), `osm:w…` (way),
`osm:r…` (relation).
