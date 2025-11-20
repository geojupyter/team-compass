---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2025-11-18"
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

# JupyterGIS sync meeting (2025-11-18)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin / `@martinRenou` / QuantStack
* Matt / `@mfisher87` / affiliation

## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* STAC
    * DSE interns:
        * Develop a generic set of components in parallel to the QuantStack catalog-specific components. Display generic components or specific components depending on selected catalog.
            * Should the catalog selector dialog use Widget or React component?
        * New QuantStack catalog: hydroweb
* Commands w/ arguments (Arjun)
    * Provides the ability for LLMs to interact with the shared document, e.g. allow the LLM to create a layer directly without UI interaction
    * PR: https://github.com/geojupyter/jupytergis/pull/969
* Greg storymaps
    * Demo
    * Reusing Marker functionality for landmarks
    * Landmarks are layers technically, but for the user they're different things
    * Scroll through the story? "Scrollytelling" experience.
