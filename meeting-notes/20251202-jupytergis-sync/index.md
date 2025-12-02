---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2025-12-02"
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
> Please attend core community meetings
> ([see GeoJupyter calendar](https://geojupyter.org/calendar))
> to meet the team and add your own agenda items, and/or
> [introduce yourself on  Zulip](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/Welcome)!

# JupyterGIS sync meeting (2025-12-02)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Greg Mooney / `@gjmooney` / QuantStack
* Martin Renou / `@martinRenou` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* STAC
    * New catalog will be Copernicus: https://browser.stac.dataspace.copernicus.eu/search?.language=en
    * Our STAC Browser may not have the right name. We can call the interface for selecting a catalog a "STAC Browser" and the interface for interacting with the selected catalog could be called something like "STAC Search"
    * Radiant Earth's STAC Browser https://radiantearth.github.io/stac-browser/
* TanstackQuery: We should investigate this!
* Switch to pnpm:
    * Remove yarn.lock, replace with pnpm lock
    * Search and replace jlpm -> pnpm
    * Lerna config updates: learna.json sets npm client to jlpm
    * Matt can invest time in this in the new year
* Hatchling upgrade causing build failures
    * https://github.com/geojupyter/jupytergis/pull/1010
    * Do we need both an upper bound _and_ to switch to `python -m build`? Martin finding out!
