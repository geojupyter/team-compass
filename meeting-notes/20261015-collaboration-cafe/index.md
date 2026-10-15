---
title: "GeoJupyter Collaboration Café"
description: |
  A GeoJupyter event for technical, social, design, and other collaboration.
  Open to all!
date: "2026-10-15"
author:
  - name: "The GeoJupyter community"
categories:
  - "Collaboration Cafes"
tags: ["collaboration-cafes"]
---

# GeoJupyter Collaboration Café (2026-10-15)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/92451699568)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=2pm)
- [Notes from previous cafés](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Sign in!

Your name / GitHub ID / affiliation

* Parikshit / `@PariSolunke` / NYU
* Daniel / `@hodczak` / BIDS
* Matt / `@mfisher87` / DSE


## Agenda & notes

* Previous onboarding meeting with Daniel
    * https://docs.google.com/document/d/1f_lQzJIV_9XapYmMjx58EhWmZRf_6USAMSAdGjdA3Nc/edit?tab=t.0#heading=h.pd3w5j3ddmze
* Pari: want to understand role, how I can help
    * Specialize in viz & machine learning
    * Experience w/ JS & TS (D3, React, Angular, MapBox, Leaflet); Python (APIs w/ Flask)
    * Not much direct experience with GIS (segmentation model training for Tile2Net)
    * Comfortable with Git/GitHub
    * Visualization / interface for Trail? Appealing as an entrypoint.
        * Create a mock trailfile containing a simple graph of steps and prototype a UI based on it!
        * Example "trail": <https://geojupyter.github.io/presentation-cng2026/assets/images/jupyter-trail-history-diagram.png>
    * Pari used NotebookJS <https://github.com/jorgehpo/notebookJS>
        * Maybe check out Anywidget for a modern conventional approach? <https://anywidget.dev/>
* Pari: How we work together -- etiquette, PRs, etc.
    * Starting work in https://github.com/geojupyter/prototype-trail/ repo
    * PRs: Everything in a PR, PRs should be small as possible, feel free to self-merge unless you feel a need for a review or input from the team
    * Decisions: https://github.com/geojupyter/trail
    * Documentation: We'll document the prototype. We'll autogenerate API/CLI docs with Sphinx
    * Inline documentation: Write docstrings, include descriptions of arguments in Google style
    * Code quality and other stuff in the Google doc linked at the top of these notes
* Daniel: GeoJupyter / Jupyter extensions / JupyterGIS
    * GeoJupyter chat is on the Jupyter Zulip (open source Slack): <https://jupyter.zulipchat.com>
    * GeoJupyter community calendar: <https://geojupyter.org/calendar>
    * High level tutorial: <https://github.com/jupytercon/jupytercon2025-developingextensions>
        * Suggest exploring this tutorial (modules 1-3) before November
        * Recording: https://www.youtube.com/watch?v=z-KZ6CjZjbM
    * JupyterGIS development setup guide: <https://jupytergis.readthedocs.io/en/latest/contributor_guide/development_setup.html>
    * Jupyter extensions: use [Micromamba](https://mamba.readthedocs.io/en/latest/user_guide/micromamba.html) for package management
    * /
*
* Daniel's notes
    * Dependency should be in pyproject.toml, not requiremens.txt
    * Pre-K is a Rust version of pre-commit and better, highly suggested
    * We have a file that defines our checks
    * Linting and formatting both using ruff
    * type-checking is Pypy
    * uv is not only faster, simpler user interface
    * Later on we might want a task runner
    * Only thing shouldn't be put in pre-commit is mypy
    * Good docstrings, good names, intuitive order, early returns
    * Kwargs over posargs. Often we should use required kwargs
    * Naming booleans is really important
    * Publishing using trusted publishing
    * For docs, we want API and CLI docs that are generated from docstrings
    * We want type annotations
    * Diataxis valuable for documentation
        * Tutorials
        * How-to
        * Examples
        * Reference
    * Diataxis highly recommended, read it
    * Github actions for most of our CI
    * automated tests
    * for minimum and maximum supported versions of python
    * pre-commit has its own CIs
    * look at the existing geospatial universe in jupyter, see where the gaps are and try to fill them
    * Reproducible research artifacts
    * Stuff that's frustrating, a waste of time
    * Stuff that's bad science, closed science
    * Interviews showing a few places where those gaps
    * hard to tell a story, so use ArcGIS story maps, which is proprietary :money_mouth_face:
    * Google Earth Engine, :money_mouth_face: :moneybag: also forces JavaScript :face_with_head_bandage:
    * Solve general, wide-ranging problems
    * Underneath geojupyter there's workshops, talks, educational materials, hackathons, combination of softwaer work and social work
    * Most of our work is on zulip
    * zulip chat, community calendar
    * collaboration cafe meeting, rescheduled
        * need to figure a new time
    * jupyter extentensions
        * high level tutorial for developing jupyter extensions
        * modules 2 & 3 important
        * If I do this tutorial before November, Matt can answer questions
        * jupyter lab is somewhat like an operating system (not a good term), but applications, terminal, everything can be done through this interface
        * menu bar, main area, status bar, left panel, right side panel
        * jupyterlab execute time
            * you install this extension, and then all of your cells show how long it took to run
        * cell magic or code is a hassle

    * extensions and plugins sound like they can be the same thing
        * widgets are the inner most thing, most exposed thing
        * extension is the thing you install
        * if you pip install, you are installing an extension
        * a plugin is very specifically a javascript thing
        * jupyterlab is just a pile of extensions cobbled together
        * Because it's extensions all the way down, you can customize it
        * You don't need to use jupyter lab, you can use your own lightweight interface
        * server extensions written in python
        * jupyter tiler tile server in the background
        * myst exposes a couple of endpoints
        * All that is backend API hkind of stuff, server extensions always written in python
        * front-end extension written in javascript or typescript
        * themes exposed as jupyter extensions
        * Extensions that are both: front and and server
            * Interface that allows user to do e.g. git add, front end stuff and when you do `git add` that needs to happen on the server
    * recorded tutorials
    * recorded too
    * APIs you need for documenting extensions are with NIX quality
        * Go through the jupyter extension documents, how do you define a command how do you define a launcher, etc.
        * commands are the under the hood way to expose to the user interfaec
        * Commands are also visible to LLMs
        * Commands are how you register behaviors to the user interface
        * Jupyter lab exposes these menus
        * Anything you define on a menu is a command
        * Commands are the behaviors that underly the buttons
        * Commands can be added to buttons
        * Draw features new layer
* micromamba, conda
    * for JupyterGIS, really recommend micromamba
    * micromamba is just like a package manager
    * several options equivalent to micromamba
    * solved many pitfalls
    * general recommendation is pixi
    * micromamba can be a rust package, etc.
    * main advantage is that there are some system level dependencies
    * e.g. GDAL
        * hard to install
        * If you install a python library, it requires a very specific version of GDAL
        * mamba, conda, etc. would allow you to install an isolated environment
        * micromamba way simplifies all the problems
        * allows you to get GDAL and the correct version
        * shared libraries
* extension is high level building block
    * plugin is frontend javascript object
    * sending a request to the server side
    *  example logs if there is an API endpoint "hello"
    *  we copied the extension, build it, test it
    *  HelloRouteHandler is an example of extension
* Widget can be both in python and javascript
    * Widget says Hello, World
    * p-tag is paragraph tag
    * innerHTML is hello world
* Commands
    * Register a command / plugin activation plugin time
    * Commands have IDs
    * Use the colon to make pseudo-namespaces
        * Jupyter uses this pattern
    * Execute key and label key, label is what shows up
    * New raster tile
    * Execute is what happens when you click that button
    * HOw do you know when that command should be active
    * You add a command, but no way to call it, so you add it ito the command palette
    * Or add it to the launcher with palette.add
* JupyterGIS
    * Extensions, widgets
    * Symbology widget
    * The thing that's rendering the map is OpenLayers, a JavaScript layer (old , since 2013 and slowed down)
    * Large datasets
    * This one is less than a thousand points
    * Soon as you load more than 50k, it will have poor performance
    * lonboard is an example that implements as a jupyter widget
    * we're talking about supporting deckGL
    * So many javascript renderers, different tradeoffs
        * OpenLayers supports any custom projection
        * We can't do it now,  but there's polar projection
        * Lonboards doesn't support polar projections
    * HOw do we support the user getting the correct renderer for their projection?
    * Supporting pluggable renderers
    * MapLibre, DeckGL, etc, what do the capabilities between the different renderers look like
    * One is going to lose support for geoparquet, etc., help user make an informed decisiion
    * Conflict-free replicated data types (CRDT)
        * Underpinning of all collaborative software that works correctly
        * multiple machines that work on a type
        * Multiple people can work on the same document
        * (such as Google Docs)
        * Multiple users responding to comment thread, multiple users editing something that changes JSON file
        * All powered by jupyter collaboration
    * Jupyter Real-Time Collaborative is another API for CRDT
* Another stream is awareness: sharing stream across users
    * example is cursor
* When you create a vector layer, Geoparquet
    * nice geoparquet that is very efficient for representing data
    * gets turned into geojson (very inefficient)
* pm tiles is the visualization optimized version of geoparquet
* overviews, or tile pyramids
* First priority: get clone of Matt's work, see if you can consume the events
