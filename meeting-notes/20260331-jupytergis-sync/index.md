---
title: "JupyterGIS sync meeting"
description: |
  A weekly gathering of JupyterGIS team to discuss our progress and help each other out.
  Open to all, but this meeting is _short_ and task-focused, so there will not be time
  for introductions. Please join a community meeting!
date: "2026-03-31"
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

# JupyterGIS sync meeting (2026-03-31)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Google Meet](https://meet.google.com/zhk-vygf-gke)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)


## Attendees

Your name / GitHub ID / affiliation

* Matthias Meschede / @mmesch / QuantStack
* Arjun Verma / `@arjxn-py` / QuantStack
* Matt Fisher / `@mfisher87` / Schmidt DSE
* Martin Renou / `@martinRenou` / QuantStack
* Guillaume Eynard-Bontemps / `@guillaumeeb` / CNES
* Greg Mooney / `@gjmooney` / QuantStack
*
*  /


### Action items

- [ ] Matt: Email vincent to see if he can join next week! Continue discussion to help Matt figure out where he can collab.


### Agenda

* Greg: Demo his current POC of:
  - selecting a STAC item in JupyterGIS
  - get the selection Python-side, process it with xarray (NDWI)
  - serve tile layers for the item
  - :tada: :clap:
  - Matt: How can we make this reproducible? See interns work on map2cell/gui2cell user experience! (https://github.com/geojupyter/prototype-map2cell-ipyopenlayers)

* How can we maximize the impact of CNES grant funding?
    * Matt: Available to shift priorities and focus only on JGIS if we can identify alignment in impacts we @ DSE see as important in the short-term. I'll need to articulate the impact to other DSE-side decision-makers.
        * We want to focus on making JupyterGIS a powerful alternative to the big players for a specific use case and increase the user base.
        * We're most interested in how we can enhance Notebook+JGIS workflows to be more polished and steer researchers towards reproducibility-by-default.
        * Architectural improvements and targeted features in the Python API, plus functionality that improves bi-directional data flow between Python and the map, are the strongest cases IMO. I think there's strong alignment with the grant here.
        * A possible failure mode looks like the "schema overhaul" I started a long way back -- architectural changes happening without clear strategy alignment and co-development with the core team. IMO success will require challenging assumptions, building a clear vision, coordinating our efforts, and moving fast together.
        * During a sprint, I can alter my work schedule to create more overlap, e.g. supporting more synchronous meetings, pair programming, whatever.
- CNES grant goals
    - CNES: Open source GEE. JupyterGIS as part of that!
        - Needs to generate an Xarray from STAC catalog from every item that's in the viewport / region of interest
        - E.g. `doc.get_viewport_bounds` combined with `doc.get_stac_selection_as_dataset`? `doc.get_all_stac_items`? And event handling`doc.on_viewport_changed(callback)`. Need to handle multi-users case.
        - Get a Xarray dataset on the Notebook side from many stac items
        - Want to also be able to build the Xarray from Python side
        - Wants to lazily do the deferred computation for only the tiles that are in the viewport. Can we use the TiTiler Algorithm mechanism to dynamically apply a deferred Xarray computation? I.e. the user doesn't have to know about the TiTiler Algorithm mechanism, they write an Xarray computation only, and this happens under the hood.
        - **For CNES' goals, only the visualization matters, everything happens in Python -- maybe for this particular goal of the grant, the work happens in jupyter-xarray-tiler to enable the dynamic viz they're looking for.**
    - CNES: Python API? Just the above?
        - Being able to reproducibly move information (STAC item/catalog selection, shapes) sounds really cool. There's some freedom to spend down the grant on these functionalities, but the bullet above is the primary goal.
    - CNES: OpenEO layers. Transient layer that could become non-transient.

* Matthias:
    * mobile bottom sheet: demo proof of concepts for:
        * [bottom sheet](https://github.com/geojupyter/jupytergis/pull/1216), and
            * Bottom "panel" instead of side panels
            * Familiar "drawer" panel for mobile
            * Already used by story maps? Need to make sure these work well together.
        * related [double panel toggle](https://github.com/geojupyter/jupytergis/pull/1214),
            * Interactively toggle the panels from the toolbar
        * [multi panel toggle](https://github.com/geojupyter/jupytergis/pull/1215).
        * Explain architecture implications. Find consensus.
            * Folks like 1216 the best! (Martin, Arjun)
        * Martin & Matt: Skeptical about the mobile use case, but supporting narrow windows, e.g. when demoing collab, is valuable!
        * Explain architecture implications.
        * Break down in small steps:
            * introduce data model / schema and move existing types to this.
            * then add UI
        * Find consensus.
    * generic "grammar of graphics" symbology: demo [proof of concept](https://github.com/geojupyter/jupytergis/pull/1221).
        * **Consensus this is the way to go forward**
        * Matt :100: :100: :100:
            * Let's extract this to an independent component that can render to many formats, e.g. vega-lite, cartoCSS, ol style expression, etc?
                * Package schema, converters, tests, etc. in separate repo
                * Martin: Unclear this is good -- Matt and Martin to explore the details offline
            * Schema stuff -- how do we ensure the schema is "obeyed"? We currently don't
            * Some default style "templates" for common use cases
                * Save users time!
                * Enable less experiences users to engage with a more complex interface
        * Martin: Do we want to get rid of other types?
            * Matt: Need to keep heatmap!
            * Considering adopting vega for non-map viz, if this interface can output vega-lite grammar, that would be amazing
            * With Nakul: Conditional rendering. OL supports it, but it's not great. E.g. if mag > 2, red, otherwise colormap. The OL style expression is _very_ hard to read. Vega expressions are JS expressions, easier to read, and supports more advanced behaviors. Can we write an adapter from vega-expression -> vega parser -> JupyterGIS grammar schema -> Open Layers style? There's a parser that can convert expressions -> AST, and we can do AST -> JupyterGIS grammar schema.
                * Matthias: The schema that the new "grammar" UI defines can be compiled to different representations.
        * Matthias: Be open to the schema evolving as we continue working, don't get hung up on making it perfect. Be humble, rely on prior art.
        * Matthias: Next (bonus) steps for data model (start simple):
            * Are branching and merging. E.g.
                * branching: one style expression -> multiple visual **encodings**
                * merging: Build RGBA color output from multiple input fields.
                * This is potentially a complexity trap! **Where do we draw the lines around the visual editor and require users to write code to express really complex symbology**
            * Filters! (and, or)
        * Martin: OL style expressions "leaking" into our schema. Instead store the generic repr in the document, and write adapter to dynamically generate renderer-specific expressions.
            * Matt: :100: We may switch to DeckGL sometime! We should be building our project schema to be generic and adapt that generic data structure to implementation details e.g. renderer. We'll also want to adapt these style expressions to e.g. plotly plots in the future.
            * Martin: note: OL style expressions leaking may have been introduced to be able to export styles to QGIS Python side? We need to be careful with this.
        * VectorTiles?
            * E.g. PMTiles has "layers within layers"
                * PMTiles can also serve raster!
            * Matthias: Same PMTiles layer multiple times, use filters to keep the UI simple?
