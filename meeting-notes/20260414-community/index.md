---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-04-14"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-04-14)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/99659397059?pwd=519zZJlcAa1TCyJWRYyYbaYDfuaXNo.1)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Attendees

Your name / GitHub ID / affiliation / icebreaker

* Matt Fisher / `mfisher87` / affiliation / ?
* Martin Renou / `@martinRenou` / QuantStack
* Greg Mooney / `@gjmooney` / QuantStack
* Vincent Sarago / `@vincentsarago` / DevelopmentSeed
* Benjamin Szeghy / `@benjaminszeghy` / UC Berkeley



### New agenda items

- [Community initiatives](https://github.com/orgs/geojupyter/projects/6) -  roadmapping as a "forum" inspired by 2i2c & JupyterHub community.
    - What would you add?
    - How to organize sub-initiatives (e.g. the upcoming QuantStack grant work for JuptyerGIS)?
    - Suggestions for how this can be useful as a discussion platform in addition to a visualization of where we're going? How to spur community input?
    - New label: "needs funding"
    - Try and demo with Sylvain next week
- JupyterGIS grants
- OpenEO process graph layers + titiler-openeo server component
    - Martin: Started looking in to introducing new layer type in JGIS, and it's basically saving the process graph for OpenEO in the layer "presentation" (?) Make use of titiler-openeo to serve tiles.
- Greg: demo: dynamic NDWI algorithm on the fly while panning/zooming the JupyterGIS map, from the Python notebook, and serving with jupytergis-tiler 
    - Showing dynamic computation and tiling of data in viewport
    - Calculates in advance before handing data to titiler
    - vincent: https://github.com/developmentseed/titiler-stacapi can help with visualizing data from stac but not the dynamic computation problem
        - Does this work with only STAC API? Or also static file catalog?
            - Vincent: Relies on pystac-api, not sure!
        - Vincent: Investigating whether titiler-stacapi makes sense!
- Reproducible viz -> Notebook workflows
- Adopting `uv` (& `pixi`?)
    - Martin: Let's keep uv for #1290, but move towards full-repo pixi adoption!