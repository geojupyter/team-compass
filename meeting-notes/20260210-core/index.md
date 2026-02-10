---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2026-02-10"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2026-02-10)

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

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Esha / e5ha / UC Berkeley
* Benny / benjaminszeghy / UC Berkeley


### New agenda items

- [ ] [jupyter-xarray-tiler](https://jupyter-xarray-tiler.readthedocs.io/)
    - The idea: A toolkit for developers of Jupyter interactive map widgets (ipyleaflet, leafmap, folium, ipyopenlayers) to add support for visualizing Xarray datasets without writing to a file (the typical approach). Uses TiTiler (maybe eventually xpublish-tiles) to serve map tiles. Uses jupyter-server-proxy to enable the JS map app to access the tiles regardless of where Jupyter is running ([needs testing](https://github.com/geojupyter/jupyter-xarray-tiler/issues/21)).
    - Is this a good idea? Leafmap currently [has tooling for visualizing Xarray datasets ](https://leafmap.org/common/?h=array_to_memory_file#leafmap.common.array_to_memory_file), but it seems to write the entire array to a memory file to make this work. Does the tiler approach work better on constrained systems (e.g. JupyterHub)?
        - Benny: E.g. on a 4GB JupyterHub instance, would the memory file approach crash the server?
        - Benny: Will find a huge raster for testing!
        - TODO: Compare with other approaches! https://github.com/geojupyter/jupyter-xarray-tiler/issues/22
        - Esha & Benny: Will try some other approaches together tomorrow!
    - Demo
- [ ] More clear onramps for new community members
    - Common quesiton: "I want to get involved, but I don't know where to start!"
    - How can we better surface startable issues for new community members?
    - How can we better direct folks to this location :point_up: How can the website change to serve this need?