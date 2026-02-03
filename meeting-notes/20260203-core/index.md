---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2026-02-03"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2026-02-03)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/99659397059?pwd=519zZJlcAa1TCyJWRYyYbaYDfuaXNo.1)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Martin RENOU / `@martinRenou` / QuantStack
* Greg Mooney / `@gjmooney` / QuantStack


### New agenda items

- [Specta](https://github.com/trungleduc/specta) stuff
    - Story maps!
        - Hooks in to Specta's "presentation" mode, and in that case renders the story viewer instead of the regular JupyterGIS interface.
    - Mobile view.
        - Detects Specta in "presentation" mode, and if the screen is small renders differently.
    - Can also write e.g. a blog post as a Notebook, with JupyterGIS widgets, and view in Specta's blog post view
    - TODO: Add to Lite deployment in docs of JupyterGIS
    - TODO: Tutorial on story map, how to use Specta
- Layer gallery improvements!
    - More types supported, not just raster
    - Simpler representation in the JSON
- `jupyter-xarray-tiler`
    - https://github.com/geojupyter/jupyter-xarray-tiler
    - Problem: Have to write out xarray datasets to file to visualize
        - Solution: TiTiler / xpublish-tiles!
    - Problem: Running a tile server in a kernel, and running a map visualizer in browser JS means sometimes you can't access the tile server, e.g. JupyterLab running in a kubernetes pod (JupyterHub) without exposed ports.
        - Solution: jupyter-server-proxy!
    - `jupyter-xarray-tiler` is just glue between jupyter-server-proxy, titiler (and eventually other backends like xpublish-tiles), and a mapping front-end. It's aimed at authors of map viz libraries for Jupyter, not end-users.
    - Martin: What about other formats than Xarray? Zarr?
        - Matt: Have been thinking about GeoDataFrames as well. Should we bundle that in the same library? :thinking_face: Maybe? I don't know. In any case I'm totally fine with changing the name if we go that route :)
        - Matt: xpublish-tiles supports Zarr. But not TiTiler AFAIK. There's a  few options now for directly visualizing Zarr from OpenLayers (e.g. https://github.com/NOC-OI/zarr-maps) as well. Do we need a solution like this for Zarr? :thinking_face:
- mambajs: Generate notebook.link lockfiles from CLI!
    - https://pypi.org/project/mambajs/
    - Previously needed to be done from the notebook.link web UI, now we can build it in to our automated tooling.
