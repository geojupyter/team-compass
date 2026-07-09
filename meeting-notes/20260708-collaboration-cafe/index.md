---
title: "GeoJupyter Collaboration Café"
description: |
  A GeoJupyter event for technical, social, design, and other collaboration.
  Open to all!
date: "2026-07-08"
author:
  - name: "The GeoJupyter community"
categories:
  - "Collaboration Cafes"
tags: ["collaboration-cafes"]
---

# GeoJupyter Collaboration Café (2026-07-08)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/92451699568)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=2pm)
- [Notes from previous cafés](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Sign in!

Your name / GitHub ID / affiliation / icebreaker

* Matt / GitHub ID / affiliation / ?
* Benny / GitHub ID / affiliation / ?
* Maryam? / GitHub ID / affiliation / ?
* Name / GitHub ID / affiliation / ?


## Agenda & notes

### ⚡ (5 minutes) Lightning intros

Tell us about you in 30 seconds or less!


### 🌐 (5 minutes) Lightning demo

What's new? Show & tell.
Post on Zulip to request a show & tell slot;
by default, QuantStack will demo awesome JupyterGIS progress each meeting!


### 💡 (5 minutes) What will we work on?

* **What do you want to work on today**?
  * For ideas, check out the [hackathon](https://github.com/geojupyter/jupytergis/labels/hackathon)
    and [good first issue](https://github.com/geojupyter/jupytergis/labels/good%20first%20issue)
    labels on the JupyterGIS project!
* **Add your ideas to the “ideas” list below**.
* **Add your favorite emoji or a `+` next to ideas you’re excited about**.
  * Press the colon (:) key on your keyboard or navigate to “Insert > Emoji” in the menu bar to open the emoji browser.

### Action items

- [ ] Matt: Make a sequence diagram of events explored below
- [ ] Matt: Make a design fiction blog post including sequence diagram
- [ ] Matt & Maryam: Review the above, then share it with the team (including Juliana, ?)!

### Notes

* Trail:
    * Handling work across computers?
        * Persistent project ID in the trailfile. Use GitHub to clone the project to the other machine.
        * Analogy to lockfiles.
        * https://docs.sylabs.io/guides/3.5/user-guide/introduction.html#
    * Collaboration with another person across different aspects of the same project?
        * Maryam: Haven't thought about RTC yet -- ignore RTC for now
        * Maryam: Focus on single-user workflow for now.
    * Emulating Windows on MacOS for certain tools?
        * We only care about tools in the Jupyter ecosystem
    * If we pin this to Jupyter-only tools, do we actually have the tools in our ecosystem to enable people to stop using their non-Jupyter tools (like QGIS, [JOSM](https://josm.openstreetmap.de/), ?)
        * Maryam: Haven't touched JGIS/QGIS/Arc for 4 years. Have been in Python instead! Jupyter Notebooks for viz/map export only.
    * Service vs multiple processes writing to a single shared file (and possible collisions), multiplayer support?
        * Run in jupyter server?
    * Very simple use case
        * Start from a project by Maryam's students!
        * https://rabahbabaci.github.io/MTC-Transit_Access_Equity/
            * User is downloading data from a public network with a Jupyter data discovery tool
                * Mock JupyterDataConnect -- it outputs a file that was downloaded and a STAC file
                * Event: Query was performed.
                * Event: Data was acquired.
            * Imports into JGIS
                * Event?: User started a JGIS project
                * Event: Data was loaded in JGIS
                * Event: User zoomed in to \<bbox\> and lingered there for 45 seconds.
                * Event: User drew a polygon
                * Event: User buffered the polygon
            * Does cleaning steps in a Notebook
                * Event: User executed a Notebook cell that opens previously-acquired data. _For now, we don't care about linking this event to the data-acquisition event_.
                * Event: User executed Notebook cell with streaming data. _For now, code is the only provenance -- no static analysis, no relationship to other events -- e.g. user streamed some data? There's an `xarray.open_dataset(...)` call that describes that_.
            * Does map interactions
                * Event: For each _major_ interaction
            * User uses another Notebook for exploration
                * TODO: Flesh this out later.
            * User uses another Notebook to finish analysis, producing outputs data files
                * Event: User runs Notebook cell that reads data. Only record what code was executed, we don't care about what the code actually did.
                * Event: Intermediate data products are read. **Trail is constantly watching the folder for read files (i.e. listening to file events)**. _This event is not connected to the previous code cell_.
                * Events: Notebook execution and file reads
                * Event: Artifact created in the project folder
                    * **Trail is constantly watching the folder for new files (i.e. listening to file events)**. _This event is not connected to any code cell events_
            * Publication:
                * Print citations: When/how did the user acquire the data
                * Print methods: What code was executed
                * Write a MyST site
                * Event: `myst build --html`
                * If the user pushed to GitHub and GitHub builds the site, we don't record anything. They can manually create an event if they want to.
                *
        * https://storymaps.arcgis.com/stories/9ab0271a09d4475fbccc68f57e97d70e
        * https://anandashar01.github.io/bart-transit-equity-full/
    * What does the actual protocol / message format look like?
        * Can we mock up an example trail file?
        * What expectations for tool implementation do have? Do we want those tools, like JGIS, to save provenance information internally in their own artifacts and write copies to Trail?
    * Clearly defined MVP?
    *
