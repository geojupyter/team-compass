---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-08-25"
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

# JupyterGIS sync meeting (2026-08-25)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Benjamin Szeghy / benjaminszeghy / schmidt DSE
* Martin Renou / martinRenou / QuantStack
* Arjun Verma / `@arjxn-py` / QuantStack
* Matt / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack
* Matthias / @mmesch / QuantStack


## Agenda & notes

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* Citation / DOI
    * Arjun, Matt, Benny: We should keep the current contributor citations!
* JupyterGIS release!! https://notebook.link/@martinRenou/jupytergis-announcement
* Symbology UI
    * Change order of mappings to right-to-left? I.e. fill color = blue; pixel color = viridis = magnitude.
        * Toggleable?
    * Can we change the opacity of features independently from the color for vector layers? For raster we can, by having one mapping to pixel-color and one to pixel-alpha. For vector we probably can't?
        * Matt: We have fill-color but not fill-alpha
        * Martin: Let's track that in an issue
    * Renaming layers/mappings: https://github.com/geojupyter/jupytergis/issues/1479
        * We still need to make a decision
            * Some transformations are pushed to the renderer, others are static operations on the data (processing).
* Flaky test
    * replace arbitrary waits from the snapshot tests
        * Benny: I'm working on a pr that targets the flakiness of the france-hiking snapshot tests
        * example of a test fail caused by another arbitrary wait (someone else may have to work on this)
            * https://github.com/geojupyter/jupytergis/actions/runs/32706175238/job/97368788452?pr=1781
            * Benny: Will open an issue!
    * How can we avoid testing openlayers and 3rd party tile services?
        * How can we select the map object from the global JS context in playwright?
        * We could mock STAC JSON and image tiles?
        * We could run mock tile server and HTTP server for STAC?
        * Generate image tiles deterministically during tests so we don't have to store them?
        * Static GH Pages site with tiles named to match XYZ tile service queries?
* Nakul's renderer switcher ui
    * https://github.com/geojupyter/jupytergis/pull/1770
    * Benny: I would really like to see D3-geo added (+1 Martin)
        * Benny: "Best projection support hands down"
        * Martin: bqplot uses d3-geo
        * Benny: can render to SVG out of the box, gives us the ability to export in a way that fits existing cartography workflows (Adobe Illustrator)
        * Benny: Open an issue!
    * Matt: Open an issue for educational tooling around map viewer choices.
    * Matt: Post on this PR about considering a React component vs an interface
* Arjun gave a small demo on Metadata Viewer - https://github.com/geojupyter/jupytergis/pull/1796
    * Martin: Neat. We should probably remove the source name entry from there "Custom GeoJSON source" is generic and not user-configurable
    * Matt: Beautiful!
        * Information -> Metadata
        * Display extent as table
        * Move CRS help-text ("What is a CRS? Learn more...") into info tip!
    * Benny: Where do the projection names / proj 4 strings come from?
        * proj4-list! Switching over to proj-codes
* Matt: Post issue for sharing info between JS app and documentation on Zulip
* Matt: Ask Clancy Wilmott about symbology terminology!
