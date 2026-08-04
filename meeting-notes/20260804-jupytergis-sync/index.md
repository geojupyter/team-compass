---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-08-04"
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

# JupyterGIS sync meeting (2026-08-04)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Greg / GitHub ID / affiliation
* Matt / `@mfisher87` / Schmidt DSE
* Benjamin Szeghy / `benjaminszeghy` / Schmidt DSE


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* Previewing playwright diffs in GitHub PR comment
    * Architecture: Store images in repo vs some hosted location?
    * Greg: This isn't important info, doesn't matter if we lose it, no security implications.
    * Matt: Top concern is complexity!
    * Simplify to one orphan branch per PR?
* Draw feature:
    * ESA wants collaborative labeling!
    * Want to support automatically saving "last editor" for example
    * Want to support a large number of features for use cases like crater counting, tree counting.
    * Sidecar file to store huge dataset, dynamically load subset? When collaboratively editing, use a JSON file as the ydoc target, and every N records, sync back to the sidecar file.
    * Data format? flatgeobuf, geoparquet? 
    * We need some way to write to a optimized binary format both in JupyterLab serverful context and JupyterLite serverless context. DuckDB-WASM?
    * Funding opportunity to develop new low-level geospatial technology like "icechunk for vectors"?
* replace CMDK as a dependency?
    * Greg: We're using ShadCN UI components, but they don't work out of the box with Jupyter, so we use its components directly (which includes CMDK and RadixUI). BaseUI feels like what we should be using, this might be an excuse to switch. 
        * We should be able to do a piecemeal migration. Cost to migrate should be low! Should be able to open a PR tomorrow.
        * Let's start with `Select.tsx`!
        * Select and ComboBox should be different things!