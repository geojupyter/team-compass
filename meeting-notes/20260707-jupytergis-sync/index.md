---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-07-07"
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

# JupyterGIS sync meeting (2026-07-07)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Greg Mooney / `@gjmooney` / QuantStack 
* Martin Renou / `@martinRenou` / QuantStack
* Benjamin Szeghy / `@benjaminszeghy` / Schmidt DSE
* /


## Agenda

* Review our [project board](https://github.com/orgs/geojupyter/projects/2)
  * What items should be added?
  * Are there stale items that are no longer urgent?
  * Are there things we can change about the project board to make it more useful? Add more information? Remove steps?
* [GPS location indicator PR](https://github.com/geojupyter/jupytergis/pull/1541)
    * Should coordinates updates travel through a Signal on the model? Or use local-only OpenLayers event listener (`geolocation.on('change', () => {...})`)? (https://openlayers.org/en/latest/examples/geolocation.html)
        * Matt: Leaning towards local-only approach (don't need to support)
        * Martin: If we eventually want to share location with collaborators, we could use the awareness.
* Draw + data: Greg is working on it!
* Global mode display in the status bar?
    * Mode is mutually exclusive and we can use it to determine if mode buttons are toggled.
    * We like this idea!
    * Group these in the toolbar? Dropdown?
    * TODO: Open an issue
* Python expressions support in symbology :rocket:
    * Currently we show the expression in the legend
        * Matt: I think we should have a graphical legend, it will serve to verify the user's Python expression and be consistent with other layers
            * Right now we'd need to be able to generate a legend from OL style expression to do this :grimacing:
    * Currently we transpile (python ->) vega -> OL
    * Matt: This approach couples us to OpenLayers. I have a (perhaps very bad) idea: what if we transpile to our Grammar of Graphics schema instead of OL? Then we can use our existing code to transpile GoG -> OL, and GoG -> graphical legend! (Then we also have 3 transpile steps :laughing:)
        * This is probably really hard; our GoG schema may not / doesn't support all the stuff that can be expressed in Vega/Python.
        * Maybe this means we should seek out improvements to our GoG schema, or adopt an existing GoG schema as our internal representation.
        * Our GoG schema would be the limiting factor of what can be expressed in Python/Vega, not OL. But GoG schema would necessarily be limited by what the renderer can express, too. Oof!


### Requests for help or feedback

* Review [`add_stac_array_layer` method](https://github.com/geojupyter/jupyter-tiler/pull/72)
    * Should the array_to_image function argument instead return a data array that can be color mapped? I.e. call it `preprocess`?
        * Martin: Yes, and we could also have a postprocess, mutually exclusive with colormap settings, that can let the user fully control the returned imagery!