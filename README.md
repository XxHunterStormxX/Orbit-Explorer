# ORbit Explorer

**Junior Astronaut Mission Trainer | NASA Space Apps Challenge 2026**  
**Team:** Orbit Sprint

ORbit Explorer is an educational, browser-based Mars colony management game. Players operate the fictional **Base Ares Planitia** and make resource decisions involving food, water, oxygen, energy, science, crew size, research and infrastructure.

The central learning idea is trade-offs: each decision affects the colony. For example, expanding the crew increases science production but also increases life-support demand. Building infrastructure can improve production while requiring resources and energy.

## Play the game

Open [`index.html`](./index.html) in a modern browser, or use the published GitHub Pages URL once Pages has been enabled for this repository.

## Project contents

- `index.html` — game prototype (HTML, CSS and JavaScript in one file).
- `Documentation/` — project overview, gameplay, science/data notes and limitations.
- `References/` — external sources and credits.
- `Presentation/` — team presentation, if added to this repository.

## NASA data and scientific scope

The prototype includes an optional NASA DONKI CME Analysis data panel. When the browser can reach the NASA API, it requests recent CME analysis records and displays the latest available CME speed as contextual information. This is **not** a Mars weather forecast, a solar-wind measurement, or a radiation measurement at Mars. The game simulation does not automatically change based on DONKI records.

NASA OSDR is listed in the game as a research resource. The prototype does not currently retrieve OSDR data directly.

All resource rates, radiation-like indicators, event effects and colony outcomes inside the game are simplified game mechanics. They are not engineering specifications, medical advice, or operational mission-planning outputs.

## Current status

This is a prototype intended to communicate an educational concept. See [`Documentation/IMPLEMENTATION_AND_LIMITATIONS.md`](Documentation/IMPLEMENTATION_AND_LIMITATIONS.md) for what is implemented and what remains future work.

## Team

Orbit Sprint

## License

No open-source license has been specified yet. Unless a license is added, the repository's contents should not be assumed to be available for reuse. Review the licenses of any third-party assets or libraries before redistribution.
