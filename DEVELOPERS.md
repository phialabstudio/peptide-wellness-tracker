# GLP-1 Wellness Tracker — Developer Documentation

User-facing documentation is in [README.md](README.md).

## Architecture at a glance

Intentionally a **single-file, no-build, no-backend** app. The entire application is one `index.html` (~4,300 lines, ~240KB) containing markup, styles, and vanilla JavaScript. No framework, no bundler, no transpile step, no server-side code.

| Concern | Choice |
|---|---|
| Framework | None — vanilla JS, global `app` object |
| Build step | None — ship `index.html` as-is |
| Persistence | `localStorage` (a single JSON data blob, `dataVersion: 2`) |
| Offline | Service worker (`sw.js`) with a precached app shell |
| Backend | None — fully client-side |
| OCR | Tesseract.js, on-device |
| Hosting | Vercel, auto-deployed from GitHub |

Rationale: zero hosting cost, no backend attack surface, no health data leaving the device (a privacy advantage), instant deploys. The cost is that all state, migrations, and backups are the client's responsibility.

## Project structure

```
/
├── index.html          # The entire app: HTML + CSS + JS
├── sw.js               # Service worker (offline caching)
├── manifest.json       # PWA manifest (name, icons, theme)
├── body-map.jpg        # Extracted body-map image (cached asset, not inlined)
├── icon-192.png / icon-512.png / icon-maskable-512.png
├── apple-touch-icon.png / favicon.ico / favicon-*.png
├── README.md           # User documentation
└── DEVELOPERS.md       # This file
```

The body-map image was extracted out of `index.html` into a separately cached asset, cutting the HTML from ~371KB to ~240KB. Keep large binaries out of the HTML and let the service worker cache them.

## Data model

All user data lives in `localStorage` as a single JSON blob carrying `dataVersion: 2` (a migration hook for future schema changes). It holds dose logs, weight/body-composition entries, meal logs (protein/calories/macros + meal type), hydration, exercise (incl. heart rate), side effects, mood, measurements, reminders, the medication list (`peptideList` internally), and settings.

> **Naming note:** internal identifiers still use "peptide" (`peptideList`, `peptideLogs`, `PeptideTrackerApp`, the `peptideTrackerData` storage key) from before the rebrand. All user-facing text says "medication"/"injection". Do **not** rename the storage key — it would orphan every existing user's data. The other identifiers are safe to rename only in a deliberate, tested refactor; there is no user-facing benefit.

Conventions to respect:

- **Always merge stored data over defaults on load.** Older blobs won't have every field; missing fields must fall back to defaults or the app can crash on restore. The load path already does this — preserve it.
- **Unit preferences are real, persisted preferences.** Weight is kg/lbs (`settings.units`); protein display is g/oz (`settings.proteinDisplayUnit`, defaulting from weight unit: lbs→oz, kg→g); hydration has its own unit. When a unit changes, stored *values* must be converted using the OZ constant (28.3495) — not merely relabeled.
- **Dates are LOCAL, not UTC.** The `today()` helper builds `YYYY-MM-DD` from local date parts. Never replace it with `toISOString().slice(0,10)` — that returns the UTC date, which put US users' evening entries on tomorrow's date (a real shipped bug, fixed July 2026). All date comparisons and the reminder ticker use the same local convention.
- **Escape all user-entered strings with `esc()`** before inserting them into the DOM. Custom medication names and reminder labels are user input and are escaped at every render sink, including the reminder popup's `innerHTML`. Keep it that way for any new sink.

## Key subsystems

**Backup / restore.** Export serializes the full blob to a download (`glp1-tracker-<date>.json`). Import **validates structure before overwriting**, stashes a recovery copy, and supports undo-restore. Never write a restore path that overwrites live data without validating and stashing first.

**On-device OCR (scan).** Tesseract.js reads clinic scale reports from a photo/screenshot. The parser recovers decimals OCR drops (e.g. `815kg` → `81.5 kg`), applies lbs conversion, and extracts weight, body fat %, skeletal muscle %, muscle mass, and visceral fat. Extracted values **pre-fill the form for confirmation** — never saved silently.

**Doctor Summary.** Builds a printable summary from the blob. Unit handling here has bitten before (protein goal once rendered ≈4g instead of 120g for lbs users) — re-check this output after any unit-logic change.

**Protein / meal logging.** `setProteinUnit()` toggles g/oz display; `setChipMealType()` + `_defaultChipMealType()` set meal type (defaulting by hour of day). Quick-add chips store protein internally in grams regardless of display unit.

**Storage quota guard.** `save()` guards against `localStorage` quota errors so a full store fails gracefully instead of silently losing data.

**Reminders.** Custom reminder labels + popup/pill UI, surfaced via the bell button in the header. The ticker (`tickReminders`) fires on local time and dedupes per-minute via `lastFired`.

## Theme / palette (actual CSS variables)

Defined in `:root` at the top of `index.html`:

| Variable | Value | Role |
|---|---|---|
| `--primary` | `#B5697A` | Rose — primary brand |
| `--primary-light` | `#E8C5CC` | |
| `--primary-dark` | `#8E4A59` | Hover / emphasis |
| `--secondary` | `#EAE6F5` | Soft lilac surface |
| `--tertiary` | `#C9884A` | Amber accent |
| `--neutral` | `#F7F4F1` | Cream background |
| `--text-dark` | `#2D2834` | |
| `--text-mid` | `#5A5570` | |
| `--text-light` | `#8A8BA0` | |
| `--border` | `#EBE6EE` | |

Typography: **Plus Jakarta Sans**. Studio: **Phia Lab Studio**.

## Running locally

No build step — serve the folder with any static server:

```bash
python3 -m http.server 8000
# or
npx serve .
```

Open `http://localhost:8000`. Service workers and PWA features need `https://` or `localhost` — they won't work from a `file://` URL.

## Deployment

Pushes to the connected GitHub repo auto-deploy to Vercel. Because the app is static, a deploy is effectively publishing the updated `index.html` + assets.

**Service-worker cache versioning:** `sw.js` uses a `CACHE_NAME` (currently `glp1-tracker-v4`). It is **network-first for the page** (newest deploy shows immediately online, cache is the offline fallback) and **cache-first for static assets** (icons, manifest, body-map). **Bump `CACHE_NAME` on any deploy that changes icons, the manifest, or cached static assets**, or users will keep the stale cached copies.

There's no server state to migrate — but there **is** client state, so treat any change to the `localStorage` schema as a migration: bump `dataVersion` and make sure the load path handles data written by older versions.

## Pre-flight checklist (before editing storage, units, or dates)

- [ ] Does the load path still merge over defaults for every new field?
- [ ] If a unit changed, are stored values *converted* (OZ = 28.3495), not just relabeled?
- [ ] Are all dates still built from **local** date parts (never `toISOString`)?
- [ ] Does the Doctor Summary render the field in the correct unit?
- [ ] Are all new user-entered strings HTML-escaped with `esc()`?
- [ ] Does restore still validate + stash before overwriting?
- [ ] Did you bump `CACHE_NAME` if cached assets/manifest changed?
- [ ] Did you bump `dataVersion` if the schema changed?
