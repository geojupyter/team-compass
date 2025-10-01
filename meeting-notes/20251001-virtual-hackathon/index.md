---
title: "GeoJupyter virtual hackathon"
description: |
  A GeoJupyter virtual hackathon. Open to all!
date: "2025-10-01"
image: "../images/hackathon.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Hackathons"
tags: [hackathons]
---

# GeoJupyter virtual hackathon (2025-10-01)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/92451699568)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=2pm)
- [Notes from previous hackathons](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Sign in!

Your name / GitHub ID / affiliation

* Yao-Ting / `@YaoTingYao` / CGA
* Nakul Verma / `@nakul-py` / independent
* Matt / `@mfisher87` / Schmidt DSE


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

* Support divergent color ramps: https://github.com/geojupyter/jupytergis/pull/912


### 💬 (10 minutes) Share out

Think about:
What exciting things did you accomplish?
What loose ends remain?
Big questions? Big ideas?

Please write for people who don’t have full context; link to related issues and documentation!

* Divergent color ramps:
    * Improve CSS for displaying disabled min/max input fields
    * Improve label of "Use actual range" button -- include the data min/max in the label! Thanks, Yao-Ting!
    * Minor refactors for readability (extract named boolean, leave props packed in object called `props`)
    * Only render min/max controls for graduated & singleband symbology modes
    * Fixup critical value display to use selected min/max, remove hardcode
    * WIP: Fixup saving/loading min/max/reverse from the shared model. Previously, these values were only "saved" in the downstream classified color stops, and when re-opening the UI they'd reset to default. Now, they save into the shared document, but they don't successfully load from the shared document (yet!). Pushed a WIP commit.