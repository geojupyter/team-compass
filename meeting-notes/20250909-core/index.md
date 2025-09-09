---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2025-09-09"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2025-09-09)

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

* Shane Grigsby / espg / Astera Institute
* Martin Renou / martinRenou / QuantStack
* Nicolas Brichet / @brichet / QuantStack
* Matt Fisher / @mfisher87 / affiliation


### Standing items

- Communication / productivity / community health:
    - What is going well?
        - Monthly structured meetings (Thanks for leading Matt! :heart:)
        - Weekly JGIS sync meetings
        - Everyone is cool af
        - Excited to have interns @ DSE
        - Collaborative vibes w/ QuantStack team
        - QuantStack adding Matt as maintainer of jupyterlite-sphinx :heart: Matt wants to find more ways to contribute to the ecosystem
        -
        -
        - /
    - Areas for improvement?
        - Community could be more active on specific needs. E.g. understanding the interchange format problem. Working groups could help?
        - Roadmap -- where is JGIS going? When should users check back to see if their use case is implemented? How do they track progress? (GitHub projects board is useful internally, but IMO not externally)
        - Funding!
        -
        -
        -
        -
        - /


### Follow-up from previous meeting(s)

- [ ]


### New agenda items

- [ ] Berkeley Hackathon last month
  - Blog post PR: https://github.com/geojupyter/geojupyter.org/pull/106
  - Published: https://geojupyter.org/blog/20250903-inperson-hackathon-and-design-dialog/
- [ ] What shape is the JupyterGIS piece of the geospatial puzzle?
  - Big topic at the hackathon! Where should we be focusing and where should we not be focusing our effort?
  - Let's document this.
  - Connecting the UI to the API
    - jdaviz API hints
    - One step after that might be recording the actions for replaying
  - What is NOT JupyterGIS?
    - What parts of QGIS are useful to have in JGIS, what parts (e.g. Model Builder?) do we want to make non-objectives?
  - If we build a provenance schema that can be used to generate reproducible code, then our tool is more compatible with AI tool calling
  - scikit-learn has a model inclusion criteria -- do we need some "rules" to help define what belongs in JGIS?
- Interchange formats?
    - Two options we know of:
        - An efficient intermediate representation (GeoArrow?) that we can send from kernel to front-end that our front-end supports (OpenLayers doesn't support GeoArrow)
        - Send imagery between kernel and renderer (comms / tile server -- tile server not compatible with JLite)
      - https://github.com/kylebarron/parquet-wasm
- [ ] Governance - what do we need? How to better distribute power in the community?
  - Working groups?
  - Frequency of community meetings? Make them less frequent to create space for working groups?
      - Nicolas, Shane: Likes 1x / month for now!
  - Use case leads
  - All: Steering committee too heavy at this stage!


### Pushed to next meeting

- [ ]
