---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-09-29"
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

# JupyterGIS sync meeting (2026-09-29)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin Renou / `@martinRenou` / QuantStack
* Matt Fisher / `@mfisher87` / DSE
* Greg Mooney / `@gjmooney` / QuantStack
* 
* 
* /


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_
* db layer PR ready for review
    * https://github.com/geojupyter/jupytergis/pull/1789
    * End users need to run their own PostGIS server and we point to it with envvar
    * tipg tile server too!
    * Database keeps separate tables for each layer by UUID
    * New Source type: FeatureStore!
    * ydoc is temp working copy, database is "final" copy!
    * UX: Logical layer group (shows up as one layer in the panel) with two layers: Base layer which is the database copy, and transient layer with the working copy (ydoc)
    * "Fold" - save working copy to database
    * Next steps:
        * Export from database -- handle new FeatureStore source
            * Start with GeoJSON, worry about parquet later
        * Make it easier to install as a package?
        * Clean up loose tables
* Draw tool dropdown ready
    * https://github.com/geojupyter/jupytergis/pull/1898
    * 
* Save edited layer as .geojson file on the server instead of in the user machine
    * https://github.com/geojupyter/jupytergis/pull/1894