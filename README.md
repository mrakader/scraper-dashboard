# scraper-dashboard

Mobile-first status dashboard for the 6 SA-retailer scrapers (Mr Price, TFG,
bash-mens, Superbalist, Evolve, Fashion Fusion).

Live at: **https://mrakader.github.io/scraper-dashboard/**

## How it works

Single static `index.html`. On first visit it prompts for a fine-grained
GitHub PAT (read-only access to the 6 scraper repos). Token is stored only
in browser `localStorage` — never sent anywhere except `api.github.com`.

The page fetches the latest workflow run + commit for each repo every
60 seconds (and when the tab regains focus). Tap a card to jump to that
repo's Actions tab.

## Setup (one-time, ~2 minutes)

1. Open the dashboard URL
2. Click the PAT setup link → github.com/settings/personal-access-tokens/new
3. Token name: `scraper-dashboard`
4. Expiration: 1 year
5. Repository access → Selected repositories → pick all 6 scrapers
6. Permissions → Repository → Actions: **Read**, Contents: **Read**, Metadata: **Read**
7. Generate, copy, paste back into the dashboard, click Save

Done. The same token works on phone and desktop — paste it once per device.
