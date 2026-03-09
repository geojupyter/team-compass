---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2026-02-24"
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

# JupyterGIS sync meeting (2026-02-24)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin Renou / @martinRenou / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* jupyter-xarray-tiler
    * Thinking about handling n-dim Datasets, not DataArrays
    * How do we help the user with exploring the dimensions of a DataArray?
        * How do we make this interface modular? E.g. do exploration as a first step, then map the data you've selected from the data array, instead of integrating an exploration experience into ipyleaflet/leafmap?
        * How do we make the interface reproducible? E.g. do we generate code and auto-create a new cell that does the operation the user did in the widget UI?
    * Talk to Qiusheng?
        * Lots of interfaces for exploring data in widgets, but not generating code for reproducibility yet!
    * https://github.com/jtpio/ipylab
        * Only way to create new cells from Python. Exposes commands to Python.
        * Do we need to do this from Python? We could do it from a widget.
            * Martin: Cleaner this way! More conventional, Jupyterish approach.
    * https://anywidget.dev/
        * Small problem: Can't create a container widget (Widget that contains widgets). This is a common pattern e.g. in bqplot, the figure is a widget, which contains an axis widget. ipyleaflet map is a widget, each layer is a widget. This is not possible with Anywidget. 
    * 
* Status
* Status


### Requests for help or feedback

* Help request
* Help request
* Help request
