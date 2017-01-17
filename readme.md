# VBB JavaScript modules

This is a list of JavaScript modules for [Berlin & Brandenburg public transport (VBB)](https://www.vbb.de/), grouped by their data source.

*TLDR*: Use [vbb-rest](https://github.com/derhuerst/vbb-rest/blob/master/docs/index.md) if you don't know where to start or want a very light client.

## Static Data

VBB **[publishes static public transport data](http://daten.berlin.de/datensaetze/vbb-fahrplandaten-dezember-2016-bis-dezember-2017) (stops of all trains of all lines at all stations) as [GTFS](https://developers.google.com/transit/gtfs/).** These GTFS data sets look & feel like a database dump, so a lot of processing needs to be done to actually consume this data.

Modules containing processed static data:

- [`vbb-stations`](https://github.com/derhuerst/vbb-stations) – A list of VBB stations.
- [`vbb-lines`](https://github.com/derhuerst/vbb-lines) – VBB lines and their stations.
- [`vbb-lines-at`](https://github.com/derhuerst/vbb-lines-at) – Which lines run at a VBB station?
- [`vbb-trips`](https://github.com/derhuerst/vbb-trips) – When do trains run where in VBB?
- [`vbb-shapes`](https://github.com/derhuerst/vbb-shapes) – Shapes of VBB lines.
- [`vbb-runs-every`](https://github.com/derhuerst/vbb-runs-every) – Compute frequencies of departures and routes. *unmaintained*
- [`vbb-translate-ids`](https://github.com/derhuerst/vbb-translate-ids) – Translate VBB ids old -> new & new -> old.
- [`vbb-static`](https://github.com/derhuerst/vbb-static) – *outdated, use the modules above*

Modules to find stations:

- [`vbb-stations-autocomplete`](https://github.com/derhuerst/vbb-stations-autocomplete) – Autocomplete VBB stations.
- [`vbb-find-stations`](https://github.com/derhuerst/vbb-find-stations) – Search for stations of VBB.
- [`vbb-find-station`](https://github.com/derhuerst/vbb-find-station) – Search for a VBB station.
- [`vbb-stations-cli`](https://github.com/derhuerst/vbb-stations-cli) – Find and filter VBB stations from the command line.

Modules with additional data:

- [`vbb-common-places`](https://github.com/derhuerst/vbb-common-places) – Aliases for common stations.
- [`vbb-osm-relations`](https://github.com/derhuerst/vbb-osm-relations) – VBB lines and their OpenStreetMap relations.
- [`vbb-station-photos`](https://github.com/derhuerst/vbb-station-photos) – Photos of every subway station in Berlin.
- [`vbb-logos`](https://github.com/derhuerst/vbb-logos) – Nice SVG logos for Berlin & Brandenburg public transport.
- [`vbb-entrances`](https://github.com/derhuerst/vbb-entrances) – Entrances for VBB stations. *outdated*
- [`vbb-delays-list`](https://github.com/derhuerst/vbb-delays-list) – Statistics on delays at VBB stations. *unfinished*

## APIs

VBB also **[provides an API](https://www.vbb.de/de/article/fahrplan/webservices/schnittstellen-fuer-webentwickler/5070.html)** under a proprietary license. This *public* API provides all the information they have, but [is unstable and rate-limited, doesn't have CORS and isn't REST](https://github.com/derhuerst/vbb-rest/blob/master/docs/why.md#why-use-this-api).

The VBB app talks to another ***private* API that is stable and has neither rate limits nor authentication**. Please note that the usage of this API is not officially endorsed and does not have any licensing. Use it and the modules below at your own risk.

These modules can be used to query data from the API and other places.

- [`vbb-client`](https://github.com/derhuerst/vbb-client) – An API client for Berlin & Brandenburg public transport.
- [`vbb-rest`](https://github.com/derhuerst/vbb-rest) – An HTTP REST server for Berlin & Brandenburg public transport.
- [`vbb-hafas`](https://github.com/derhuerst/vbb-hafas) – A JavaScript client for Berlin & Brandenburg public transport HAFAS API.
- [`vbb-disruptions`](https://github.com/derhuerst/vbb-disruptions) – Disruptions in VBB public transport.
- [`vbb-monitor`](https://github.com/derhuerst/vbb-monitor) – Fetch all departures of all lines at all stations of VBB.
- [`vbb-positions-stream`](https://github.com/derhuerst/vbb-positions-stream) – A realtime stream for positions of buses and trains.

## Tools, UIs & Experiments

- [`vbb-cli`](https://github.com/derhuerst/vbb-cli) – A CLI for Berlin & Brandenburg public transport.
- [`vbb-telegram`](https://github.com/derhuerst/vbb-telegram) – A Telegram bot for Berlin & Brandenburg public transport.
- [`vbb-map-routing`](https://github.com/derhuerst/vbb-map-routing) – Use VBB interactively, using a map. *unfinished*
- [`vbb-delays-map`](https://github.com/derhuerst/vbb-delays-map) – A map showing delays of public transport in Berlin. *outdated*
- [`vbb-delays`](https://github.com/derhuerst/vbb-delays) – Generate statistics on delayed VBB departures. *unfinished*
- [`bvg-topological-map`](https://github.com/derhuerst/bvg-topological-map) – BVG transport map as a nice SVG.
- [`vbb-web`](https://github.com/derhuerst/vbb-web) – A web client for Berlin & Brandenburg public transport.
- [`vbb-anybar`](https://github.com/derhuerst/vbb-anybar) – Let the status bar show you when to catch the train. *unfinished*
- [`vbb-map`](https://github.com/derhuerst/vbb-map) – Render VBB lines on a map. *unmaintained*

Modules I'm not willing to maintain right now:

- [`vbb-osm-map`](https://github.com/derhuerst/vbb-osm-map) – Render VBB lines on a map, using OpenStreetMap. *unmaintained*
- [`vbb-toy-map-feed`](https://github.com/derhuerst/vbb-toy-map-feed) – A live feed for the BVG delays map. *unmaintained*
- [`vbb-station-graph`](https://github.com/derhuerst/vbb-station-graph) – Visualize VBB public transport next to any station. *unmaintained*

## Utilities

These modules perform a specific distinct task. They are used by the modules above.

- [`vbb-parse-line`](https://github.com/derhuerst/vbb-parse-line) – Parse VBB lines like M4, TXL, S42.
- [`vbb-parse-ticket`](https://github.com/derhuerst/vbb-parse-ticket) – Parse ticket information from the VBB HAFAS API.
- [`vbb-short-station-name`](https://github.com/derhuerst/vbb-short-station-name) – Remove noise from VBB station names.
- [`vbb-tokenize-station`](https://github.com/derhuerst/vbb-tokenize-station) – Remove noise from VBB station names.
- [`vbb-util`](https://github.com/derhuerst/vbb-util) – JavaScript utilites for the VBB API client.
