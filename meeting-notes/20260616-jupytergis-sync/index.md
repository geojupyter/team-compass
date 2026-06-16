---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-06-16"
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

# JupyterGIS sync meeting (2026-06-16)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / affiliation
* Martin Renou / `@martinrenou` / affiliation
* Benjamin Szeghy / `@benjaminszeghy` / Schmidt DSE
* Name / GitHub ID / affiliation

## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* Conda Forge
    * We think we know what's wrong with the xpublish-tiles recipe
        * https://github.com/conda-forge/staged-recipes/pull/33446#issuecomment-4720473710
* GUI reproducibility! Export a drawn shape to code
    * is #471 overlapping with #1525
        * Matt: Let's make 1525 specific to code snippets to use a layer's data in code
    * Martin: Greg has exposed the document awareness to the Python API. We could e.g. `doc.bbox` for a drawn feature in the current awareness. Not reproducible, but interactive. Maybe we offer a method like `doc.bbox.get_reproducible()` that generates an HTML repr with code the user can copy for reproducibility. How useful is this actually? Would `.get_reproducible()` just be a wrapper around a shapely/fiona `.to_geojson()` (https://shapely.readthedocs.io/en/2.1.2/reference/shapely.to_geojson.html) call?
    * Consider two tabs? An "interactive" tab that shows you how to get the data from live project state, and "reproducible" tab that shows you how to get the source data as a reproducible snippet that's not linked to project state.
        * Reminds me of jdaviz "api hint" functionality
* Grammar of Graphics Python PR! :D https://github.com/geojupyter/jupytergis/pull/1420
    * Flaky snapshot tests!
        * May be caused by a [race condition](https://github.com/geojupyter/jupytergis/issues/1481).
        * Considering an async approach, but **it may break compatibility with ipykernel**!!!
            * ipykernel will block on the kind of async we want to do: https://notebook.link/@DerThorsten/async-xeus-python
            * Would need to switch to xeus-python
            * Should be no negative tradeoffs to this switch
            * Martin: We shouldn't break compatibility, but we should give a warning.

### Requests for help or feedback

* Matt: _Review Python API grammar of graphics PR!_
