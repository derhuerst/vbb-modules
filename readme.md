# VBB JavaScript modules

This is a list of JavaScript modules for [Berlin & Brandenburg public transport (VBB)](https://www.vbb.de/), grouped by their data source.

[![support me on Patreon](https://img.shields.io/badge/support%20me-on%20patreon-fa7664.svg)](https://patreon.com/derhuerst)

*TLDR*: Use [vbb-rest](https://github.com/derhuerst/vbb-rest/blob/master/docs/index.md) if you don't know where to start or want a very light client.

## Friendly Public Transport Format

There's an ongoing effort to convert all of the modules below to the [Friendly Public Transport Format](https://github.com/public-transport/friendly-public-transport-format), which intends to make them interoperable and easier to use.

## Static Data

VBB **[publishes static public transport data](http://daten.berlin.de/datensaetze/vbb-fahrplandaten-dezember-2016-bis-dezember-2017) (stops of all trains of all lines at all stations) as [GTFS](https://developers.google.com/transit/gtfs/).** These GTFS data sets look & feel like a database dump, so a lot of processing needs to be done to actually consume this data.

Modules containing processed static data:

- [`vbb-gtfs.jannisr.de`](https://vbb-gtfs.jannisr.de/) – Raw data for Berlin & Brandenburg public transport.
- [`vbb-stations`](https://github.com/derhuerst/vbb-stations) – A list of stations.
- [`vbb-lines`](https://github.com/derhuerst/vbb-lines) – Lines and their stations.
- [`vbb-lines-at`](https://github.com/derhuerst/vbb-lines-at) – Which lines run at a station?
- [`vbb-stations-connected-to`](https://github.com/derhuerst/vbb-stations-connected-to) – Get all stations connected to a station.
- [`vbb-trips`](https://github.com/derhuerst/vbb-trips) – When do trains run where?
- [`vbb-shapes`](https://github.com/derhuerst/vbb-shapes) – Shapes of lines.
- [`vbb-runs-every`](https://github.com/derhuerst/vbb-runs-every) – Compute frequencies of departures and routes. *unmaintained*
- [`vbb-translate-ids`](https://github.com/derhuerst/vbb-translate-ids) – Translate VBB IDs from 9-digit to 12-digit and reverse.
- [`vbb-static`](https://github.com/derhuerst/vbb-static) – *outdated, use the modules above*

Modules to find stations:

- [`vbb-stations-autocomplete`](https://github.com/derhuerst/vbb-stations-autocomplete) – Autocomplete stations.
- [`vbb-find-stations`](https://github.com/derhuerst/vbb-find-stations) – Search for stations.
- [`vbb-find-station`](https://github.com/derhuerst/vbb-find-station) – Search for a station.
- [`vbb-stations-cli`](https://github.com/derhuerst/vbb-stations-cli) – Find and filter stations from the command line.

Modules with additional data:

- [`vbb-fare-zones`](https://github.com/derhuerst/vbb-fare-zones) – All VBB stations and their fare zones.
- [`vbb-station-operators`](https://github.com/derhuerst/vbb-station-operators) – Which operator services a Berlin public transport station?
- [`vbb-common-places`](https://github.com/derhuerst/vbb-common-places) – Aliases for common stations.
- [`vbb-osm-relations`](https://github.com/derhuerst/vbb-osm-relations) – VBB lines, platforms, entrances and their OSM relations.
- [`vbb-station-photos`](https://github.com/derhuerst/vbb-station-photos) – Photos of every subway station in Berlin.
- [`vbb-stations-with-wifi`](https://github.com/derhuerst/vbb-stations-with-wifi) – All VBB stations with free wifi.
- [`vbb-logos`](https://github.com/derhuerst/vbb-logos) – Nice SVG logos for Berlin & Brandenburg public transport.
- [`vbb-entrances`](https://github.com/derhuerst/vbb-entrances) – Entrances for VBB stations. *outdated*
- [`vbb-delays-list`](https://github.com/derhuerst/vbb-delays-list) – Statistics on delays at VBB stations. *unfinished*
- [`vbb-graph`](https://github.com/derhuerst/vbb-graph) – Berlin & Brandenburg public transport as JSON graph.

## APIs

VBB also **[provides an API](https://www.vbb.de/de/article/fahrplan/webservices/schnittstellen-fuer-webentwickler/5070.html)** under a proprietary license. This *public* API provides all the information they have, but [is unstable and rate-limited, doesn't have CORS and isn't REST](https://github.com/derhuerst/vbb-rest/blob/master/docs/why.md#why-use-this-api).

The VBB app talks to another ***private* API that has neither rate limits nor authentication**. Please note that the usage of this API is not officially endorsed and does not have any licensing. Use it through the modules below at your own risk.

These modules can be used to query data from the (private) API and other places.

- [`vbb-client`](https://github.com/derhuerst/vbb-client) – An API client for `vbb-rest`, covering all of VBB, deployed at `2.vbb.transport.rest`.
- [`vbb-rest`](https://github.com/derhuerst/vbb-rest) – An HTTP API, covering all of VBB.
- [`vbb-hafas`](https://github.com/derhuerst/vbb-hafas) – A client for their HAFAS API.
- [`hafas-departures-in-direction`](https://github.com/derhuerst/hafas-departures-in-direction) – Pass in a HAFAS client, get departures in a certain direction.
- [`hafas-collect-departures-at`](https://github.com/derhuerst/hafas-collect-departures-at) – Utility to collect departures, using any HAFAS client.
- [`hafas-client`](https://github.com/derhuerst/hafas-client) – A client for HAFAS mobile APIs.
- [`hafas-rest-api`](https://github.com/derhuerst/hafas-rest-api) – Expose a HAFAS client via an HTTP REST API.
- [`vbb-disruptions`](https://github.com/derhuerst/vbb-disruptions) – Disruptions in VBB public transport.
- [`vbb-monitor`](https://github.com/derhuerst/vbb-monitor) – Fetch all departures of all lines at all stations.
- [`vbb-positions-stream`](https://github.com/derhuerst/vbb-positions-stream) – A realtime stream for positions of buses and trains.

## Tools, UIs & Experiments

- [`vbb-cli`](https://github.com/derhuerst/vbb-cli) – A CLI for VBB.
- [`vbb-telegram`](https://github.com/derhuerst/vbb-telegram) – A Telegram bot for VBB.
- [`vbb-map-routing`](https://github.com/derhuerst/vbb-map-routing) – Travel in Berlin, using a map. *unfinished*
- [`vbb-journey-ui`](https://github.com/derhuerst/vbb-journey-ui) – UI component for displaying a journey like in Google Maps.
- [`vbb-delays-map`](https://github.com/derhuerst/vbb-delays-map) – A map showing delays of public transport in Berlin. *outdated*
- [`record-vbb-delays`](https://github.com/derhuerst/record-vbb-delays) – Generate statistics on delayed departures.
- [`generate-vbb-gtfs`](https://github.com/derhuerst/generate-vbb-gtfs) – Generate clean GTFS from VBB data. *unfinished*
- [`bvg-topological-map`](https://github.com/derhuerst/bvg-topological-map) – BVG transport map as a nice SVG.
- [`vbb-stations-html`](https://derhuerst.github.io/vbb-stations-html/) – An HTML index of all VBB stations.
- [`vbb-web`](https://github.com/derhuerst/vbb-web) – A web client for Berlin & Brandenburg public transport.
- [`vbb-anybar`](https://github.com/derhuerst/vbb-anybar) – Let the status bar show you when to catch the train.
- [`vbb-get-off-bot`](https://github.com/derhuerst/vbb-get-off-bot) – A Telegram bot that helps you get off your train on time.
- [`berlin-commute-footprint`](https://github.com/derhuerst/berlin-commute-footprint) – Compare cost, environmental and health impact of commuting by car, public transport of bike. *unfinished*
- [`predict-vbb-delays`](https://github.com/derhuerst/predict-vbb-delays) – Predict delays of Berlin public transport vehicles. *unfinished*
- [`vbb-routing`](https://github.com/derhuerst/vbb-routing) – Compute journeys based on the VBB GTFS data. *unfinished*
- [`naive-gtfs-routing`](https://github.com/derhuerst/naive-gtfs-routing) – A naive routing engine for GTFS data. *unfinished*

From the [*How to automatically generate transit maps.*](https://github.com/public-transport/generating-transit-maps) experiment:

- [`generate-vbb-graph`](https://github.com/derhuerst/generate-vbb-graph) – Berlin & Brandenburg public transport as JGF file.
- [`generate-vbb-transit-map`](https://github.com/derhuerst/generate-vbb-transit-map) – Generate an SVG transit map for Berlin public transport.
- [`transit-map-generator`](https://github.com/derhuerst/transit-map-generator) – Generate and optimize transit maps interactively. *unfinsihed*
- [`vbb-graph-computation-server`](https://github.com/derhuerst/vbb-graph-computation-server) – A web service to queue VBB transit map computations. *unfinsihed*

Modules I'm not willing to maintain right now:

- [`vbb-map`](https://github.com/derhuerst/vbb-map) – Render lines on a map. *unmaintained*
- [`vbb-osm-map`](https://github.com/derhuerst/vbb-osm-map) – Render lines on a map, using OpenStreetMap. *unmaintained*
- [`vbb-toy-map-feed`](https://github.com/derhuerst/vbb-toy-map-feed) – A live feed for the BVG delays map. *unmaintained*
- [`vbb-station-graph`](https://github.com/derhuerst/vbb-station-graph) – Visualize public transport next to any station. *unmaintained*

## Community

Modules by others, sorted by latest activity:

- [`vbb-stations`](https://github.com/poldixd/vbb-stations) – Lists of stations in Berlin which are operated by BVG or S-Bahn.
- [`MMM-PublicTransportBerlin`](https://github.com/deg0nz/MMM-PublicTransportBerlin) – MagicMirror module to display public transport with VBB Hafas data.
- [`vbb-interactive`](https://github.com/domsson/vbb-interactive) – Attempt to draw the VBB public transport map with JS and SVG
- [`isometric-icons`](https://github.com/tursics/isometric-icons) – VBB toy map, created at mobility{hacks} 2016
- [`vbb-delay-map`](https://github.com/juliuste/vbb-delay-map) – VBB delay map, created at mobility{hacks} 2016
- [`vbb-bot`](https://github.com/brene/vbb-bot) – A bot that tells you times for public transport in Berlin
- [`InfoVis-VBB-Fahrplandaten-Starplot`](https://github.com/sto3psl/InfoVis-VBB-Fahrplandaten-Starplot) – Eine Informationsvisualisierung der VBB-Fahrplandaten von Dezember 2014 bis Dezember 2015.
- [`VBBNow`](https://github.com/docterd/VBBNow) – A VBB NotificationCenter Widget. It shows the nearby transit information
- [`vbb_permalink`](https://github.com/westberliner/vbb_permalink) – Ein Bookmarklet, das Permalinks von VBB-Fahrinfo und der Deutschen Bahn generiert.
- [`berlin-transport-status`](https://github.com/mschneider/berlin-transport-status) – Distributed crawler for VBB-Fahrinfo written in node.js
- [`vbb-json`](https://github.com/stefanw/vbb-json) – JSON-API wrapper around the VBB API
- [`vbbFXOS`](https://github.com/derroman/vbbFXOS) – vbb maps ported to firefox os
- [`vbb-coverage`](https://github.com/domoritz/vbb-coverage) – Visualization of the VBB data from [`daten.berlin.de`](http://daten.berlin.de/datensaetze/vbb-fahrplan2012)

## Utilities

These modules perform a specific distinct task. They are used by the modules above.

- [`vbb-parse-line`](https://github.com/derhuerst/vbb-parse-line) – Parse VBB lines like M4, TXL, S42.
- [`vbb-sort-lines`](https://github.com/derhuerst/vbb-sort-lines) – Sort VBB lines by their importance.
- [`vbb-mode-weights`](https://github.com/derhuerst/vbb-mode-weights) – Weights of modes of public transport in Berlin.
- [`merge-vbb-stations`](https://github.com/derhuerst/merge-vbb-stations) – Heuristic to find VBB stations & stops that should be one.
- [`merged-vbb-stations`](https://github.com/derhuerst/merged-vbb-stations) – A precomputed list of VBB stations that should be one.
- [`vbb-parse-ticket`](https://github.com/derhuerst/vbb-parse-ticket) – Parse ticket information from the HAFAS API.
- [`vbb-short-station-name`](https://github.com/derhuerst/vbb-short-station-name) – Remove noise from station names.
- [`vbb-tokenize-station`](https://github.com/derhuerst/vbb-tokenize-station) – Make station names search-safe.
- [`vbb-util`](https://github.com/derhuerst/vbb-util) – JavaScript utilites for `vbb-hafas`.
- [`are-vbb-hafas-stations-the-same`](https://github.com/derhuerst/are-vbb-hafas-stations-the-same#are-vbb-hafas-stations-the-same) – Check if two stations from the VBB API should be one.
- [`hafas-discover-stations`](https://github.com/derhuerst/hafas-discover-stations#hafas-discover-stations) – Pass in a HAFAS client, discover stations by querying departures.
- [`hafas-estimate-station-weight`](https://github.com/derhuerst/hafas-estimate-station-weight#hafas-estimate-station-weight) – Pass in a HAFAS client, estimate the importance of a station.
- [`hafas-monitor-journeys`](https://github.com/derhuerst/hafas-monitor-journeys) – Use any HAFAS API to monitor journeys from A to B.
