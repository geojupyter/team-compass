---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-06-09"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-06-09)

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

* Nicolas Brichet / @brichet / QuantStack
* Matt / `@mfisher87` / SchmidtDSE
* Guillaume Eynard-Bontemps / @guillaumeeb / CNES
* Greg Mooney / @gjmooney / QuantStack


### New agenda items

- Glossary!
    - https://github.com/geojupyter/jupytergis/pull/1491
    - https://github.com/geojupyter/jupytergis/issues/1479
    - Would love feedback on glossary in general + symbology terms
    - Nicolas: +1
    - TOC on index page doesn't include glossary, just includes h2 headers of the about/index page?
- Story map stuff!
    - Merged article-style specta view (named "vertical scroll") and mobile view
    - Adding global navigation in title bar in the Specta list mode, replacing the one that was at the bottom
- How to easily run jupyter-tiler or openEO stuff (binder link?)
    - Two issues:
        - Binder links in PRs aren't working (might be linked to CNES network)
        - No binder link in README for main branch / latest release
    - For now try it out with uv:
        - `uv run --with jupytergis==<version> --with jupyterlab jupyter lab`