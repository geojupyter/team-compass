---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-04-07"
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

# JupyterGIS sync meeting (2026-04-07)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matthias Meschede / `@MMesch` / affiliation
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Vincent Sarago / `@vincentsarago` / DevelopmentSeed
* Martin Renou / `@martinRenou` / QuantStack
* Benjamin Szeghy / `@benjaminszeghy` / UC Berkeley


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* _Please add more items if you have them!_


### Action items

- [ ] Xarray computation -> band expression translator -- how does Xarray store deferred computations internally?
- [ ] Can Xarray computations be deferred to implicitly occur at read-time without calling `.compute()`
- [ ] Can we know in advance whether an Xarray computation is "embarassingly parallel"?


### Notes

* Last time: https://compass.geojupyter.org/meeting-notes/20260331-jupytergis-sync/
* Xarray computation rendered with TiTiler
    * Use Algorithm mechanism?
        * Vincent: Possible; may not be best way
        * Have to read data to merge datasets to create a specific tile first, then algorithm is applied after the band information is lost
        * You might actually want the algorithm to be earlier in the pipeline! There are ways to work around this. Maybe use BandExpression instead?
        * A new feature flag (lazy reading) is not appropriate for TiTiler. This is why titiler-openeo exists. And https://github.com/EOPF-Explorer/titiler-eopf also supports complex processing for each tile.
        * OpenEO: This feels like the better route to go.
        * Can we approach the simplicity of an Xarray-native workflow with OpenEO pipelines?
    * Can TiTiler handle large number of items in an Xarray dataset?
        * Requires downloading the data to the system
        * https://developmentseed.org/titiler-stacapi/
            * Can viz from search parameters
            * Can also do the computation step!
                * Done as part of request as a band math expression
            * Does not support xarray (yet?)
            * Band math happens **after** resampling the data for the viewport resolution
                * Of course easier with datasets with overlays. COG / Zarr multiscale. Zarr multiscale spec still evolving and lacking tool support. Maybe zarritajs supports this?
                * 1.0 release of GeoZarr coming soon? 2026?
            * Xarray computation -> band expression translator?
                * **We should explore this!**
        * Vincent: In TiTiler-xarray you give it a Zarr path, tell it which variable to view. TiTiler open the dataset, selects a variable. When selecting a variable, you could apply a deferred computation on a dataArray, then pass it to riotiler. If you could tell xarray to do that computation at read-time, we could pass riotiler the dataarray with the deferred computation.
* Matthias' grammar of graphics work
    * Martin: Asked Nakul to start looking in to symbology expressions
        * I.e. function part in the middle of a grammar entry could be a vega expression, and we could parse to AST and translate out to openlayers (or other) style expression
        * Matt: Should this be a separate project?
            * Martin: Yes! `vega2ol`? `vega-babel`? For now, sticking with openlayers so let's not spend too much time on the name :)
            * Martin: vega's expressions parse to ESTree https://github.com/estree/estree
            * Matthias: Want to work towards a more general to translate vega expressions to multiple representations.
                * General means:
                    * Support multiple output languages (OpenLayers style expression, CartoCSS, ??)
                    * Martin: What about supporting an additional input language?
    * Matthias: Break in to small pieces first, do PRs step-by-step
* Matthias: Mobile view with bottom "drawer"
    * Should be ready very soon. Advancing quickly!
    * Moving to symbology next
* Matthias: AI writing a story map! Ask JupyterAI to guide user through a map with story map functionality. "Write me a tour through the geology of the world" with MacroStrat
        * Vector Symbology was a challenge
* Arjun: Working on removing output repr from project file
    * What if the user edits a single color stop? Need to save that.
    * Only save color stop information if the user overrides stuff. Custom flag in symbology schema, boolean, to say if color stops were altered. In which case we save the color stops.