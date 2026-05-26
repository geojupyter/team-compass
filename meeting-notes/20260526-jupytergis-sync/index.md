---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-05-26"
image: "../images/standup.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "JupyterGIS notes"
tags: [jupytergis-notes]
---

> :pray: **Our apologies, there's no time for introductions!**
>
> We're excited for you to join us, but this meeting is _short_ and _task-focused_.
> Please attend community meetings
> ([see GeoJupyter calendar](https://geojupyter.org/calendar))
> to meet the team and add your own agenda items, and/or
> [introduce yourself on  Zulip](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/Welcome)!

# JupyterGIS sync meeting (2026-05-26)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Name / GitHub ID / affiliation
* Martin Renou / `@martinRenou` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack
* Benjamin Szeghy / `benjaminszeghy` / Schmidt DSE
* 


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* [`jupytergis[tiler]`](https://github.com/geojupyter/jupytergis/pull/1347) - tests WIP! What else do we need to be ready to merge?
    * Martin: Pinning to 3.13 in CI is fine!
    * Martin: Concerned about conflicts with symbology PR. Prefer to merge the tiler PR first!
* geoprocessing / code generation PoC/demo
    * Martin: :tada: 
    * Matt: Like the idea to move this into a dedicated repository representing processing operations and their translations into different runners (Python/Pandas, Python/Polars, GDAL, GRASS, R, etc.) as just data, reusable in many software projects.
        * Martin: In QGIS, processing defined as Python classes. They have arguments, and templates to generated GDAL. This is really just data
    * UI: Where does the dialog for geoprocessing go? Right panel, toolbar button and dialog?
* OpenEO! https://github.com/geojupyter/jupytergis/pull/1409
* Scrollytelling work continuing!


### Requests for help or feedback

* Matt: Review Python symbology PR (https://github.com/geojupyter/jupytergis/pull/1420)