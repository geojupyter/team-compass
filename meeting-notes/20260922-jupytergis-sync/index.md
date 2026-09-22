---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-09-22"
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

# JupyterGIS sync meeting (2026-09-22)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / DSE
* Greg Mooney / `@gjmooney` / QuantStack
* Martin RENOU / `@martinRenou` / QuantStack


## Action items

- [x] Open issue to track "right click menus are unintuitive for users with specific expectations about right click in the browser"
    - https://github.com/geojupyter/jupytergis/issues/1886
- [ ] Merge swipe PR and release through conda-forge. Update CNG docker image with new version!
- [ ] Matt: Do research on mapadapter state duplication, open issue for "set the state on the mainView and some general mechanism passes that state down into the map adapter; i.e. no manually setting state on the map adapter." `@` Greg & Martin & Arjun & Nakul!


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_
* CNG coming up soon! (October 6). Presentation WIP: https://github.com/geojupyter/presentation-cng2026/
    * Arjun developed swipe comparison feature! Release?
        * Looking forward to timeline feature? How to make the UX reasonable?
        * Next iteration of swipe UX: Layer groups as the mechanism for comparison, or in the future, blending (set the group's mode to compare/blend/whatever)
    * Typo in Notebook: "...with the ndvi DataArray we just calculated!" -> NDSI
* Collaboration UX improvements
    * Pointer component extracted to jupyter-collab, shared between CAD and GIS: https://github.com/geojupyter/jupytergis/pull/1871
    * https://codimensional.com <-- not Jupyter, but reminiscent of JupyterCAD
* Nakul exploring Maplibre viewer
    * Working with simple layers!
    * Matt: State duplication? https://github.com/geojupyter/jupytergis/pull/1873#discussion_r4066127759
    * Matt: Interested in scoping out d3-geo for cartography use cases