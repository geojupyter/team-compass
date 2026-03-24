---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-03-24"
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

# JupyterGIS sync meeting (2026-03-24)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Martin Renou / `@martinrenou` / QuantStack


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* GeoPackage PR
    * Arjun picking it back up
    * Struggling with some WASM stuff
    * GeoPackage dependencies depend on a WASM build of SQLite
    * One of the deps uses a fork! :X Just forked to add a compilation flag (add R\*tree feature). But this means we have 2 WASM runtimes for SQLite.
    * Can we lazy-load the WASM files?
    * Merge the PR and track in an issue.
* Projection in project file is ignored https://github.com/geojupyter/jupytergis/pull/1189
    * Separately, still need a way to change projection in the GUI!
* Nakul moved filters to symbology panel
* File icon fix! :tada: Not sure who John is, but thank you John!
* model vs sharedModel
    * Martin: From JupyterLab. Might be against renaming it!
    * Martin: Would be OK with getting rid of the thin wrappers on `model`
    * Martin: Make sharedModel hidden / private?
    * Martin: sharedModel is lower level stuff -- directly make changes on ydoc. That's why I think I think it should be hidden and `model` acts as a higher level interface.
    * We can test:
        * Can we change the name of sharedModel, does it break anything?
        * Can we make sharedModel private, does it break anything?