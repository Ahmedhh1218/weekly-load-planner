# Weekly Load Planner

Plan your week by dragging blocks onto a timeline, see hours, effort and spare capacity, and track income and expenses. Free, private (no account, data stays on the device) and installable on iPhone, Android and desktop as a progressive web app.

Live site: https://ahmedhh1218.github.io/weekly-load-planner/

## What is in here

```
index.html         Landing page with install instructions
privacy.html       Privacy note
app/               The planner (single page app, vanilla JS, no build step)
  index.html       App source: markup, styles and script in one file
  sw.js            Service worker (offline cache and update flow)
  manifest.webmanifest
  icons/, fonts/
assets/            Landing page screenshots
.github/workflows  Deploys to GitHub Pages on every push to main
```

## Run it locally

Service workers need http, not a file path:

```
python3 -m http.server 8000
```

Then open http://localhost:8000/ (landing) or http://localhost:8000/app/ (app).

## Releasing an update

1. Make your change in `app/index.html`.
2. Bump the version in three places: `APP_VERSION` in `app/index.html`, `VERSION` in `app/sw.js`, and add an entry to `CHANGELOG.md` (and the list on `index.html`).
3. Push to `main`. The workflow checks the two versions match, then deploys.

Installed copies notice the changed `sw.js`, download the new version in the background and show "A new version is ready" with a Reload button. User data is stored separately (localStorage keys beginning `wl-`) and is not touched by an update. If a release changes the stored data shape, add a migration in `normalize` / `normMoney` so old data still loads.

## Data and backup

Everything lives in the browser's localStorage. The Backup button writes one JSON file with all plans and the money data; Restore can replace or merge. That file is also how you move between devices.

## Licence

MIT, see `LICENSE`. Exchange rates by [ExchangeRate-API](https://www.exchangerate-api.com).
