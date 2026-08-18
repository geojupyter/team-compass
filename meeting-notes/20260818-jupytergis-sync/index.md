---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-08-18"
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

# JupyterGIS sync meeting (2026-08-18)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_
* Combobox!
    * Matt: Merge
    * Matt: Create an issue to consolidate the two Button components!
* Tailwind
    * Greg: Will start going through other components and Tailwind-ifying them!
* Snapshot testing workflow
    * With the repo-based approach, we get a commit thank links to the PR, e.g. https://github.com/geojupyter/jupytergis/commit/ae0c3c03fd52ccf42472d970178ad10ba7c8697f
    * Greg: Currently no comment is posted when the integration tests fail for a reason other than snapshot difference. Easy to assume everything is good if no comment
    * Consider the inline playwright report action? Less work for us, and there's still an opportunity to improve and upstream a bot comment action. Bot will comment a test report even for non-snapshot failures. Greg, Matt: +1