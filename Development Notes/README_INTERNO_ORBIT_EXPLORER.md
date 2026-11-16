# Orbit Explorer | Internal README

## 1. Project overview

**Orbit Explorer** is a browser-based educational space-colony survival and management game. The player manages an early settlement on Mars, balances essential resources, protects the crew, researches upgrades and expands the base while responding to environmental hazards and space-weather events.

The reviewed project is delivered as a single HTML application. The current supplied file is `Orbit_Explorer_BETA.html`; numbered historical builds from `Orbit_Explorer_BETA_0.1.html` through `Orbit_Explorer_BETA_0.10.html` were also reviewed.

### Core design pillars

- **Survival management:** keep Water, Food, Oxygen and Energy available.
- **Colony development:** spend Science to unlock and improve infrastructure.
- **Crew management:** crew members increase Science production but also consume supplies.
- **Environmental risk:** radiation and space-weather events create pressure on the colony.
- **NASA-informed learning:** connect game concepts to public NASA event records, research publications and station-report archives.
- **Accessible presentation:** use clear resource colors, readable text, pixel-art visuals and direct event feedback.

## 2. Current game loop

1. Collect resources through the action controls.
2. Monitor resource stocks, net production/consumption, crew count, health and radiation simulation.
3. Spend Science on upgrades and new buildings.
4. Build automated production for Water, Oxygen, Science, Energy and Food.
5. Expand crew capacity and manage the additional resource demand.
6. Activate the radiation shield when needed, while accounting for its Energy cost.
7. Respond to random or NASA-informed space-weather events.
8. Keep the colony stable for as long as possible.

### Main resources

| Resource | Role in the simulation |
|---|---|
| Water | Crew survival and water-related systems |
| Food | Crew survival and agricultural production |
| Oxygen | Crew breathing and oxygen-generation systems |
| Energy | Actions, production and shield operation |
| Radiation | Environmental hazard represented by a game simulation value |
| Science | Currency/resource used to unlock upgrades and buildings |

The displayed rates and caps are gameplay parameters. They should not be described as direct measurements from NASA hardware.

## 3. Main interface areas

The current HTML exposes these principal areas:

- **Start menu:** start the game, open settings and exit guidance.
- **HUD:** health, crew, outpost level, elapsed time, pause and sound controls.
- **Actions:** manual collection of Water, Food, Oxygen, Energy and Science.
- **Crew & Shield:** astronaut capacity, consumption guidance and radiation-shield control.
- **Upgrades:** improvements to resource efficiency, shielding, communication and oxygen use.
- **Build:** automated production and colony infrastructure.
- **Data:** mission phase, NASA DONKI event panel, radiation simulation label, ISS report archive and NASA NTRS research references.
- **Game-over screen:** reason for failure, survival time, largest crew, total Science and action count.
- **NASA sources modal:** links to official information sources.

## 4. Building and upgrade systems

### Automated buildings represented in the game

- Ice Drill: automated Water production.
- Oxygen Generator: automated Oxygen production.
- Science Lab: automated Science production.
- Power Plant: automated Energy production.
- Farm Tunnel: automated Food production.
- Habitat Module: increases crew capacity and resource capacity.
- Landing Pad / Space Shuttle: supports crew arrivals.
- Other upgrades improve recycling, greenhouse production, solar generation, shielding, air filters and communications.

### Individual building upgrades

In BETA 0.4, eligible placed buildings can be selected directly on the map and upgraded individually.

- Individual building levels are stored in `S.bldLv`.
- The building-specific upgrade window displays current and next production.
- The individual building upgrade cap in the reviewed code is Level 3.
- Each additional level increases the effective production contribution of that placed building.

Do not confuse the individual building Level 1–3 system with the broader upgrade progression displayed in the upgrade cards.

## 5. Event system

The game includes positive and negative events. Events can affect resources, crew conditions or the colony and can present the player with choices.

- The game timer is paused while the full-screen event decision is open.
- Positive events use the `GOOD NEWS` label.
- Dangerous events use the `WARNING` label and may trigger the siren.
- The player can choose an available action or wait, depending on the event state.
- Event consequences are resolved by the game simulation.

### NASA-informed event selection

When DONKI records are available, the game can use a real event category as the basis for an in-game event:

- FLR → solar-flare event category.
- CME → solar-storm event category.
- GST → solar-storm event category.

