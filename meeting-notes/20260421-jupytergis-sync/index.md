---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-04-21"
image: "../images/standup.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "JupyterGIS notes"
tags: [jupytergis-notes]
---

> :pray: **Our apologies, there's no time for introductions!**
>
> We're excited for you to join us, but this meeting is _short_ and _task-focused_.
> Please attend community meetings
> ([see GeoJupyter calendar](https://geojupyter.org/calendar))
> to meet the team and add your own agenda items, and/or
> [introduce yourself on  Zulip](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/Welcome)!

# JupyterGIS sync meeting (2026-04-21)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt / `@mfisher87` / Schmidt DSE
* Greg / `@gjmooney` / QuantStack
* Vincent / `@vincentsarago` / Development Seed


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* Greg: PR for drawing vector layers
    * Matthias review
* Greg: Fixup awareness updates
    * Break things up in to many fields/signals: selectedLayer, viewportState, identifiedFeatures, remoteUser, cursorPosition,
* Vincent: Notebook for calculating at tile request time
    * Needs an additional endpoint (mosaic endpoint instead of dataarray endpoint)
        * Backend to run search queries to get items and create xarray data array for each tile (opposite of current). DataArray created on each tile request.
        * Define Array, create path dependency, create factory for tile requests with dependency of search request. Pass this to the endpoint.
    * Something needs to change in jupyter-xarray-tiler to do this
    *
* Matt: working on integrating jupyter-xarray-tiler with jupytergis
* Vincent: Update ... to get rid of Xarray because it's slow. titiler-xarray will stay for now, but may switch to titiler-zarr and go into maintenance mode. DevSeed goal is to move more towards Zarr support.
    * EOPF: Testing new data format. Many arrays in one Zarr store. Takes 5-7 seconds to open, then can create tiles. Super slow! Decided to work with Zarr-Python to get asynchronous behavior.
    * Vincent: For local tiling, look at XPublish?
        * Matt: Already looking ;)
