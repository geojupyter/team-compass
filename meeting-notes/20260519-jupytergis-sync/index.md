---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-05-19"
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

# JupyterGIS sync meeting (2026-05-19)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin Renou / `@martinrenou` / QuantStack
* Matt Fisher / `@mfisher87` / DSE
* Matthias Meschede / `@mmesch` / QuantStack
* Vincent Sarago / `@vincentsarago` / DevSeed


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* Grammar of graphics
    * PR merged!
        * Bug: When radius not set, nothing is displayed.
    * Martin: Working on Python API side! https://github.com/geojupyter/jupytergis/pull/1420
        * Expose grammar of graphics on the programmatic API! :tada:
        * Factory functions for e.g. `constant_color`
        * Can pass multiple factory functions as a list, and these are separate symbology "layers" (**we need a better name for this**!)
        * Objects with chainable methods, e.g. `constant_num(3, target=["circle-radius", "circle-stroke-width"]).color_ramp(value="mag", target="stroke", name="viridis")`
        * Race condition: sometimes symbology doesn't apply as expected.
* Matthias: Vega-lite plot rendering PoC (https://github.com/geojupyter/jupytergis/pull/1419)
    * Matt: Mixed feelings about mixed plot and map symbology in the UI! More efficient, but potentially confusing. Some icons for which mappings are plot mappings and which are map ones might be useful! (:+1: Martin)
    * Matt: What do we think this UI should look like?
        * Bottom panel right now, reusing same space as console.
        * Might be nice to use different JLab tabs
            * Should be doable if they are lumino widgets, Lab will allow drag-and-drop. Could then also generate plots in notebooks!
            * Can use similar approach for attribute tables
        * Floating might also be nice!
        * Ability to name plots!
    * Testing symbology with OpenLayers
        * Matt: Snapshot testing? Or?
* OpenEO support 
    * Available from the Python API on `main` https://github.com/geojupyter/jupytergis/pull/1287
    * UI Components to edit the OpenEO layer in progress https://github.com/geojupyter/jupytergis/pull/1409 
* GeoZarr support in progress https://github.com/geojupyter/jupytergis/pull/1400
    * Remains to get the symbology to work with it (needs to get the bands info from the zarr file lazily) :100: