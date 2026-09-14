# clockout-app-web

Landing page for [ClockOut](https://play.google.com/store/apps/details?id=org.clockout), hosted on GitHub Pages.

## Publish it

**Option A — via github.com (no terminal needed)**
1. Go to github.com → **New repository** → name it `clockout-app-web` → Public → Create.
2. On the empty repo page, click **uploading an existing file** and drag in `index.html` (and this `README.md`).
3. Commit to `main`.
4. Go to **Settings → Pages** → under "Build and deployment", set Source to **Deploy from a branch**, Branch: `main`, folder `/ (root)` → Save.
5. Wait ~1 minute, then your site is live at `https://ruzickaond.github.io/clockout-app-web/`.

**Option B — via git**
```bash
mkdir clockout-app-web && cd clockout-app-web
git init
cp /path/to/index.html /path/to/README.md .
git add .
git commit -m "Initial landing page"
git branch -M main
git remote add origin https://github.com/RuzickaOnd/clockout-app-web.git
git push -u origin main
```
Then enable Pages the same way as step 4 above.

## What's in the page

- Sticky nav with anchor links to Ritual / Screens / Details.
- Hero with a Material `Lightbulb` icon and pulsing halo, matching the in-app ritual — dims on scroll, relights back at the top.
- Self-contained "Get it on Google Play" button (no dependency on Google's hotlinked badge image).
- Screenshot strip, feature checklist, and a short privacy note.
- Floating back-to-top button that fades in after scrolling.

## Notes / next steps

- Screenshots are currently hotlinked directly from the Play Store CDN. That works fine on a real domain, but for long-term reliability, consider exporting your own screenshots into an `/assets` folder and swapping the `src` attributes.
- Copy is in English only, matching the primary Play Store listing. The app itself supports Czech — a language toggle would be a natural next step if you want a CZ version of the page.
- Once you have a custom domain, add a `CNAME` file with the domain name at the repo root and point your DNS at GitHub's Pages IPs / `ruzickaond.github.io`.

## Languages

The site is bilingual: English at the root (`/`), Czech under `/cs/`. Visitors whose browser language is Czech get auto-redirected to `/cs/` on first visit; the choice is remembered in `localStorage` after that (manual switch via the EN/CS link in the nav always wins). Both versions share the same screenshots in `/en/`.

When editing copy, keep both `index.html` and `cs/index.html` in sync structurally (same sections/ids), since they share the same CSS and JS inline in each file.