The reviewed code comments specify a 40% chance of selecting a NASA-informed event when records are available. This is a game event-selection rule, not a scientific probability model.

## 6. NASA data integrations

### 6.1 DONKI / CCMC

**Endpoint base used in BETA 0.10 and the subsequent unnumbered BETA:**

`https://ccmc.gsfc.nasa.gov/DONKI/WS/get/`

The client requests:

- `CME`
- `FLR`
- `GST`

The query window is the latest seven days, calculated as the current date minus six days through the current date.

**Refresh and cache behavior**

- Cached results are stored in browser `localStorage` under `donkiCache`.
- Cache validity is three hours (`DONKI_CACHE_HOURS = 3`).
- The refresh button forces a new request.
- The feeds are requested independently with `Promise.allSettled`, allowing partial results when one endpoint fails.
- Retrieved records are stored in `donkiData` and used by the event-selection system.

**What DONKI does not provide to this panel**

The reviewed interface explicitly states that these event feeds do not supply solar-wind speed or Kp index. Those values must not be fabricated from CME/FLR/GST event counts.

DONKI records are event data, not a continuous stream of every environmental sensor reading. Keep the UI clear about the distinction between:
- NASA-reported event records;
- game-simulated resource/radiation effects;
- any future direct instrument measurements.

### 6.2 NASA NTRS

The later unnumbered BETA adds a list of selected NASA Technical Reports Server references.

- Citation URLs are built with `https://ntrs.nasa.gov/citations/{id}`.
- Selected building cards can display a NASA fact and a related research link.
- The Data panel lists the research entries that have a paper reference.

This is a publication/reference integration, not a live data API. Verify report title, identifier and publication year against the NTRS record before using the entry as a formal citation.

### 6.3 NASA ISS Daily Reports

The later unnumbered BETA requests:

`https://www.nasa.gov/blogs/stationreport/feed/`

The client parses the RSS XML and displays up to four entries with title, link and publication date.

The interface describes this section as an archive. It is not a live ISS telemetry feed. Browser cross-origin restrictions or feed changes may prevent the request from loading; the code includes a failure message.

### 6.4 NASA OSDR

The current HTML includes a link to NASA OSDR as an information source. In the reviewed code, no direct OSDR API request or health-data ingestion was found.

Do not describe OSDR as an active live integration unless a real supported data connection is implemented.

## 7. Technical architecture

### Current delivery model

- One HTML file contains the page structure, styling and application JavaScript.
- Tailwind CSS is loaded from its CDN.
- Google Fonts loads Andika and Press Start 2P.
- Game rendering uses browser canvas and generated pixel-art assets/sprites.
- Browser `fetch` is used for external NASA resources.
- `localStorage` is used for DONKI response caching.
- The game is client-side; no backend service is required by the reviewed HTML.

### Key code areas

Names below are based on functions and identifiers found in the supplied source files.

| Area | Main identifiers / elements |
|---|---|
| Main game state | `S` |
| Resource and upgrade definitions | `UPGRADES_DEF`, `UPGRADE_STATS` |
| Difficulty and resource simulation | `getDifficultyPhase`, `getModeDrainMultiplier`, `eventDrain`, `crewSciRate` |
| Event selection | `triggerRandomWeatherEvent`, `showEventAlert`, `closeEventAlert` |
| HUD and alerts | `renderHUD`, `renderTopAlertBar`, `setTopAlert` |
| Colony rendering | `initColonyRenderer`, `draw`, `drawTerrain`, `drawRocket` |
| Individual building upgrades | `BLD_TYPE`, `UPG_KEY`, `UPG_INFO`, `bldLevel`, `bldPower`, `renderBuildingWindow` |
| Pause and audio | `togglePause`, `playSound`, `playSiren`, `playMenuSfx` |
| NASA DONKI | `fetchNasaDonkiTelemetry`, `DONKI_CACHE_HOURS`, `donkiData`, `DONKI_EVENT` |
| NASA research | `NASA_FACTS`, `NTRS` |
| ISS report archive | `iss-reports-list` |

The project is currently a monolithic HTML build. These names are navigation aids, not separate modules.

## 8. Running the game locally

1. Keep the HTML file and its filename unchanged while testing.
2. Open the HTML file in a modern desktop browser.
3. Allow network access for the external stylesheet, fonts and NASA requests.
4. Start a new game and verify the HUD and resource controls.
5. Open the Data panel and check the DONKI status, event counts and refresh control.
6. Check the ISS report archive and NTRS list separately.
7. Test pause/resume, event decisions, building upgrades and game-over flow.

