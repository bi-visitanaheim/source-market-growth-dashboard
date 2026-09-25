# Source Market Growth Dashboard

Visit Anaheim quarterly dashboard for the Communications team: what is driving year-over-year growth and which source markets contribute most. Built on the VA Branded design system.

Powered by Visit Anaheim Business Intelligence Team.

## How it works

- `index.html` is a single static page (no build step). It carries a snapshot of the latest edition so it always renders.
- On load it reads `data/editions/index.json` and every edition listed there, then shows the newest one. An Edition dropdown appears once two or more editions exist.
- Sources: STR (lodging), Visa Destination Insights (visitor spend), Azira (visitation share).

## Quarterly update

1. Add the new edition file to `data/editions/`, named by the latest month of data (for example `2026-10.json`).
2. Add its id to the top of `data/editions/index.json`.
3. Commit and push to `main`. Vercel deploys automatically.

Edition file fields: `id`, `label`, `year`, `prepared`, `loadedAt`, `availMonths`, `markets[]` (`name`, `market`, `band`, `home`, `a25`/`a26` monthly Azira shares, `v25`/`v26` monthly Visa spend for prior/current year), `strm` (monthly STR `sup`, `dem`, `rev` keyed by year), `otherAzira`, `otherVisa`.

## Deploy

Static site. On Vercel: framework preset "Other", no build command, output directory `.` (repository root).
