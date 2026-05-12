---
title: "GeoJupyter community meeting"
description: |
  A monthly gathering of the GeoJupyter community. Open to all!
date: "2026-05-12"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter community meeting (2026-05-12)

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
* Matthias Meschede / `@mmesch` / QuantStack
* Nicolas Brichet / `@brichet` / QuantStack
* Benjamin Szeghy / `benjaminszeghy` / UC Berkeley
* Greg Mooney / `@gjmooney` / QuantStack
* Guillaume Eynard-Bontemps / `@guillaumeeb` / CNES


### Action items

- [ ]


### Standing items

- [ ]


### New agenda items

- Conferences
    - EGU last week! Matthias attended and submitted an abstract.
      Lots of interest in JGIS!
      Should show more presence there, show that it's a stable project and not a one-off.
        - Matthias planning to attend more conferences
        - Asked about AGU? Last year: https://events.geojupyter.org/conferences/2025-agu/
        - AGU this year? Maybe scaled down participation compared to last year? Unclear.
    - [Cloud Native Geospatial Forum 2026](https://2026.cloudnativegeo.org/)! Matt & Guillaume preparing a talk
        - https://hackmd.io/@x9qbxSGiQv2LrxJlmY0LsQ/SJUARv1yGg
        - Any QuantStack folks coming? Probably not!
    - ESA EO tooling forum
        - Guillaume
    - Living Planet Symposium is every 2 years, not this year!
    - [Compute!](https://compute.events/paris2026/) conference.
    - Others coming up!
- PR grammar symbology (Matthias)
    - Schema? Schema is now more strict but not generating the form from schema yet.
    - Matthias considering more strict runtime validation of schemas
        - Disadvantage: Would break projects during development of a new release.
        - We should learn how other projects do schema migrations!
    - Recent PR decoupled OL expressions from schema. Grammar is coming after that. Since we didn't release or have migration scripts since the OL PR, any projects created with the development version will break with the next release!
    - TODO: Non-linear mapping (not for this PR)
    - TODO: Update Python API
    - TODO: Migrations
    - Replace old UI or keep both?
        - Matt, Martin: Replace!
            - Martin: Worried about QGIS export. Does it still work?
    - Break into its own package?
    - When do we merge? Polish first, or merge now?
        - Matt & Martin: Merge now!
    - Filtering: Currently AND only, no OR. E.g. can't filter middle values out with "X < 5 OR X > 7"
- Matt: Worried about duplication of logic in programmatic APIs & JS
- Vega expression
    - Nakul built a Vaga -> OL compiler! Opened a PR but it's on hold right now, fits better in Matthias' grammar PR. Vega becomes a "mapping" algorithm?
    - Separate PR: Visualize the mapping! Map on a chart X->Y
    - TODO: Move to draft until rebased on grammar PR
- https://github.com/awesome-spectral-indices/awesome-spectral-indices
    - Could these spectral indices be built in to the UI? User selects NDWI for example and the symbology editor fills in the details.
    - NDVI and NDSI really classic. Some more complex: Automated Water Extraction Index


### Pushed to next meeting

- Geoprocessing generator library
- PR mobile compatibility (Matthias)
- GeoZarr support incoming https://github.com/geojupyter/jupytergis/pull/1400
- AI policy?
