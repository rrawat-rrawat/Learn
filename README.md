# Nimbus — GA4 / GTM / BigQuery Practice Sandbox

A free, static demo site combining BFSI journeys (savings account, term insurance) and an ecommerce shop, fully instrumented with `dataLayer.push()` events using GA4-recommended event names. No domain, no hosting cost — built to deploy on GitHub Pages.

## What's tracked

See `PROJECT_MANIFEST.json` for the full list of pages and events, and `assets/dataLayer-events.js` for the shared `trackEvent()` helper every page uses.

## Deploy for free in 5 minutes

1. Create a new **public** GitHub repository.
2. Push everything in this folder to the repo's `main` branch.
3. In the repo, go to **Settings → Pages**, set source to `main` (root).
4. Your live site will be at `https://<your-username>.github.io/<repo-name>/` within a few minutes.

## Connect GTM

1. Create a free [Google Tag Manager](https://tagmanager.google.com) container.
2. Add the GTM `<script>`/`<noscript>` snippet to the `<head>`/`<body>` of each HTML page (there's a placeholder comment in `index.html` — copy the same snippet into every page, after `assets/dataLayer-events.js`).
3. Use **Preview mode** in GTM, browse the live site, and you'll see every event listed in `PROJECT_MANIFEST.json` appear in the GTM debug panel as you click around.
4. Build GTM triggers (Custom Event, matching the event name) and tags (GA4 Event tag) for whichever events you want to send to GA4.

## Connect GA4

1. Create a free GA4 property and a GA4 Configuration tag in GTM.
2. Open GA4's **DebugView** (or Realtime) while browsing the site to watch events land.

## Connect BigQuery (optional, still free)

1. In GA4 Admin → BigQuery Links, link a free Google Cloud project (BigQuery's sandbox tier needs no billing account for limited daily-export use).
2. Once linked, GA4 exports raw event data to BigQuery daily — query it directly to learn the GA4 BigQuery export schema.

## Extending this project

This site was built with the `ga4-gtm-bigquery-sandbox` skill. To add new pages or events later, ask Claude to extend the project — it will read `PROJECT_MANIFEST.json` first and follow the existing conventions automatically.
