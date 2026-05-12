# scraper-dashboard

A mobile-first status + trigger dashboard for the 6 SA-retailer scrapers
(Mr Price, TFG, bash-mens, Superbalist, Evolve, Fashion Fusion).

Live: **https://mrakader.github.io/scraper-dashboard/**

## What it does

- Shows each scraper's last-run status, time, and duration
- One-tap to trigger any scraper, or all 6 at once
- Cancel an in-flight run
- Auto-refreshes every 60 seconds while open; instantly on tab focus
- Installs to home screen on iOS/Android (Safari → Share → Add to Home Screen)

## Design lens

Built with a clinical / behavioural-psychology + neurology mindset:

- **Pure-black OLED background** reduces retinal load on phones
- **Grouped iOS lists** chunk information (Miller's 7±2) so 6 retailers
  stay legible at a glance
- **44 px minimum tap targets** (Fitts's law, iOS HIG)
- **Redundant status encoding** (colour dot + word label) so colour-vision
  differences don't lose the signal
- **Single accent colour** (system blue) for actions; status uses only
  semantic colours (green / red / orange / gray) to reduce ambiguity
- **Animations <300 ms** with a single spring curve — present but not
  attention-stealing

## Setup (one-time, ~2 minutes)

1. Open https://github.com/settings/personal-access-tokens/new
2. Token name: `scraper-dashboard`, expiration **1 year**
3. Repository access → **Only select repositories** → pick all 6 scrapers:
   - `mrakader/scraper`
   - `mrakader/tfg-scraper`
   - `mrakader/bash-mens-scraper`
   - `mrakader/superbalist-scraper`
   - `mrakader/evolve-scraper`
   - `mrakader/fashion-fusion-scraper`
4. Permissions → **Repository** →
   - **Actions: Read and write** (read = status, write = trigger)
   - **Contents: Read** (for latest commit info)
   - **Metadata: Read** (mandatory, set automatically)
5. Generate, copy, paste into the dashboard, tap **Save & continue**

Token is stored only in your browser's `localStorage`; never sent anywhere
except `api.github.com`.

### Upgrading an existing token

If you set up the dashboard before triggers were added, your token has
read-only Actions permission. Open https://github.com/settings/personal-access-tokens,
edit the `scraper-dashboard` token, change **Actions** from "Read" to
"Read and write", and save. The dashboard will start working with triggers
immediately — no re-paste needed.
