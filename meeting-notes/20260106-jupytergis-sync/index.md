---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a core meeting!
date: "2026-01-06"
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

# JupyterGIS sync meeting (2026-01-06)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt / `@mfisher87`
* Martin / `@martinrenou`


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Status reports

* Matt: Something like JupyterGIS-tiler but not coupled with JupyterGIS. I.e. `jupyter-xarray-tiler` component anyone can use to tile xarray datasets and display them in any map thingy
    * Martin: Add as dependency of and integrate with ipyleaflet!
    * Martin: Don't bind to titler? E.g. `jupyter-xarray-tiler[titiler]` / `jupyter-xarray-tiler[xpublish]`
        * Or even further, not only bound to xarray? What about geoparquet data? GeoDataFrames?
        * See: <https://www.linkedin.com/posts/kanahiro-iguchi_foss4g-duckdb-ugcPost-7403315764348280834-8y5R/?utm_source=share&utm_medium=member_android&rcm=ACoAAA7c8FABpLSJeNgcYB0C36JOi9aLGMOZzQg> The associated tool https://github.com/Kanahiro/yosegi
    * See <https://github.com/xarray-contrib/xarray_leaflet>
* QuantStack expects significantly more time for JupyterGIS coming soon! Not sure exactly when yet, likely this year :)
* Strategy meeting with Matt, Martin, Fernando, Sylvain, Matthias!



### Action items:

* Martin: Send Matt Matthias' email
* Matt: Email David, Martin, Sylvain, Matthias about meeting to discuss a component for Jupyter to dynamically tile geospatial datasets in Python objects. (i.e. JupyterGIS-tiler but independent)
* Matt: Schedule strategy meeting with Matt, Martin, Fernando, Sylvain, Matthias!


### For next week

* STAC browser
* GSOC?


### Requests for help or feedback

* Help request
* Help request
* Help request
