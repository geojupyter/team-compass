---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-07-14"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-07-14)

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

* Benjamin Szeghy / `@benjaminszeghy` / Schmidt DSE
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack


### New agenda items

- Greg - Attributees / Properties naming decision & PR https://github.com/geojupyter/jupytergis/pull/1616
    - Discussion: https://github.com/geojupyter/jupytergis/issues/1589
    - We decided "Attributes"!
    - Already encoded in glossary: https://jupytergis.readthedocs.io/en/latest/about/glossary.html#term-Attribute
    - TODO: Matt close issue
- Matt - (WIP) Adding Python type checking! https://github.com/geojupyter/jupytergis/pull/1617
- Matt - Fixing up type names: https://github.com/geojupyter/jupytergis/pull/1622
- Benny - ask Greg how he feels about adding a "traverse mode" or gps-based entry for his data drawing tool (I can work on this)
    - In mainview, there's a drawend event to finish draw mode, this is what adds a feature to a layer.
    - Right now, you need to manually create an empty GeoJSON layer. We think you can only draw on either empty GeoJSON layers or GeoJSON layers with only features with the "fromDrawTool" attribute on them.
        - This UX could use a little work; create a layer for you or let you choose a compatible layer?
- Benny - I ran into hard-coded CRS (web mercatur) in the code. Something for converting lat/lon <-> x/y. Is fixing this something we want to tackle?
    - TODO: Open an issue!
        - Benny: Hardcoding
        - Matt: Change projection in GUI (https://github.com/geojupyter/jupytergis/issues/1626)
