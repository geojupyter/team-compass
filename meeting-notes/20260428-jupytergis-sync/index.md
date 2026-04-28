---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-04-28"
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

# JupyterGIS sync meeting (2026-04-28)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Greg / `@gjmooney` / QuantStack
* Martin / `@martinrenou` / QuantStack
* Matt / `@mfisher87` / DSE
* Benny / `@benjaminszeghy` / Berkeley


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* JupyterGIS & AI
    * https://github.com/geojupyter/jupyter-geoagent
    * https://github.com/geojupyter/jupytergis/pull/969
        * Previously our commands just spawned dialogs, but didn't actually create layers. This PR added commands to use those same commands programmatically.
        * Works with JupyterLite-AI or Jupyter-AI
        * JupyterLite-AI doesn't require Jupyter-AI!
        * There's also [NotebookIntelligence](https://github.com/notebook-intelligence/notebook-intelligence)! There are 3 different things! Probably more.
    * Martin: Biggest worry is depending on Jupyter-AI too much -- don't want to restrict deployments to Lab only.
* WebGlLayer -> rename GeoTiffLayer
* VectorLayer -> VectorImageLayer PR: https://github.com/geojupyter/jupytergis/pull/1316
    * Faster, but worse label rendering (we don't render labels!)
    * https://openlayers.org/en/latest/apidoc/module-ol_layer_VectorImage-VectorImageLayer.html
* Benny: Geoprocessing toolbox. Let's chat at the community meeting!
* Martin: Vega expression PR! Let's chat at the community meeting. Want Matthias to be involved.
    * Matt: Want to work on this with Matthias! Start a thread in GeoJupyter Zulip and `@` Benny, Matthias, Martin, Greg
* TiTiler: Martin and Matt to chat! Can wait 2 weeks.
* Matt: Send info about meeting notes setup to Martin for next week.


### Requests for help or feedback

* Help request
* Help request
* Help request
