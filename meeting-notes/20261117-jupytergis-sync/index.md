---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-11-17"
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

# JupyterGIS sync meeting (2026-11-17)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt / `@mfisher87` / DSE
* Martin / @martinRenou / QuantStack
* Greg / `@gjmooney` / QuantStack
* Name / GitHub ID / affiliation


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_
* jupyter-tiler stac tiler PR ready for review https://github.com/geojupyter/jupyter-tiler/pull/72
    * Filtering -- fully custom filter predicate? pre-post-process? Or build that in to the process callback (return None to filter out)
        * Balanced approach where we offer custom filter predicate and allow the user to import some common ones like nodata filter? (`filter_predicate=jupytergis.predicate.max_nodata(0.2)`)
* Notebook Link: https://notebook.link/@martinRenou/jupytergis-openeo-gallery
  * https://github.com/geojupyter/openeo-gallery/
* schema version bump, when?
    * Editing schema for the deckgl PR! 
* linter/formatter benchmarked
    * https://github.com/geojupyter/jupytergis/issues/1999
    * oxc more drop-in compatible (no naming convention rule yet)
    * We have a lot of type-aware linting rules that are enabled but doing nothing because our stuff is out of date
    * Typescript 6 upgrade reveals lots of new errors!
    * Can upgrade to TS7, but api not stable. We should upgrade now anyway!
* deck gl pr
    * Yay!
* Schema/UI coupling
    * Greg: It's gotta go! Schema should be for validation, not UI concerns.
        * Matt: Mixed feelings. See advantages/disadvantages to both. In past, considered adding context to the schema to help with form generation -- decouple more from rjsf, have more roll-our-own form generation
    * How do we test that the UI is in sync with the schema?
        * Form registry? Each form is tested with some mock data against the schema.
    * How do we lower the burden of UI development? (We have a component library, but do we need more helpers?)
    * Redundancy has a developer experience cost, are we OK with that?
    * Greg: The Python type generation is a huge problem because it's not always compatible with JS type generation! But JS type generation is multiple major versions old.
* General problem: Ecosystem moving faster than we can keep up!