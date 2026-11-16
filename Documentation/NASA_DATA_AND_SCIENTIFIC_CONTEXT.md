# NASA Data and Scientific Context

## NASA DONKI

The prototype contains a browser-side request to the NASA DONKI **CME Analysis** endpoint. It requests records for a recent 30-day window and, when the request succeeds and a record contains a usable speed field, displays the latest available CME speed.

Official service: <https://kauai.ccmc.gsfc.nasa.gov/DONKI/>  
NASA Open APIs: <https://api.nasa.gov/>

### What the DONKI panel means

- DONKI is used as contextual space-weather information for the learning experience.
- The displayed speed is a reported **coronal mass ejection (CME) speed**.
- CME speed must not be labelled as solar-wind speed.
- The value is not a direct measurement of radiation at Mars and is not a Mars-specific forecast.
- DONKI data does not currently alter resource rates, event probabilities or simulation outcomes.
- If the API cannot be reached, the interface should clearly show that live data is unavailable and that the game is operating in simulation mode.

The browser request currently uses NASA's `DEMO_KEY`. Availability and rate limits may vary. A failed request does not prevent the local game simulation from being played.

## NASA Open Science Data Repository (OSDR)

The game links to NASA's Open Science Data Repository as a research resource: <https://osdr.nasa.gov/>. The current prototype does **not** make a direct OSDR API request or import OSDR datasets into gameplay. Do not describe OSDR as an implemented data integration.

## Scientific interpretation and educational simplifications

The game represents broad mission-planning themes: life-support resource management, energy constraints, crew needs, infrastructure and space-weather awareness. It simplifies these subjects into understandable game mechanics.

The resource quantities, consumption/production rates, radiation-like game indicator, event effects, upgrade costs and colony outcomes are not engineering models or operational recommendations. They have not been validated against a specific NASA mission design or life-support system.

## Appropriate claims

Use: “The game includes a NASA DONKI CME Analysis panel that can display recent CME analysis data when the API is available.”

Do not use: “The game predicts radiation on Mars,” “DONKI controls the in-game solar storms,” or “the game uses OSDR datasets.” Those statements are not supported by the current implementation.
