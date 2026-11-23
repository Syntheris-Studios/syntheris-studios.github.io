# Syntheris Studios — new static site (Phase 1 staging)

Static site for syntheris-studios.com, built to replace the Wix site. This folder
becomes the GitHub Pages repo content at deploy time. **Staging only — nothing
here is published yet.**

## Structure

- `index.html` — Home
- `about/` — About the artist (bio migrated from Wix, refreshed)
- `software/` — Public software releases
  - `software/continuum/` — Syntheris Continuum V5.1.0 page, adapted as-designed from the launch space
- `journal/` — Pi3rre's Creative Corner, 8 migrated posts (Apr–Aug 2025)
- `publishing/` — Publishing arm + generic comic-universe teaser (no universe name, no imprint name)
- `contact/` — Enquiries only (no services menu, no prices, no booking)
- `legal/` — Privacy, Terms, Refund, Shipping, Accessibility (written fresh Nov 22; see Migration notes)
- `redirects.md` — old Wix URL → new URL map for the DNS switch (documentation only)
- `assets/css/site.css` — shared stylesheet (Continuum design tokens)
- `assets/img/` — optimized images (EXIF stripped, max 1600px wide, JPEG)
- `assets/continuum/` — Continuum brand assets (wordmark, C mark, favicon)
- `sitemap.xml`

## Brand identity — official logo files (swapped in Nov 22)

Pierre sent the clean logo files Nov 22. All six live in `assets/img/` as
transparent PNGs: the black backgrounds were converted to transparency with
luminance-to-alpha (a black-crush curve for the two holographic variants, whose
backgrounds are dark blue rather than pure black), so no black rectangles show
on the site's near-black navy. EXIF stripped, resized for web.

