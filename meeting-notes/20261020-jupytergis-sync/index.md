---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-10-20"
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

# JupyterGIS sync meeting (2026-10-20)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matt / `@mfisher87` / DSE
* Martin / `@martinRenou` / QuantStack


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* Trail
    * Monitor the many tools that practitioners use in their typical workflow and produce a provenance across tools to enable greater reproducibility, repeatability, and understanding when using multiple tools (some GUI-based).
    * Starting with prototyping forwarding JupyterGIS signals -> Jupyter Server event bus, and subscribing over websocket: https://github.com/geojupyter/prototype-jupytergis-eventfeed
    * Martin: https://github.com/notebook-link/metrics
    * How do we
* Maplibre viewer in https://github.com/geojupyter/jupytergis/pull/1875
    * deck.gl? :P Gains projection support in v10! Can be used in combination with MapLibre. IMO, we should have a deck.gl + MapLibre adapter -- adapters shouldn't be 1:1 with individual renderers.
        * COG support? https://developmentseed.org/deck.gl-raster/blog/multi-band-cog/
            * https://github.com/geomatico/maplibre-cog-protocol , https://maplibre.org/maplibre-gl-js/docs/examples/add-a-cog-raster-source/ ,
        * https://developmentseed.org/deck.gl-raster/examples/reprojection-explainer/
    * Need a way to add "warning" to layers -- we want to show e.g. "this layer won't display with this renderer" or "this layer is ephemeral because it's backed by an Xarray dataset in kernel memory"!
* OpenEO:
    - New example https://github.com/geojupyter/jupytergis/blob/main/examples/99-OpenEO-NDCI_venice_lagoon-Microsoft.ipynb uses the same backend (titiler-openeo) as https://studio.mpc.ds.io/
    - auth: Arjun looking into supporting OIDC
    - CORS: JupyterLab -> use our own proxy. JupyterLite -> ??. Notebook.link -> We'll provide our own.
    - tiff tiles -> to enable symbology
* GEE viz/analysis feedback loop (CNG)
    * Presented at CNG: https://github.com/geojupyter/presentation-cng2026/
    * Hypothesis: Users want GEE-like viz/analysis feedback loops. Test your computation quickly on a large dataset. GEE does this by using overviews efficiently, not by super-impressive hardware, i.e. if your map is zoomed out, do the computation on the fly on lowest-resolution data. The CNG/OSS ecosystem is almost able to do this, but we are missing some building blocks. Namely, Xarray datasets are not overview-aware, and can't do overview-aware computations. If our tile server could take a dataset that contains deferred computations backed by a COG, e.g. `ndvi = (ds["nir"] - ds["red"]) / (ds["nir"] + ds["red"])` and do e.g. `ndvi[myslice].compute(overview_level=3)`, **we could provide a GEE-like UX with only OSS tools**.
