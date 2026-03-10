---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-03-10"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-03-10)

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

* Nakul Verma / `@nakul-py` / affiliation
* Martin Renou / `@martinRenou` / QuantStack
* Benjamin Szeghy / `@benjaminszeghy` / UC Berkeley
* Greg Mooney / `@gjmooney` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE


### Standing items

- [ ]


### Follow-up from previous meeting(s)

- [ ]


### New agenda items

- Benny - Demo: Reproducible GUI interactions 
    - ...
    - How can this be integrated with JupyterGIS?
    - Martin:
        - I really like the QGIS processing toolbox way of doing reproducible actions -> generates code equivalent to what you do in the UI
        - keep in mind it won't be only about Python. We are planning on making a R API as well
        - you should play with jupyterlite-ai if you haven't already. Unlike the name suggests, it's not only working in jupyterlite
        - we should use commands to help LLMs leverage these actions (https://github.com/geojupyter/jupytergis/pull/969)
        - Maybe have an intermediate repr of actions and then translate that to code.
    - How can we make this modular?
        - Have a separate package containing schemas for actions and translators for actions (JSON structures) -> Python, R, ?
- Move ipyopenlayers into GeoJupyter organization?
    - May help people contribute
    - Let's do it!
    - Feels "wrong" to have a Python API under JGIS and separate one under ipyopenlayers. Can we share logic? IpyOL could have an API which talks to different frontends. Are we just describing leafmap
    - https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/How.20do.20we.20make.20GUI.20actions.20more.20reproducible.3F/with/578044376
- Matt - [jupyter-xarray-tiler](https://jupyter-xarray-tiler.readthedocs.io/) now supports Xpublish
    - https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/jupyter-xarray-tiler.3A.20your.20Jupyter.20map.20widget.2Fapp.20.3C-.3E.20Xarray/with/575339311
- Nakul - How to prevent deletion of source parameters of original layer when deleteng the duplicated layer.
    - Use case of duplicating layers: want to change layer settings overrides for each segment; before we had source overrides, you had to duplicate layers to change source parameters. Even if we have source overrides, it still makes sense to duplicate a layer. Maybe even copy-paste a layer from one project to another.
    - Matt: Are we over-optimizing by sharing source? Should we allow both duplicating (copying source and layer) and creating a new **view** of a layer (shared source)?
    - Don't remove a source if a layer points to it. Update the implementation of remove source to not delete the source if there's still a live reference.
- Story maps
    - Form refactor -- layers created twice (fighting RJSF). Promises resolved early (why are there even promises?).
    - Mobile view for Specta presentations (drawer, click through story segments, doesn't work with scrolling yet)
    - Styling away the gradient? No way to do that right now, but there should be an option.
        - Custom CSS for whole project?
        - Ability to override jupytergis settings (jupyterlab settings) in the project file? Package that with the JGIS file?
        - Martin: Bad idea! People will break everything if they edit the CSS and then open issues :) Support and respect JupyterLab themes, have folks make a JLab theme.
            - Maybe if we allow customizing CSS but communicate that this is unsafe and done at own risk.
- 
- 
- 
- /


### Pushed to next meeting

- [ ]