- **Header wordmark** (`wordmark-chrome.png`, 1200×500): liquid chrome
  "SYNTHERIS STUDIOS" with the brushstroke through the H, generated Nov 22.
  Site header on every page (44px tall, next to the emblem). Black background
  converted to transparency with a black-crush alpha ramp (lo=6, hi=48) so
  the dark interior shading of the chrome stays solid metal; verified
  composited on the site navy (#080c18) at full size and at header size.
- **Wordmark master** (`wordmark-official.png`, 1200×400): the official hi-res
  2024 final wordmark, white "SYNTHERIS STUDIOS" with the paint-splatter H.
  Kept in assets as the master; no longer the header (replaced by the chrome
  version Nov 22 per Pierre's call).
- **Emblem** (`emblem-cyan.png`, 400×400; `favicon.png`, 64×64): the glowing
  cyan S swirl (the X avatar). Header mark, home hero, publishing teaser,
  footer, and favicon. Replaces the screenshot-crop `emblem.png` used in the
  first staging build.
- **Hologram wordmark** (`wordmark-hologram.png`, 720×520): neon cyan
  holographic wordmark, cropped to content. Home hero centerpiece.
- **Chrome emblem** (`emblem-chrome.png`, 1000×1000): chrome/silver S swirl.
  About page, under the portrait ("The studio mark").
- **Holographic portrait** (`wordmark-holographic.png`, 800×1200): holographic
  glitch wordmark, portrait. About page, in the portrait column under the
  chrome mark ("The studio wordmark — holographic treatment").

Sources (originals, unmodified): `workspace/user/media_library/image/` —
`hiresLOGO2024-syntheris-final.jpg`, `xn4pTBoA_400x400.jpg`,
`ComfyUI_temp_lghsb_00002.jpg`, `Futuristic_Syntheris_Studios_Hologram.png`,
`Syntheris_Studios_Holographic_Vision.png`; chrome header source
`workspace/imagine_media/media-generation-syntheris-logo-chrome-0-ef4c4567-e93a-4ec1-aa01-7771cff7a71c.webp`.

## Promo imagery (placed Nov 22)

Seven promo images Pierre shared Nov 22, all in `assets/img/` (EXIF
stripped, max 1600px on the long edge, JPEG quality 82). The two
landscape/portrait pairs use `<picture>` with a 720px media breakpoint so
the right orientation serves per viewport; the assembler rewrites `srcset`
paths the same way it rewrites `src` (see `build_staging.py`).

- **Home hero** — `promo-station-landscape.jpg` (1600×893) on desktop,
  `promo-station-portrait.jpg` (1195×1600) on mobile: the studio station in
  orbit above Earth. Banner figure at the foot of the hero.
- **Home statement** — `promo-we-build-worlds.jpg` (1195×1600): "WE BUILD
  WORLDS / Comics. Games. AI. Robotics." Full-width statement section
  between "What we make" and the Journal preview. The subline is approved
  as-is — video games and robotics are future lines.
- **Home closer** — `promo-future-written.jpg` (1600×900, 16:9): "THE FUTURE IS
  BEING WRITTEN" over a tech-corridor background. Final beat before the
  footer, displayed wide (`.poster-figure.wide`, max 960px). Swapped in
  Nov 23, replacing the portrait version.
- **Publishing teaser** — `promo-signal-crt.jpg` (1600×893) on desktop,
  `promo-signal-glitch.jpg` (1195×1600) on mobile: "SIGNAL ACQUIRED".
  Banner above the teaser card.
- **About** — `promo-robot-hand.jpg` (1195×1600): chrome robotic hand with
  the studio name etched on it. Figure in the main column (NOT the portrait
  column, which already stacks three figures), captioned with the studio's
  AI/robotics work.

Sources (originals, unmodified): `workspace/user/media_library/image/` —
`Deep_space___202604091909.jpg`, `Deep_space___202604091859.jpg`,
`A_glitchy_digital_202604091910.jpg`, `A_glitchy_digital_202604091900.jpg`,
`A_recruitment_hiring_poster_202604091900.jpg`,
`A_corporate_launch_202604091900.jpg`, `A_sleek_robotic_202604091859.jpg`.

## Migration notes

- The Wix "template" post slug (`/post/template-the-ultimate-guide-to-writing-the-ultimate-guide`)
  actually held the real PC-build article — it migrates under the clean slug
  `journal/custom-pc-build-for-ai/`. There was no template content to drop.
- Post titles kept verbatim as published, including the typo
  "PortraitureThrough" in the Next Level post and the double "The" in its
  "The Transcendent Syntheris" case-study heading. Pierre's call whether to fix.
- The PC-build post uses its blog-index title; its page H1 on Wix was the
  draft-like "guide custom pc build for Ai".
- Post dates are Montreal-local (America/Toronto) conversions of the published
  timestamps: the Next Level post shows July 13, 2025 (published Jul 14 03:44
  UTC = Jul 13 23:44 EDT); the Triumph post shows July 10, 2025.
- The interpolation post's closing CTA now links to the Continuum page (the
  successor product) instead of the old Wix service page. Its historical
  claims (70% artifact reduction, 95%+ usable footage) are migrated as
  published and flagged for Pierre's review — the Continuum overview treats
  them as not re-certified.
- The "share your experiences below" line in the State of AI Art post refers
  to the old Wix comments section, which the new site does not have. Kept
  verbatim; Pierre's call whether to trim it.
- "ChatGPT vs. Human Design." in the same post is a caption line for a
  comparison image that the Wix text fetch did not surface; kept as a
  standalone line. If Pierre has the comparison image, it can be added.
- The State of AI Art post's King Conan case study is migrated as published.
  (The King Conan gallery page itself stays unpublished per Pierre's Nov 16 call.)
- Legal pages (Nov 22): the Wix legal pages were unfilled Wix template
  boilerplate ("how to write your own document", "[enter organization name]"),
  so the five pages were written fresh instead of migrated verbatim — short,
  honest, studio-specific (static site, no cookies/analytics; no online sales
  or shipments yet; accessibility commitment). No address or phone anywhere;
  contact is the studio email only. Revisit with legal counsel at
  incorporation, per the migration plan.
- Social links (Nov 22): footer on every page carries GitHub, LinkedIn,
  Facebook, Instagram, X (official studio pages, all target="_blank"
  rel="noopener"); the Contact page's follow line lists all four socials.

## Hard constraints honored

- No universe name, no universe titles, no canon anywhere (IP gate).
- The comics publishing imprint name is NOT used anywhere on the site — the imprint is not announced and not trademarked. Refer to it only generically ("the studio's own publishing imprint") until Pierre says otherwise. (The imprint name itself is deliberately not written in this file: this folder ships as the public repo.)
- No street address or phone number anywhere. City only: "Montreal, Canada".
- No private-suite apps, no celebrity material, no book drafts.
- No shop/commerce, no prices, no booking flow, no contact form (no backend).
- Designer toys described generically — no figure names (IP gate).
- The animation/film imprint name is not used (not confirmed public-safe).
- No Work/portfolio page in Phase 1 (no real projects ready).

## Local preview

Serve the folder statically, e.g. `python3 -m http.server 8000` from this
directory, then open http://localhost:8000/. All links are relative, so the
site also works from any subpath.

## Staging preview

The preview space (`syntheris-studios-staging-site`) is a single-file assembly
of these pages, built by `build_staging.py` (durable copy in this folder;
`/tmp/build_staging.py` is the working copy) — the artifact runtime serves
only index.html + assets/, so the assembler inlines all 20 pages with a
router. Nov 22: hash-only routing proved dead in the space viewer (clicks did
nothing even though the audit probe navigated fine); the router now uses
direct delegated click handling (preventDefault + show() directly, hash
updated via history.replaceState) alongside hashchange, with a home fallback
for unknown anchor hashes. Verify nav by real clicks in the rebuilt preview,
never by hash assignment alone.
