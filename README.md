# Documentation for June 2025 interactive map of new bus routes

================
* [Overview](#overview)
* [Data](#data)
* [Methodology](#methodology)
  * [What's in here?](#whats-in-here)
* [Limitations & Assumptions](#limitations--assumptions)
* [Credit](#credit)

## Overview
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

The D.C. Metro will replace all of its bus routes on June 29, the first major overhaul of the network since it began operation 50 years ago. Nine “Better Bus” routes will replace existing routes through American University and Tenleytown.

We were dissatisfied by [Metro's existing maps](https://www.wmata.com/initiatives/plans/Better-Bus/upload/Resource_2025-Network_District-of-Columbia-Map.pdf) that were difficult to read and on too great a scale to be relevant to AU students. That's what this map seeks to fix.

## Data
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

At the start of June, Metro [published data](https://developer.wmata.com/api-details#api=gtfs&operation=bus-gtfs-static-bbnr-qa) for the new bus routes in a format known as the General Transit Feed Specification, or GTFS, mainly for mapping companies to configure the new transit routes.

Metro [explains](https://developer.wmata.com/license#o01lq): "The GTFS provides users and developers certain Transit Data either statically through a series of text files collected in a downloadable .Zip file or through a real-time GTFS feed. The static GTFS provides the same schedule data that supports WMATA’s online trip planner."

## Methodology
*[Back to top](#documentation-for-june-2025-interactive-map-of-new-bus-routes)*

We downloaded the GTFS .Zip file and used the JavaScript package gtfsToGeoJSON to convert the data into GeoJSON