# Astra Charge Timer

An offline-capable PWA that works out when to defer EV charging so a
Vauxhall Astra Electric reaches its target charge by morning. Enter the
current battery %, pick the charger (granny 2.3 kW, wallbox 7.4 kW, or
custom), and it shows the defer time from now, the start time of day,
and the charging duration.

Everything runs client-side; settings persist in `localStorage`.

## Install on a phone

Open the GitHub Pages URL, then:

- **Android (Chrome):** menu → *Add to Home screen* → *Install*
- **iPhone (Safari):** Share → *Add to Home Screen*

The service worker caches the whole app on first load, so it works with
no connection afterwards.

## Assumptions

Defaults are the Astra Electric: 51 kWh usable battery, ~90%
wall-to-battery charging efficiency. All assumptions (target %, ready-by
time, charger kW, capacity, efficiency) are editable in the app.

## Deploys

Pushes to `main` publish to GitHub Pages via
[deploy.yml](.github/workflows/deploy.yml). When the app changes, bump
the cache version in [sw.js](sw.js) so installed copies pick up the new
version.
