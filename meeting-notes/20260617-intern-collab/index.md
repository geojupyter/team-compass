---
title: "GeoJupyter Intern Collaboration"
description: |
  An event for technical, social, design, and other collaboration with GeoJupyter
  interns.
date: "2026-06-17"
author:
  - name: "The GeoJupyter community"
categories:
  - "Intern collaboration"
tags: ["intern-collaboration"]
---

# GeoJupyter Intern Collaboration (2026-06-17)

Please add new agenda items under the `New agenda items` heading!

- [Notes from previous events](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Sign in!

Your name / GitHub ID / affiliation / icebreaker

* Benjamin szeghy / `benjaminszeghy` / DSE / ?
* Matt Fisher / `@mfisher87` / Berkeley | DSE


## Agenda & notes

### Action item

- [ ] Benny: Create a JupyterGIS issue for the "draw + data"
- [ ] Benny: Create a corresponding initiative!
- [ ] Matt: Reach out to Clancy about collaborative draw + data use case


### Discussion

* Thinking about Lucia's described workflow
    * Using Google Earth imagery to inventory trees (do we understand this right?)
    * Presumably: Click a tree, get its coordinates, record attributes (species?) into a saved dataset
    * In JupyterGIS, you can create a dataset by drawing points, but you don't have attributes
    * To enable Lucia to do this in JupyterGIS:
        * Add a way to define the structure of the data you want to create, e.g. what fields you want and their types (string vs number)
        * Either fill out the form every time you create a point, or fill out (partially or in full) the form before clicking, and every click populates the pre-filled form values. E.g. "I want to mark every tree I click as a Spruce", and then you just click with no form-filling.
        * Perhaps you right-click on a layer, go to "properties", and then "attach form" that is used when drawing. This may feel a bit hidden for users using the tool the first time.
        * Bonus? "Add a marker at my current GPS location" -- could be useful for field data collection?
    * Clancy Wilmott & "Participatory Mapping"
        * Want a way to have many volunteers/team members contribute data to a single data source.
        * Have done this on individual project basis with custom implementation
        * Esri has "Field Maps", which costs extra! (And it's not very usable/configurable)
        * E.g. door-to-door tool called PDI, industry standard (and expensive)
            * Benny: Ordered voter data from state of CA and county of Alameda. Tried to use it with Field Maps. Had lots of issues, like couldn't control per-file data ordering when visualizing.
            * Talked to Clancy about this, and she's been looking at it for a long time and doesn't know a better way.
    * Matt: Benny should make an experience report (or many)!
        * Benny: I have a few past experiences ready to record
            * Benny: Ran in to jupyter-tiler issues for one use case.
        * Clancy is going on sabbatical soon, need her input ASAP.
* AI Chat bubbles
    * Let's review! :white_check_mark:
* Export to interactive map button? Downloads a zipped folder containing data & HTML file to display a map & maybe some other conveniences.