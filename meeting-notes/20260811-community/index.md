---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-08-11"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-08-11)

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

* Matt / `@mfisher87` / Schmidt DSE
* Greg / `@gjmooney` / QuantStack
* Martin / `@martinRenou` / QuantStack
* Benny / `@benjaminszeghy` / Schmidt DSE


### New agenda items

- Proposed activity: Collaborate on some docs! Explain the various global state / models, and when a contributor should use which for what.
    - model:
    - sharedModel: Goes in JGIS file
    - awareness: Transient state (cursor location, viewport location, ...)
    - JupyterLab stateDB (localstorage): State of your local application (panels, size, files open). We could put e.g. embedded terminal state, size of left/right panels in there.
    - uiState: left/right panel open (and GPS location indicator boolean). Persists between reloads (because we save it to stateDB? Or local storage? Not sure at the moment)
    - Settings: Deployment wide feature flags
    - IMPORTANT: Codify what is driven by settings vs StateDB vs ...? How do things persist!
    - Matt: TODO: start this doc
- Galata snapshot comment workflow
    - Switch to using inline playwright report action?
    - Upstream a workflow to automate posting a PR comment!
- Collab labelling improvements
    - postgis db and the tile server
    - OL can listen to changes coming from PostGIS!
    - a ydoc is the working copy
    - toolbar button to sync to PostGIS
        - When you click it, the file is drained to PostGIS
        - Probably will be a timer or based on number of changes or both
        - Martin: Toolbar button is perhaps actually useful! Makes saving explicit.
        - We do `.clear()` to drain it -- is this "out of band" or CRDT-mediated change? We think this is a CRDT message. (TODO: Link docs!)
    - [TiPG](https://developmentseed.org/tipg/) from devseed is the tile server -- serves MVT
    -
    - Open questions:
        - How does user do analysis on data that's in the PostGIS DB?
            - https://geopandas.org/en/stable/docs/reference/api/geopandas.GeoDataFrame.from_postgis.html ?
        - Should the sync be triggered by automatically or by a button?
            - In normal Notebook collab, CTRL+S is a no-op, it's always automatically synced.
            - If we implement autosave in the front-end we end up with conflicts if multiple people are trying to save at the same time. We should implement this to work the same way notebook saving works except writing to a DB instead of a file.
- Notebook.link may soon be collaborative! WebRTC! Requires some infrastructure to set up.
    - Linux Foundation CFP to run the handshake server as a public service? Or AWS donate some infra?
- Benny: Merge combobox change?
    - Yes!
    - Should we switch to a dev trunk workflow?
- Tailwind?
    - We trust Greg :grin:
