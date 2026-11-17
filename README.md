
# ORbit Explorer

**A Space-Colony Survival and Strategy Game | NASA Space Apps Challenge Project**

> **Post-Event Project Updates**
>
> Following the conclusion of the NASA Space Apps Challenge event, the ORbit Explorer project continued to evolve through additional development, improvements, and technical adjustments.
>
> As part of this ongoing development, the `Development Notes/` folder was added to the repository after the event. It serves as a dedicated record of post-event programming activities, including code modifications, bug fixes, new implementations, gameplay improvements, and technical updates.
>
> **Important:** These notes document work carried out after the NASA Space Apps Challenge event and are separate from the original project submission. They provide transparency about the project's continued development and make it possible to track its evolution over time.
>
> For information about changes and improvements made after the event, please refer to `Development Notes/`.
>
> **Final version:** the final post-event version of the game is inside the `Development Notes/` folder: [`Development Notes/Orbit_Explorer_Final_Version.html`](Development%20Notes/Orbit_Explorer_Final_Version.html) ([play online](https://xxhunterstormxx.github.io/Orbit-Explorer/Development%20Notes/Orbit_Explorer_Final_Version.html)). The original submission (`index.html`) remains unchanged.

ORbit Explorer is an educational space-colony management game prototype. Players make resource and survival decisions while developing a settlement on Mars. The project combines a playable HTML prototype with a presentation and supporting documentation.

> **Project status:** Prototype. Features described as planned or under development are not necessarily implemented in the current game. NASA data integration is documented conservatively; simulated values and real external data must not be confused.

## Repository Guide

This repository is organized so visitors, teammates, and evaluators can quickly find the playable prototype, understand the project, and review its supporting materials.

| Item | What it contains | Why it is here |
|---|---|---|
| `index.html` | The browser game prototype, including HTML, CSS, and JavaScript in one file. | Main playable entry point. |
| `ORBITA EXPLORER - English.pdf` | The team's project presentation in PDF format. | **This is the presentation for reviewers.** It introduces the project, explains the problem and proposed solution, shows the game concept and features, and communicates the intended impact and next steps. |
| `Documentação/` | Markdown documentation about the project, gameplay, implementation, scientific context, limitations, and submission information. | Provides written detail that does not fit into the presentation slides. |
| `Referências/` | Sources and credits used by the project. | Helps readers identify external references, data sources, and third-party resources. |
| `Development Notes/` | Post-event development notes and programming updates, including the **final version of the game** (`Orbit_Explorer_Final_Version.html`). | Documents ongoing development, improvements, bug fixes, and technical changes made after the NASA Space Apps Challenge event. |
| `README.md` | This guide to the repository. | Starting point for anyone visiting the project. |

## How to Run the Game

1. Open the repository and select `index.html`.
2. Download the file, or clone/download the repository.
3. Open `index.html` in a modern web browser.

The prototype is designed as a browser-based HTML game. If the project is published with GitHub Pages, the game can also be opened through the Pages website address.

## Project Presentation

The PDF file **`ORBITA EXPLORER - English.pdf`** is the presentation deck.

It is intended to give evaluators and other visitors a concise overview of the project. It should be read alongside the playable prototype and the Markdown files in `Documentação/`.

The presentation is a communication artifact: it explains the concept and the team's proposal. The actual implemented behavior should be verified in `index.html` and the implementation documentation.

## Scientific Context and NASA Data

The project explores space-colony survival and uses NASA-related scientific context. The prototype includes an attempted connection to NASA's DONKI service.

A connection attempt or displayed fallback does not, by itself, prove that live NASA data is successfully retrieved or used to drive gameplay.

Please consult the scientific-context and implementation documentation for the exact status, limitations, and source references. Values generated internally by the game are simulations, not NASA measurements.

## Current Scope and Limitations

- This repository contains a prototype, not a certified engineering simulator.
- Simulated resource levels, hazards, and environmental indicators are gameplay mechanics.
- External API availability may vary; fallback behavior should not be interpreted as live data.
- Planned features and educational goals should be distinguished from features currently implemented.
- The project should not be used for real mission planning or operational decisions.

## Suggested Review Order

1. Read this `README.md`.
2. Open `ORBITA EXPLORER - English.pdf` for the original project presentation.
3. Play `index.html`.
4. Read the files in `Documentação/` for technical and scientific details.
5. Review `Referências/` for sources and credits.
6. Visit `Development Notes/` to follow post-event development updates and programming progress, and play the final version (`Orbit_Explorer_Final_Version.html`).

## Team

**Orbit Sprint**

This repository is part of the team's NASA Space Apps Challenge project work. Please refer to the presentation and team documentation for the team's project framing and contributor information.

---

*ORbit Explorer — Because every colony deserves a plan to survive.*
