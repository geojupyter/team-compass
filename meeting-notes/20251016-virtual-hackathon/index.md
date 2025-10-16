---
title: "GeoJupyter virtual hackathon"
description: |
  A GeoJupyter virtual hackathon. Open to all!
date: "2025-10-16"
image: "../images/hackathon.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Hackathons"
tags: [hackathons]
---

# GeoJupyter virtual hackathon (2025-10-16)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/92451699568)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=2pm)
- [Notes from previous hackathons](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Sign in!

Your name / GitHub ID / affiliation / icebreaker

* Matt / `@mfisher87` / DSE
* Stefan / `@stefanv` / BIDS
* Maryam / `@Mary-h86` / BIDS

## Agenda & notes

### ⚡ (5 minutes) Lightning intros

Tell us about you in 30 seconds or less!


### 🌐 (5 minutes) Lightning demo

What's new? Show & tell.
Post on Zulip to request a show & tell slot;
by default, QuantStack will demo awesome JupyterGIS progress each meeting!


### 💡 (5 minutes) What will we hack on?

* **What do you want to work on today**?
  * For ideas, check out the [hackathon](https://github.com/geojupyter/jupytergis/labels/hackathon)
    and [good first issue](https://github.com/geojupyter/jupytergis/labels/good%20first%20issue)
    labels on the JupyterGIS project!
* **Add your ideas to the “ideas” list below**.
* **Add your favorite emoji or a `+` next to ideas you’re excited about**.
  * Press the colon (:) key on your keyboard or navigate to “Insert > Emoji” in the menu bar to open the emoji browser.


#### Ideas

* Brainstorm new, well-scoped use cases for Jupyter users analyzing geo data


### 🪄 (all the minutes) Hack together!

Form teams from the ideas generated in the step above!


### 💬 (10 minutes) Share out

Think about:
What exciting things did you accomplish?
What loose ends remain?
Big questions? Big ideas?

Please write for people who don’t have full context; link to related issues and documentation!

* **A Jupyter Widget which enables viewing many Python data objects together on a map as layers with a simple, well-typed, well-documented API**
  * `some_package.explore(da1, da2, gdf1, {data: gdf2, symbology: {"choropleth": {steps: 11, classification: "natural"}})`
  * Support rioxarray DataArrays  
  * Support geopandas GeoDataFrames  
  * Maybe: Support WMTS?  
  * Support some curated default symbology options  
    * Choropleth: # steps, classification mode, ?  
    * Symbol map: shape, min/max size, size variable, color variable
    * Dot density: …  
    * Cartogram: Maybe?  
  * Support some symbology customization  
    * Each symbology option provides   
  * Use a Jupyter Server extension to tile raster data under the covers, e.g. [rioxarray DataArray \-\> TiTiler](https://developmentseed.org/titiler/packages/xarray/)  
  * Send vector data to the renderer as binary (geoarrow)  
  * Future integration (developed as an independent component): Support a data discovery interface which can help the user find other data they want to integrate with their Notebook analysis  
    * Plain language search  
    * Produce Python one-liners to bring that dataset into their notebook, e.g. `geopandas.read_file(...)` and `xarray.open_mfdataset(...)`  
  * Display the data on slippy map widget (e.g. DeckGL)