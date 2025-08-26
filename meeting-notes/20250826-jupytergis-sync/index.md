---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2025-08-26"
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

# JupyterGIS sync meeting (2025-08-26)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_
*


### Status reports

* Matt: Reviewing LOTS of PRs
* QuantStack: Discussing ESA "Call for Ideas".
* Matt: TODO - Review https://github.com/geojupyter/jupytergis/pull/880
* Arjun: Vector Legends PR by Arjun https://github.com/geojupyter/jupytergis/pull/880
* Arjun: Auto-focus the identify tab once your start identifying by Arjun https://github.com/geojupyter/jupytergis/pull/900
    * **Matt: Review**!
* Arjun: Add settings for disabling some features (in progress) https://github.com/geojupyter/jupytergis/pull/898
* Should we ask contributors to disclose use of LLMs? Let's wait until we're getting too many PRs and need to use it in prioritization decisions.
* Rework panels?
    * One panel that changes based on context? E.g. when identifying, switch panel. Previous button to return to where you were before. Clicking a layer in the list switches to object properties.
        * Identify could become a button on the layer, next to the eyeball button?
        * Annotation could become a mode in the toolbar like identify
        * Object properties could become a right-click context menu button.
        * Should there be a "home" button that always goes to the layer menu? Or use a "layers" icon (see Google maps lower left)
    * Multiple panel modes? Single panel mode, double panel mode, 0 panel mode?
    * Home button could be https://fontawesome.com/icons/layer-group?f=classic&s=solid in the top-left corner to come back to the layer list
* Skipped reviewing project board for today -- let's do it next week!
