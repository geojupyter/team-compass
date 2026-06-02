---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-06-02"
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

# JupyterGIS sync meeting (2026-06-02)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Martin Renou / `@martinRenou` / QuantStack
* Greg Mooney / `@gjmooney` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Matthias Meschede / `@mmesch` / QuantStack
* Vincent Sarago / `@vincentsarago` / Developmentseed

## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add
    more information? Remove steps?
* Matthias:
    * Docs PR. Proposal on how to move forward with image gallery. Merge?
    * Compressing / optimizing images for our repo
        * Git LFS is not useful because it has a 10GB/repo/month storage/bandwidth limit. Only time it's useful is if you do a full clone. Just an extra hassle.
        * When reducing image dimensions, the docs look poor.
        * Conclusion: Stay with full dimensions for gallery. Compress as JPEG. If doing a snapshot test on these images, need to increase tolerance for comparison. Think we can get this stable.
    * Release? What to do for it?
        * Matt: Our default docs page is "latest" so we don't need to release for people to see it right away! (I don't know if this is "right" for our project, it's a tradeoff :X)
        * Martin: Don't feel confident releasing right now! Want to fix QGIS opening, merge Python symbology API.
        * Matthias: Can we move towards more incremental releases / "beta" releases?
            * Martin: This doesn't feel like too much work!
            * Martin: Will open an issue!
* Merging @Greg's blog story PR https://github.com/geojupyter/jupytergis/pull/1455 . Decide on a name: "Blog"/"vertical scroll", how does it differ from the "guided" mode?
    * Guided is left-right navigation with map as the main interface
    * New interface is more article-like
    * Matt: "Scrollytelling"? "Blog" doesn't feel right. "Article" is closer.
    * "Vertical scroll" most descriptive
* Merging @Arjun's OpenEO PR https://github.com/geojupyter/jupytergis/pull/1409 -- ready to go! Needs final review.
* Merging @Nakul's GeoZarr PR https://github.com/geojupyter/jupytergis/pull/1400 -- :tada: In draft, mostly ready. Needs final review. [Can open some GeoZarrs, but not others](https://github.com/geojupyter/jupytergis/pull/1400#issuecomment-4603889001).
    * Vincent: GeoZarr still in flux, spec not fully mature. Looking at it and shared with DevSeed team. GeoZarrs in the wild can differ, so expected that some files don't work. The spec doesn't include a geozarr version in the metadata, so we can't reasonably tell the user what went wrong.
        * Vincent: https://github.com/zarr-developers/geozarr-spec/issues/102
        * Martin: For now, just give a vague error that's visible to the user.
        * Matthias: Need a common feature for reporting errors nicely to users.
* jupyter-tiler!
* Data management, how do we get data to Python/R/other kernels?
    * In JupyterLite, kernel can access the browser cache
    * GeoParquet with spatial indexes proposal: https://github.com/Kanahiro/cloud-optimized-geoparquet
        * QuantStack Parquet/Arrow folks unsure about this proposal.
* Qiusheng making an in-browser GIS thing! https://geolibre.app/demo/
