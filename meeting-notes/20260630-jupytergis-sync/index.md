---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-06-30"
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

# JupyterGIS sync meeting (2026-06-30)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin Renou / `@martinRenou` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?


### Status reports

* jupyter-tiler extra package now in conda-forge pre-release
    * Need an extra argument to use pre-release
    * `micromamba create --name test -c conda-forge/label/jupytergis_prerelease -c conda-forge jupytergis-lite=0.16.0a4 jupytergis-tiler`
    * BUT this does not work `micromamba create --name test -c https://prefix.dev/conda-forge/label/jupytergis_prerelease -c https://prefix.dev/conda-forge jupytergis-lite=0.16.0a4 jupytergis-tiler`. Prefix doesn't mirror non-default labels.
    * <https://github.com/conda/ceps/blob/main/cep-0044.md> -- optional dependency groups coming soon!
* R JupyterGIS in GeoJupyter!
    * 3 people working on this @ QuantStack!
    * <https://github.com/geojupyter/r-jupytergis>
    * Do we keep the version numbers in sync?
        * Maybe we add another segment e.g. v0.16.0.1?
        * :white_check_mark: TODO: Open an issue in the repository (<https://github.com/geojupyter/r-jupytergis/issues/9>)
* New Story Maps editor :D
    * :star-struck: Beautiful!!!
    * Markdown editor: Working on codemirror
        * MyST?
            * Should we depend on jupyterlab-myst and render with MyST?
            * Or match JupyterLab behavior, if MyST is installed we render with it, otherwise we don't
                * Then folks who share projects need to ensure MyST is installed everywhere it's used, just like with Jupyter Notebooks
    * Previews work in another tab now!
    * Working on collaborative story editing!
* jupyter-tiler `add_stac_array_layer`
    * Goal: 0.16, but OK with punting if we are ready for 0.16 before this feature is ready.
* Ready for 0.16?
    * Matt: <https://github.com/geojupyter/jupytergis/issues/1278>
        * Matt will try to repro on latest alpha, and debug differences between my repro environment and Martin's non-repro environment.
