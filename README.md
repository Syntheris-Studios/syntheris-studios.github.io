# Syntheris Studios — website

The public website for **syntheris-studios.com**, hosted on GitHub Pages
under the Syntheris-Studios org. Static HTML/CSS only — no build step, no
backend, no JavaScript framework. The site replaced the old Wix site in
November 2026.

Live at: https://syntheris-studios.com
(also served at https://syntheris-studios.github.io)

## Deploy

Push to `main`. GitHub Pages deploys from the `main` branch, root folder,
automatically. No build, no CI.

- `CNAME` — the custom domain (`syntheris-studios.com`). Do not delete it;
  without it the custom domain stops working.
- `.nojekyll` — tells GitHub Pages to serve the files as-is (no Jekyll).
- The custom domain + HTTPS are configured in the repo's
  Settings → Pages. "Enforce HTTPS" is on once the certificate is issued.

## Structure

20 pages:

- `index.html` — Home
- `about/` — About the artist and the studio
- `software/` — Public software releases
  - `software/continuum/` — Syntheris Continuum (frame interpolation)
- `journal/` — Blog, 8 posts (Apr–Aug 2025)
- `publishing/` — Publishing arm + generic comic-universe teaser
- `contact/` — Enquiries only (no services menu, no prices, no booking)
- `legal/` — Privacy, Terms, Refund, Shipping, Accessibility
- `assets/css/site.css` — shared stylesheet
- `assets/img/` — images (EXIF stripped, max 1600px, JPEG/PNG)
- `assets/continuum/` — Continuum brand assets
- `sitemap.xml`
- `redirects.md` — old Wix URL → new URL map (documentation)

## Redirect stubs

GitHub Pages has no server redirects, so the old Wix URLs are covered by
minimal meta-refresh stub pages at the old paths (`about-2/`, `blog/`,
`post/<slug>/`, the old legal slugs, the dropped service/portfolio pages).
Each stub refreshes instantly to the new URL and carries a canonical link.
See `redirects.md` for the full map. One old URL is intentionally NOT
redirected: the unpublished King Conan gallery page, which has been a 404
since Nov 16, 2026 and stays unpublished.

## Staging preview

Before anything is pushed here, changes are previewed in the Muse staging
space (`syntheris-studios-staging-site`), a single-file assembly of these
pages with a router. The staging copy is the review surface; this repo is
the deploy target. Nothing goes live until Pierre approves it in staging.

## Brand

Header wordmark: liquid chrome "SYNTHERIS STUDIOS" (`wordmark-chrome.png`).
The official 2024 final wordmark is kept in assets as the master
(`wordmark-official.png`). Emblem: glowing cyan S swirl (`emblem-cyan.png`).
Logo files are studio brand assets — all rights reserved, not open source.

## IP gate — read before adding content

This repo is public. The following must NEVER appear on the site until
Pierre explicitly says otherwise:

- The comic book universe name, any project titles, or any canon.
- The comics publishing imprint name (not announced, not trademarked).
  Refer to it only generically ("the studio's own publishing imprint").
- The animation/film imprint name.
- Any private-suite app (the production tools are private arsenal).
- Any celebrity material or book drafts.
- Any street address or phone number. City only: "Montreal, Canada".
- No shop/commerce, no prices, no booking flow, no contact form.

Designer toys are described generically — no figure names.

## Updates

Tell RoboXor what to change; edits are made, previewed in staging, and
deployed from there. No editor UI to fight.