A local web server is preferable for repeatable browser testing. Some browser security policies can behave differently when an HTML file is opened directly using `file://`.

## 9. Validation checklist

### Core gameplay
- [ ] Start menu opens and starts a new session.
- [ ] Difficulty selection changes the intended game parameters.
- [ ] Manual resource actions update stocks and costs.
- [ ] Resource production and consumption rates update correctly.
- [ ] Crew arrivals and capacity limits work.
- [ ] Shield activation consumes Energy and affects the radiation simulation.
- [ ] Upgrade purchases deduct Science and update production.
- [ ] Individual building selection and Level 1–3 upgrades work.
- [ ] Pause stops simulation time and resumes correctly.
- [ ] Positive and negative event decisions resolve correctly.
- [ ] Game-over screen reports the session results.

### NASA panels
- [ ] DONKI CME feed loads or shows a clear unavailable state.
- [ ] DONKI FLR feed loads or shows a clear unavailable state.
- [ ] DONKI GST feed loads or shows a clear unavailable state.
- [ ] Partial feed failure does not erase successful feeds.
- [ ] Refresh bypasses the three-hour cache.
- [ ] Recent events link to the corresponding NASA record when a link exists.
- [ ] NTRS links open the intended report.
- [ ] ISS archive shows entries or a clear failure message.
- [ ] No UI labels simulated values as direct NASA measurements.

## 10. Known limitations and maintenance risks

1. **Monolithic source:** HTML, CSS and JavaScript are bundled into one large file, making reviews and merge conflicts difficult.
2. **External dependencies:** Tailwind and Google Fonts require network access.
3. **DONKI availability:** external service availability, response structure and browser network policy can change.
4. **ISS feed availability:** RSS parsing depends on the NASA feed remaining compatible and readable from the browser.
5. **No live LSR telemetry:** no direct Life Support Rack live telemetry endpoint is integrated in the supplied HTML.
6. **No direct OSDR ingestion:** OSDR is currently a reference link, not a connected data pipeline.
7. **NASA key exposure in historical build:** BETA 0.9 contains a personal NASA API key in its source. BETA 0.10 removes it, but a public Git commit history can preserve the earlier value. Revoke/regenerate the key if it was real and publicly exposed.
8. **Research metadata:** verify every NTRS record ID, title and year. At least some displayed year values should be checked against the official record.
9. **Localization:** the current interface mixes English and Portuguese labels. Decide on a consistent language strategy before a public release.
10. **Version identity:** the unnumbered `Orbit_Explorer_BETA.html` contains changes beyond 0.10. Add a visible version/build identifier to avoid ambiguity.

## 11. Recommended repository structure

A future refactor could use this structure without changing gameplay behavior:

```text
Orbit-Explorer/
├── index.html
├── README.md
├── docs/
│   ├── README_INTERNAL.md
│   ├── PATCH_NOTES.md
│   ├── NASA_DATA_SOURCES.md
│   └── TEST_PLAN.md
├── src/
│   ├── game-state.js
│   ├── resource-simulation.js
│   ├── events.js
│   ├── buildings.js
│   ├── colony-renderer.js
│   ├── nasa-donki.js
│   └── nasa-research.js
└── assets/
    ├── sprites/
    ├── backgrounds/
    └── audio/
```

This is a recommended future organization. The supplied project is not currently structured this way.

## 12. Development priorities

### Priority 1: preserve and stabilize
- Preserve the exact judging submission separately from post-submission development.
- Add a version/build string to the title screen and documentation.
- Remove all credentials from tracked source and rotate exposed credentials.
- Test startup, resource loop, pause, events and game-over.

### Priority 2: data integrity
- Make DONKI status and timestamps unambiguous.
- Distinguish event records from live sensor telemetry.
- Validate NTRS metadata.
- Treat the ISS feed as an archive.
- Avoid claiming OSDR or LSR telemetry integration until implemented.

### Priority 3: maintainability
- Split the monolithic HTML into modules.
- Centralize NASA source metadata.
- Add a test checklist for each release.
- Keep patch notes aligned with actual commits and builds.

---

**Internal documentation status:** reconstructed from the supplied HTML versions. It describes implemented code where visible in those files and labels future structure or priorities as recommendations rather than existing functionality.
