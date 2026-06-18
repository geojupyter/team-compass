---
title: "GeoJupyter Collaboration Café"
description: |
  A GeoJupyter event for technical, social, design, and other collaboration.
  Open to all!
date: "2026-06-18"
author:
  - name: "The GeoJupyter community"
categories:
  - "Collaboration Cafes"
tags: ["collaboration-cafes"]
---

# GeoJupyter Collaboration Café (2026-06-18)

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

* Thorsten / `@derthorsten` / QuantStack
* Matt / `@mfisher87` / Schmidt DSE
* Martin Renou / `@martinRenou` / QuantStack
* Min / `@minrk` / UC Berkeley
* Florence Haudin / `@HaudinFlorence` / QuantStack
* Sylvain Corlay / `@sylvaincorlay` / QuantStack


## Action items

- [ ] Martin & other QuantStack folks: Talk with Ian!


## Discussion

* Jupyter GIS & async -- can we solve this in ipykernel?
    * Race condition breaking our Python API: https://github.com/geojupyter/jupytergis/issues/1481
    * When you load a document in the Python API, the frontend provides the document content (using comms). These would only be received after the cell execution is done.
    * When loading a document and adding layers all in one cell, the new layers are added before the old layers load.
    * Looking in to `await doc.ready()` which resolves when the document is loaded
    * xeus-python supports top-level await!
        * in ipykernel top-level await is possible, but when awaiting comm messages, the kernel gets stuck -- the comms message comes in after execution, and execution is waiting for the comms message.
        * Min/Thorsten: does ipykernel run an event loop per cell or one big event loop? Min: a cell is a coroutine. Thorsten: xeus does the same. **Min: ipykernel has a single queue for cell execution and comm messages!**
        * Is it really a queue? Abstractly -- just a coroutine running a for loop.
        * Min: Cell messages should be concurrently processed.
        * Martin: Can comm messages come through a separate queue? Min: Could create a race condition in the kernel
        * Sylvain: For xeus, "finished" means **scheduling** the code, not executing the code.
            * Min: Multiple cells awaiting tasks can then run out of order
            * Sylvain: Xeus makes an exception for execute requests to be queued. This means comm messages can come in before an execution is complete.
            * Min/Sylvain: There is ambiguity in the protocol! This needs to be addressed at the protocol level. Be explicit about what is appropriate to be concurrently processed. This ambiguity allows for multiple interpretations (xeus: concurrent vs ipykernel: ordered message processing).
            * David Brochart playing with "akernel" experiment where everything is async/concurrent (including concurrent cells).
    * Min: Having a "ready" task is probably the right solution, but probably addressable without top-level await. Can instead schedule adding a layer. Martin: Basically make the whole API async. Min: We can make the top level function still be sync -- it just schedules the task. Martin: The current API expects to be able to act on the layer, and it returns a value.
    * Think we can solve this in ipykernel without too much change. Min: Agree, if we think that's the direction we should go. It's just a detail question of how we do it. Do we spawn a task to schedule execution, or do we do something more like grouped queues to preserve comm message ordering?
        * Sylvain: Comm message ordering is going to lead to more deadlocks
        * Min: Things like comm messages which are unidirectional (no associated reply) make a more reasonable case for concurrency
        * Sylvain: The kernel status message on iopub (busy (started processing message)/idle (finished processing message)). Should probably be an integer representing how many tasks are running. Min: Including the channel in the status message is reasonable. busy/idle is an accurate description for a single channel, but with multiple channels, it's really "started processing" and "finished processing" and becomes an inaccurate representation of busy/idle.
* Next step: Check if there is a JEP to clarify protocol ambiguity, if not create one!
    * This will be a slow conversation.
    * Sylvain: https://github.com/ipython/ipykernel/pull/589
    * Sylvain: Similar case with JupyterLite bluetooth manager -- used to control physical toys. Want to e.g. wait for motor to reach specific angle. This raises the same problem!
    * Min: Makes sense for the internals of JGIS to be async. But we can wrap it in a sync API. Or we can just break the API and make the public API async.
        * Thorsten did this for the robotics case. From the outside, stuff looks blocking, but it isn't really. For that reason, think it's better to have an async public API.
            * E.g. interacting with a widget async looks like creating a task. When you print from within the task, it doesn't appear below the cell where you expect it, but instead in the log. It's confusing hard to explain to users. Errors are silent. A top-level `await` means e.g. your `print` statements end up where you expect them.
                * Min: There is a way to have a sync API that works. You can write coroutines, or futures. For a coroutine, if you don't await it, nothing happens. For a future, the user can await it if they want to to get the return value, but the side effects still happen.
                * Thorsten: In ipykernel today, if you await the change of a slider in a single cell, you'll deadlock.
                * Min: Do you want to make people always use await, or do you want things to work if they don't?
                * Could just raise an error if things aren't ready.
### Conclusions

* **look in to ipykernel processing comms concurrently with cell execution**
    * does not require going through JEP process!
    * Ian Thomas should look at this.
    * Potential issues:
        * Clicking a button with async behavior then clicking a button with sync behavior -- could run in opposite order you clicked it. The human would need to know to wait before clicking the 2nd button.
            * This is unlikely to cause problems in reality (Min: "computers usually win races with humans"), but now it can **technically** happen.
* JGIS can show a warning for now until ipykernel resolves the concurrent comms problem!
* Extra (JGIS not dependent on):
    * channel should be in iopub status message parent headers
    * JEP: Clarify the protocol to say that :point_up: is OK, but not required.