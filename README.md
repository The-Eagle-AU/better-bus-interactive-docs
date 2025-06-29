# Documentation for June 2025 interactive map of new D.C. bus routes

================
* [Overview](#overview)
* [Data](#data)
* [Methodology](#methodology)
* [What's in here?](#whats-in-here)
* [Credit and disclaimers](#credit-and-disclaimers)

## Overview
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

The Washington Metropolitan Area Transit Authority replaced all of its bus routes on June 29, the first major overhaul
of the network since it began operation 50 years ago. Nine “Better Bus” routes will replace existing routes through
American University and Tenleytown.

We were dissatisfied by [Metro's existing maps](https://www.wmata.com/initiatives/plans/Better-Bus/upload/Resource_2025-Network_District-of-Columbia-Map.pdf) that were difficult to read and on too great a scale to be relevant
to AU students. That's what this map seeks to fix.

## Data
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

At the start of June, Metro [published data](https://developer.wmata.com/api-details#api=gtfs&operation=bus-gtfs-static-bbnr-qa) for the new bus routes in a format known as the General Transit Feed
Specification, or GTFS, mainly for mapping companies to configure the new transit routes.

Metro [explains](https://developer.wmata.com/license#o01lq): "The GTFS provides users and developers certain Transit Data either statically through a series
of text files collected in a downloadable .Zip file or through a real-time GTFS feed. The static GTFS provides the same
schedule data that supports WMATA’s online trip planner."

## Methodology
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

We downloaded the GTFS .Zip file and used the JavaScript package gtfsToGeoJSON to convert the data into a map-readable
format. You can replicate this step by running `gtfs-to-geojson.js`, but first make sure you add your [WMATA API](https://developer.wmata.com/)
key to `config.json` (sorry, not getting mine!).

Once the data was converted to GeoJSON, we wrote (with help from Claude) a pretty generic interactive map. It uses
Leaflet with MapTiler's Streets V2 basemap. Leaflet supports the initialization and CSS elements, such as the tooltips
and route lines.

The map itself, as deployed in our story, is hosted on my personal website and is called by an `iframe` element embedded via our CMS.

## What's in here?
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

This project contains the following files:
* `api_key.js` - Template JavaScript file for hiding your MapTiler API key (still not getting mine!)
* `better_bus_au_routes.geojson` - The route path data
* `config.json` - Configuration code for `gtfs-to-geojson.js`
* `gtfs-to-geojson.js` - The JavaScript program to convert the static GTFS feed to GeoJSON
* `prod.html` - The production-ready HTML file, which can easily be embedded or deployed on a website

## Credit and disclaimers
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

This build is subject to the [WMATA Developer License Agreement](https://developer.wmata.com/license) and the terms and copyrights of Leaflet, MapTiler
and OpenStreetMap Contributors.

Claude, a generative artificial intelligence model by Anthropic, was used as a coding companion for this project.

Everything contained in this repository is free to use. Do not remove attribution, source or documentation.