# Orbit Explorer | Patch Notes

## BETA 0.10 and subsequent internal BETA update

**Project:** Orbit Explorer  
**Game concept:** Space-colony survival and management on Mars  
**Builds reviewed:** BETA 0.1 through BETA 0.10, plus the unnumbered `Orbit_Explorer_BETA.html` file  
**Document type:** Development changelog

> This changelog was reconstructed by comparing the supplied HTML builds. The unnumbered `Orbit_Explorer_BETA.html` contains additional work beyond BETA 0.10, but the file does not declare a formal version number. It is therefore documented as a subsequent internal update, not assigned an invented version.

---

## Highlights

- Expanded the original resource-survival loop into a colony-building and management game.
- Added a connected base layout, modular buildings, individual building upgrades and animated rocket arrivals.
- Improved event handling with full-screen alerts and player choices.
- Connected in-game space-weather events to NASA DONKI event records.
- Replaced the NASA API-key endpoint with the CCMC DONKI web service endpoint in BETA 0.10.
- Added NASA technical research references and an ISS report archive panel in the later unnumbered BETA.

## Version-by-version history

### BETA 0.1 | Initial playable foundation

The earliest supplied build establishes the core survival loop:

- Manage essential colony resources: Water, Food, Oxygen, Energy, Radiation and Science.
- Collect resources through direct player actions.
- Use Science to improve the base.
- Manage crew capacity, astronaut needs and radiation shielding.
- Survive changing conditions and random space-weather events.
- Present the colony through a visual Mars/base interface.

This is the baseline build used for comparison; the supplied files do not contain an earlier changelog.

### BETA 0.2 | Resource economy and automated production

The next build develops the survival simulation:

- Adds or expands automated resource-production upgrades, including Energy, Food, population arrivals and oxygen technology.
- Adds oxygen consumption per astronaut, with Air Filters reducing the consumption rate.
- Adds event-driven resource drains, such as losses caused by active hazards.
- Makes crew Science production responsive to crew conditions: sheltered crew stop producing Science, while sick crew produce less.
- Adjusts the difficulty phases and the timing of events and crew arrivals.
- Refines the resource and upgrade descriptions.

**Impact:** the player must balance production, consumption, crew growth and environmental pressure rather than relying only on manual collection.

### BETA 0.3 | Colony expansion, event decisions and audio

This build introduces a substantial expansion of the game systems:

- Adds a more developed base-building presentation, including a branching network layout and additional building types.
- Adds building and upgrade progression content.
- Adds full-screen event alerts and player choices for resolving events.
- Pauses the simulation while a full-screen event decision is open.
- Adds menu sound effects and a warning siren.
- Adds a Science cost to the manual solar/resource action, making the action part of the economy rather than a free action.
- Expands the visual presentation of the colony, including animated details and rovers.

**Impact:** the base becomes a place the player develops, not just a dashboard of resource counters.

### BETA 0.4 | Individual building upgrades, tiers and pause

A major systems update:

- Adds individual upgrades to eligible buildings directly on the colony map.
- Each eligible building can be upgraded up to Level 3; each level increases the effective production of that building.
- Adds per-building upgrade costs and a dedicated building information window.
- Adds progression tiers displayed at Levels 1, 3 and 5 for the related upgrade/building progression.
- Rebalances upgrade prices, maximum levels and production descriptions.
- Adds a pause control that stops the game timer and pauses music.
- Adds a pixel-art rocket, with a landing, ground-contact and take-off animation.
- Connects landing-pad progression and crew arrivals to rocket activity.
- Improves the HUD and building status presentation.

### BETA 0.5 | Rocket landing alignment

A focused visual correction:

- Changes the rocket landing target so the rocket lands at the center of the landing-pad structure, rather than selecting among nearby terrain positions.

**Impact:** rocket arrivals become visually consistent with the landing station.

### BETA 0.6 | Warning interface simplification

- Simplifies the top alert bar.
- Uses a consistent red `WARNING` treatment for alerts.
- Removes the previous multi-style badge/icon treatment from the alert bar and simplifies how event actions are displayed.

**Impact:** the warning language becomes more visually direct and consistent.

### BETA 0.7 | Full-screen decisions for all events

- Displays both beneficial events and dangerous events in the full-screen event alert.
- Distinguishes positive events with `GOOD NEWS` and negative events with `WARNING`.
- Plays the siren only for dangerous events.
- Changes the event-choice button styling.
- Makes the `Wait it out` option conditional so it is shown when the event flow requires it.

