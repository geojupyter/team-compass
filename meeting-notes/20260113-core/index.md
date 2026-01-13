---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2026-01-13"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2026-01-13)

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
* Martin Renou / `@martinRenou` / QuantStack
* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation


### Action items

- [ ] Martin: Check with Greg about what's stopping us from using stac-react
    - Matt: Open any necessary issues on the stac-react repo that would enable us to collaborate with them to build a common STAC engine for use in JGIS!


### Standing items

- [ ]


### Follow-up from previous meeting(s)

- [ ]


### New agenda items

- [ ] Status for JupyterGIS
    - STAC Filter extension support PR ready! Matt to review
        - https://github.com/geojupyter/jupytergis/pull/1035
        - Reuse / contribute to development seed [STAC react](https://github.com/developmentseed/stac-react) library?
            - Need to chat with Greg about it!
                - Martin will follow up with Greg: What do we need that stac-react doesn't have?
    - STAC doesn't support symbology because it's a custom layer type
        - Martin, Matt agree we should move towards using existing layer/source types for STAC, and move the STAC metadata for a layer (asset/item) into a new provenance field.
    - Scrolly telling map!! https://github.com/geojupyter/jupytergis/pull/1061
        - Imagining a workflow that's less coupled with JupyterGIS, perhaps using Notebook or MyST as the medium for authoring scrollytelling experiences and using Specta to deploy them! See Specta demo: https://trungleduc.github.io/specta/specta/
        - JupyterLab already has a "preview with Specta" extension! Automatically re-renders when file content changes. We could have a live preview in JLab, then deploy.
        - Matt: How does Specta integrate with (or replace) existing blogs?
            - Martin: Could write a blog index as a Notebook! Potentially generate the links to all other posts with Python?
            - Martin: Could iframe into an existing blog!
            - Martin: Build the specta post as a single static HTML build, push to your HTTP server, link to it.
    - Snapshots bot! Martin fixed it! :tada: :heart:
        - Tested with JupyterGIS! Worked as expected, tested with users with write and without write permissions
        - ~~reusable workflow~~ composite action: https://github.com/jupyterlab/maintainer-tools/pull/268
            - Matt: Pair program on exploring reusable workflows vs composite actions? Which one is more appropriate / useful? Is it worth the extra effort?
            - Matt: This actually is already a composite action, not a reusable workflow! Nevermind!
    - Matt: PR for ui testing & npm security docs: https://github.com/geojupyter/jupytergis/pull/1066
        - Martin: This should be in the JupyterLab documentation!
            - Matt: We may need to do some reorganization, this relates to both extension development and contribution to JupyterLab itself.
                - Martin: Should document that it's important to use compatible versions of JupyterLab and Galata. How to know which versions are compatible?
- [ ] Non-JupyterGIS stuff
    - Matt focusing on jupyter-xarray-tiler (currently, repo is named jupyter-microgis. will change)


### Pushed to next meeting

- [ ]
