---
title: "GeoJupyter core community meeting"
description: |
  A monthly gathering of the GeoJupyter core community. Open to all!
date: "2026-01-27"
image: "../images/community-meeting.jpg"
author:
  - name: "The GeoJupyter community"
categories:
  - "Meeting notes"
tags: [meeting-notes]
---

# GeoJupyter core community meeting (2026-01-27)

Please add new agenda items under the `New agenda items` heading!

- [Join us on Zoom](https://berkeley.zoom.us/j/99659397059?pwd=519zZJlcAa1TCyJWRYyYbaYDfuaXNo.1)
  - [What time is the meeting in my time zone?](https://dateful.com/convert/utc?t=3pm)
- [Previous meetings](https://compass.geojupyter.org/meeting-notes/)
- [GeoJupyter](https://geojupyter.org) handy links:
  - [GitHub org](https://github.com/geojupyter)
  - [Community calendar](https://geojupyter.org/calendar.html)
  - [Zulip chat](https://jupyter.zulipchat.com/#narrow/channel/471314-geojupyter)


## Attendees

Your name / GitHub ID / affiliation

* Matt Fisher / `@mfisher87` / Schmidt DSE
* Martin Renou / `@martinRenou` / QuantStack 
* Name / GitHub ID / affiliation
* Name / GitHub ID / affiliation


### New agenda items

- Scrollytelling! :tada:
    - Greg: Working on changing symbology of layers while progressing through the story. Uses the full symbology editor!
        - Matt: Currently, we have a copy of the full symbology data structure for each step (landmark/keyframe) in the story. What if we only saved the different parts of the symbology data structure for each landmark/keyframe (i.e. overrides)? Then, for example, changing a non-overridden field, e.g. colormap, would apply to all the keyframes and save the user work. We could also display in the editor which fields are overridden, and provide a "reset" button to un-override a field for a given keyframe.
- Our schema architecture
    - Is it working? Do we like RJSF? (Some of us don't for sure XD) Is it worth the cost?
        - Sometimes, we need to add a primitive field to a layer config, and it works _great_ for that.
        - Other times, there's complexity with the feature set supported by the libraries that generate stuff (TS types, Python types, forms), and we need to work around differences to make the outputs compatible with each other
        - Still other times, we need non-primitive fields. Is this number field an "input" element or a "slider" element? The "classification" map is an example where we need to completely override form generation to have a mapping between data values ("input") and colors (color picker), and we need a "Classify" button which depends on the values of other fields ("classification mode", "min", "max") to populate the mapping fields. So we completely ditch RJSF to implement that functionality in React, and as a consequence our schema and form go out of sync.
        - What other options are there?
            - Use the schema only for validation and build all forms in React?
            - Some in-between where we provide more information about the UI in the schema (e.g. component type, `ui:foo` fields from RJSF's "uiSchema")?
                - E.g. for the "vector color symbology" schema, we could say that the entire schema uses the `VectorColorSymbology` component to render, and the "classification" field of that schema uses the `ColorClassification` component to render. This may introduce a lot of complexity, but grants more confidence that the schema is staying in sync with the UI. Does it make it easier to contribute (special-casing JSONSchema doesn't seem very contributor-friendly, but maybe if we do a great job documenting it? :clown_face:)