**Impact:** positive and negative events use a more consistent interaction model while retaining different warning semantics.

### BETA 0.8 | NASA DONKI event integration

Adds the first explicit NASA DONKI integration in the supplied version sequence:

- Queries three DONKI event categories:
  - **CME:** Coronal Mass Ejections.
  - **FLR:** Solar Flares.
  - **GST:** Geomagnetic Storms.
- Stores retrieved event records in the game state.
- Uses a NASA event record as the basis for an in-game weather event in 40% of event selections when records are available.
- Displays the corresponding real-event label and date in the event alert.
- Adds a NASA DONKI data panel with event counts and a recent-events list.
- Adds a manual refresh action.
- Adds a local browser cache with a three-hour validity period.
- Uses independent request handling so one failed feed does not necessarily prevent the other feeds from loading.

**Important distinction:** DONKI provides event records. It is not a continuous sensor stream for every environmental measurement in the game. The game still simulates resource production, radiation effects and event consequences.

### BETA 0.9 | Personal API key

- Replaces `DEMO_KEY` with a personal NASA API key in the source.

**Security note:** this key was removed in BETA 0.10, but a key committed to a public Git history may remain recoverable from earlier commits. If the key was real and exposed publicly, revoke or regenerate it through the NASA API portal. Do not put API secrets in client-side HTML or public commits.

### BETA 0.10 | DONKI endpoint migration

- Removes the embedded NASA API key.
- Changes the DONKI request base to `https://ccmc.gsfc.nasa.gov/DONKI/WS/get/`.
- Keeps the CME, FLR and GST feeds.
- Keeps the rolling seven-day event window, local three-hour cache and manual refresh behavior.
- Uses the CCMC-hosted DONKI service rather than the `api.nasa.gov/DONKI/` route.

**Impact:** the game no longer needs the personal API key in the client code for these DONKI requests. The code should still handle network failures and partial feed availability.

### Subsequent unnumbered BETA | NASA research and ISS archive panel

The supplied `Orbit_Explorer_BETA.html` contains additional features beyond BETA 0.10:

- Adds a **Life Support Research • NASA NTRS** section.
- Adds NASA Technical Reports Server links associated with selected base upgrades/buildings.
- Adds educational NASA facts to relevant building cards.
- Adds an **ISS Daily Reports • Archive** section.
- Loads the ISS station-report RSS feed and displays up to four entries when the feed can be read.
- Adds a note in the interface that the daily report series is an archive and that NASA stopped publishing those daily summaries in July 2024.
- Keeps the DONKI panel and CCMC endpoint integration from BETA 0.10.
- Adds or retains links to NASA DONKI and NASA OSDR as official information sources.

**Important distinction:** the NTRS section links to research publications, and the ISS section reads an archive feed. The supplied code does not implement a live Life Support Rack telemetry API or a live OSDR health-data feed.

---

## Data-source behavior in the reviewed build

| Source | Use in the game | Data type |
|---|---|---|
| NASA DONKI / CCMC | CME, FLR and GST event records | Space-weather event records |
| NASA NTRS | Research references associated with buildings | Technical publications |
| NASA ISS Station Report feed | Recent/archived station report links | RSS archive |
| NASA OSDR | External information link | Reference link; no direct data ingestion found in the reviewed HTML |

## Known boundaries

- The game’s radiation rate is labelled as a **game simulation** value, not a measured radiation dose.
- The DONKI event feeds do not provide the solar-wind speed or Kp index values displayed by dedicated monitoring services. The reviewed interface explicitly avoids fabricating those measurements.
- A real NASA event may influence the type/label of an in-game event, but the resulting gameplay effect remains part of the simulation.
- The ISS report feed may fail to load in a browser if the remote server blocks cross-origin requests or the feed is unavailable.
- The supplied build uses one large HTML file with embedded application code; this makes maintenance and regression testing harder.
- Some NTRS reference metadata, including displayed publication years, should be checked against the linked record before being treated as a verified bibliography.

## Recommended next steps

1. Keep a preserved copy of the submitted judging build.
2. Add a visible build/version identifier to the game and documentation.
3. Separate game simulation values from measured NASA data in labels and explanatory text.
4. Verify every NTRS title, report ID and publication year against its official record.
5. Add loading, empty, partial and error states to every external data panel.
6. Keep credentials out of the HTML and Git history.
7. Add a small automated smoke test for the game startup, pause, event modal, building upgrade and NASA data panel.
