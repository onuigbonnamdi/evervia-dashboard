# Evervia Web Dashboards

Public-facing sites for the two Evervia Innovations products, each with live UK grid data and AI forecasts rendered in the browser.

| Site | Folder | Audience | Live |
|---|---|---|---|
| Evervia | `evervia/` | Businesses and public sector (B2B) | [evervia.co.uk](https://evervia.co.uk) |
| GridSense | `gridsense/` | Home users and developers (B2C) | [gridsense.evervia.co.uk](https://gridsense.evervia.co.uk) |

## Evervia

Product site for Evervia, an AI energy intelligence platform for SMEs, retail chains, schools, hospitality groups, property managers, and councils.

- Live UK grid panel with real-time demand and a 48 hour forecast
- Positioning around cost and carbon impact, and the move from energy reporting to autonomous optimisation
- Tiered offer across SMEs (Core), multi-site operators (Pro), and the public sector (Pilot and Council)
- Early pilot programme sign-up

## GridSense

Landing page and live demo for the GridSense forecasting API.

- Live UK national demand chart from Elexon BMRS data
- 48 hour AI demand forecast (Random Forest with Open-Meteo weather regressors, validated R² 0.977)
- API overview: REST endpoints, Supabase persistence, CSV and bulk export
- Pricing tiers and waitlist capture

## How it works

```
Elexon BMRS + Open-Meteo
        |
        v
Forecasting API (see verdant-forecast-api)  --->  Supabase (Postgres)
        |
        v
Static HTML dashboards (Chart.js)
```

Both sites are single-file HTML pages with no build step. Charts are drawn with Chart.js and data is fetched live from Supabase and the Evervia forecasting API.

## Note on versions

This repo holds earlier static versions of both sites. Since then, the GridSense app has moved to Next.js ([gridsense-nextjs](https://github.com/onuigbonnamdi/gridsense-nextjs)), and early-access sign-ups on the live Evervia site now run through a Tally to n8n pipeline instead of a direct database form.

## Tech stack

- HTML, CSS, vanilla JavaScript
- Chart.js 4
- Supabase
- Open-Meteo weather API
- Evervia forecasting API

## Running locally

Open either `index.html` in a browser, or serve the folder:

```bash
npx serve evervia     # or: npx serve gridsense
```

## Related repos

- [verdant-forecast-api](https://github.com/onuigbonnamdi/verdant-forecast-api): the demand forecasting service
- [gridsense-nextjs](https://github.com/onuigbonnamdi/gridsense-nextjs): the full GridSense web app

## Author

**Nnamdi Onuigbo**, Founder and AI Systems Engineer, Evervia Innovations Ltd
