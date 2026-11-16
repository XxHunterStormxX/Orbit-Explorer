# Implementation Status and Limitations

## Implemented in the current prototype

- Single-page HTML application containing its own CSS and JavaScript.
- Browser-based interface; no separate installation is required for the prototype.
- Colony resource and crew-management mechanics.
- Food, water, oxygen, energy and science systems.
- Crew/population, health and morale indicators.
- Construction, upgrades and research-related progression.
- Explorer and Astronaut difficulty modes.
- Simulated operational and space-weather events.
- NASA DONKI CME Analysis panel with a live API request and a fallback state when the request is unavailable.
- Links to NASA DONKI and NASA OSDR as external references.

## Not implemented or not demonstrated as complete

- OSDR data is not queried directly by the game.
- DONKI data does not currently drive or modify the simulated events or colony state.
- The game does not provide a validated Mars weather or radiation forecast.
- The game does not model a complete engineering-grade life-support system.
- No user study or measured learning-outcome evaluation is included in the materials reviewed.
- The presentation mentions reports and browser auto-save. These should only be claimed as working features if the team verifies them in the submitted build. The project should not claim cloud saving or cross-device synchronization.
- No formal accessibility audit, performance benchmark or compatibility test report is included.

## Known scientific communication safeguards

- Treat the Base Ares Planitia location and colony as fictional.
- Label random events as simulated scenarios, not live NASA alerts.
- Label the radiation indicator as a game value, not a real exposure measurement.
- Label a DONKI speed value as CME speed, not solar-wind speed.
- Keep the NASA data panel separate from the game simulation unless a future implementation explicitly connects them using a documented scientific method.

## Suggested future work

1. Test the game in current desktop and mobile browsers.
2. Verify each button, resource change, event, upgrade and difficulty mode.
3. Replace the NASA DEMO_KEY with a properly managed API key if required for reliable public use; do not publish private keys in client-side code.
4. Add source notes for the scientific assumptions used to choose game rates and event effects.
5. If live data is intended to influence gameplay, define and document the transformation from the NASA dataset to a game event, including limitations and uncertainty.
6. Conduct playtests with the intended age group and record feedback before making claims about measured educational impact.
