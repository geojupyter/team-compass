---
title: "GeoJupyter Collaboration Café"
description: |
  A GeoJupyter event for technical, social, design, and other collaboration.
  Open to all!
date: "2026-04-01"
author:
  - name: "The GeoJupyter community"
categories:
  - "Collaboration Cafes"
tags: ["collaboration-cafes"]
---

# GeoJupyter Collaboration Café (2026-04-01)

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

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Benny Szeghy / `...` / UC Berkeley


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

#### Action items

- [ ] Esha: Open a new issue in prototype-map2cell-ipyopenlayers repo. "Support lines, polygons, and points"
- [ ] Benny: Open a new issue in same repo. "Open communication lines with JupyterAI project"
- [ ] Benny: Open PR for `integrate_draw` branch, add Matt as reviewer
- [ ] Benny & Esha: Implement `vector_types_dropdown` functionality


#### Ideas & discussion

* Discussion: JupyterGIS "Open source GEE"
    * JupyterGIS has some concrete advantages over GEE:
        * It's Python-native (GEE is JS-native)
        * Partial execution support in GEE is poor, JGIS can leverage Notebooks
* Connection: Jeff Chambers, prof at Berkeley
    * Switching from Envi -> GEE for his course
    * Thinking about: Python needs a faster algorithm for grey-level co-occurrence matrix (GLCM). R implementation is good.
* JupyterAI? How do we integrate?
    * How do we make an interaction more valuable than just using the chat window directly?
    * Maybe we offer some static prompts that when clicked populate the JupyterAI chat window with the prompt. E.g. "How do I integrate this new shape with my existing analysis?"
        * **Simple starting place -- let's do this**
    * Use the LLM itself to suggest useful prompt. E.g. give the LLM access to the layers that are on the map and maybe some details (bounds? field names?) about the layer and ask it to generate things the user might do next.
* How do we record interns' work plans?
    * Use GitHub issues! Put in:
        * requirements (what we're updating, how)
        * scope
        * who's doing the work (assign)
