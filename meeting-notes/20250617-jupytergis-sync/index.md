---
title: "JupyterGIS sync meeting 2025-06-17"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2025-06-17"
image: "../images/standup.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "JupyterGIS notes"
tags: [jupytergis-notes]
---

:::info {.callout-info}
:mag: This meeting is _short_ and _task-focused_. Unfortunately, we won't have time to
introduce every new person to the team. Please attend core community meetings ([see
GeoJupyter calendar](https://geojupyter.org/calendar)) to meet the team and add your own
agenda items, and/or
[introduce yourself on Zulip](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter/topic/Welcome)!
:::

# JupyterGIS sync meeting 2025-06-17

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=4pm)
- [Previous meetings](https://geojupyter.org/blog/#category=JupyterGIS%20notes)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / \@mfisher / Schmidt DSE
* Martin Renou / \@martinRenou / QuantStack
* Greg Mooney / \@gjmooney / QuantStack
* Name / GitHub ID / affiliation


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* Processing refactor: https://github.com/geojupyter/jupytergis/pull/758
    * Do we want to include the data which drives generating the processing code in the JSONSchema? Matt: Doesn't feel right to combine these responsibilities in one place.
    * If we extract to TypeScript, how to dynamically generate types, e.g. the various processingIds? If each file has a ProcessingID variable, how do we union those?
    * What about separating the data part of the schemas into separate JSON files that are checked by a schema? Validate at build-time.
