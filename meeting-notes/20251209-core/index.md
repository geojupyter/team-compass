---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2025-12-09"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2025-12-09)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/99659397059?pwd=519zZJlcAa1TCyJWRYyYbaYDfuaXNo.1)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=4pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Nicolas Brichet / `@brichet` / QuantStack


### Standing items


### Follow-up from previous meeting(s)


### New agenda items

- [ ] JupyterGIS updates
    - Story maps: Greg making lots of cool progress!
        - Ex: https://projects.sfchronicle.com/2019/kincade-fire-origin/
        - https://github.com/geojupyter/jupytergis/pull/994
        - Can set landmarks, attach text, advance through the landmarks, configure transitions (maybe more!)
        - Currently, the story text is in the side panel
        - Do we need a kernel for story maps? Maybe not for the first iteration on this feature. Enables embedding in static sites! But later, with a kernel, we could have cool features like widgets in the story!
            - Interactive story maps could enable new playful/sandbox experiences that are powerful persuasion or decision-making tools
    - Data model binding to the renderer
        - It would be nice to support more renderers for situations when OL doesn't do what we want (e.g. large geoparquet dataset!)
        - This could be confusing to users. But maybe we have a default renderer and offer the ability to swap it out with e.g. `pip install jupytergis-deckgl`?
        - Our data model needs some work to not be coupled with openlayers concepts, and instead model for simplicity and use adapters between our data model and renderers.
    - STAC:
        - Greg working on adding Copernicus catalog
        - Interns working on generic STAC interface. Should have progress by Feb 15, but it may not be fully releasable at that time (?); more of a base for some finishing touches like additional filters to help users navigate large catalogs.
    - Strategy:
        - How do we support making the architecture more robust?
        - Path to more funding and capacity: More people and orgs using JGIS as a daily driver, a critical dependeny
        - What's stopping people from using JupyterGIS as a daily driver?
            - Bugs or features?
        - Path to getting new daily driver users?
            - Develop a single use case "happy path" and make it very robust, including necessary architecture improvements. E.g. tight integration with a Notebook workflow using Xarray and GeoDataFrame datasets.
            - Estimate number of developer hours required with team
            - Submit for funding
            - As more daily driver users onboard, more willingness to fund additional features and robustness will come.
        - Matt: Discuss with Sylvain!


### Pushed to next meeting