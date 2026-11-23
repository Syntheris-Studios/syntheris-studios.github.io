# Redirect map — Wix → new site

Documentation for the DNS-switch step (launch target: Tuesday morning
Nov 24, 2026). Old URLs are from the live Wix sitemaps, fetched Nov 22, 2026.
Domain registrar: Wix (DNS managed in Wix; preserve the Google Workspace
MX/TXT records exactly at switch time). New host: GitHub Pages.

## The map

All paths are relative to `https://www.syntheris-studios.com`.

### Pages

| Old Wix URL | New URL | Note |
|---|---|---|
| `/` | `/` | Unchanged |
| `/about-2` | `/about/` | |
| `/blog` | `/journal/` | |
| `/services-4` | `/contact/` | Services dropped as pages; enquiries only |
| `/service-page/pre-production-for-film` | `/contact/` | Service dropped |
| `/service-page/brand-design-and-ip-development` | `/contact/` | Service dropped |
| `/service-page/generative-ai-consulting` | `/contact/` | Service dropped; consulting is enquiry-only |
| `/portfolio` | `/` | Portfolio dropped; no Work page yet |
| `/portfolio-collections/my-portfolio/project-title-6` | `/` | Visions of the Future dropped |
| `/book-online` | `/contact/` | No bookings |
| `/portfolio-collections/my-portfolio/project-title-5` | — | No redirect: already 404 on Wix since Nov 16 (King Conan stays unpublished) |

### Blog posts (8)

| Old Wix URL | New URL |
|---|---|
| `/post/the-state-of-ai-art-elevating-creativity-through-human-ai-collaboration` | `/journal/state-of-ai-art/` |
| `/post/the-great-cinema-format-wars-why-we-lost-more-than-we-gained` | `/journal/cinema-format-wars/` |
| `/post/template-the-ultimate-guide-to-writing-the-ultimate-guide` | `/journal/custom-pc-build-for-ai/` |
| `/post/an-artist-s-triumph-how-creative-thinking-conquered-a-technical-mountain` | `/journal/artists-triumph/` |
| `/post/the-human-creative-advantage-why-ai-generated-content-will-never-replace-strategic-artistic-vision` | `/journal/human-creative-advantage/` |
| `/post/the-next-level-art-process-redefining-ai-assisted-portraiturethrough-11-stage-synthesis` | `/journal/next-level-art-process/` |
| `/post/the-end-of-amateur-video-interpolation-how-syntheris-video-processor-just-made-every-competitor-obs` | `/journal/end-of-amateur-video-interpolation/` |
| `/post/my-favorite-tools-blending-tradition-technology-and-ai-in-art` | `/journal/my-favorite-tools/` |

Notes: the "template" slug held the real PC-build article (see README). The
interpolation post's Wix slug is genuinely truncated at "obs" — verified live
Nov 22; the full "...obsolete" URL returns 404.

### Legal pages (5)

| Old Wix URL | New URL |
|---|---|
| `/english-privacy-policy` | `/legal/privacy/` |
| `/english-terms-conditions` | `/legal/terms/` |
| `/english-refund-policy` | `/legal/refund/` |
| `/english-shipping-policy` | `/legal/shipping/` |
| `/accessibility-statement` | `/legal/accessibility/` |

## How redirects work on GitHub Pages

GitHub Pages is static hosting: no server config, no `.htaccess`, no true
301 redirects. The practical approach is **meta-refresh stub pages**: for
each old URL, publish a minimal HTML page at the old path containing
`<meta http-equiv="refresh" content="0; url=/new-path/">`, a plain link
("This page has moved…"), and a canonical link to the new URL. Google
treats an instant meta refresh largely like a redirect for ranking
purposes, though it is weaker than a true 301; visitors land on the right
page either way.

**Recommendation:** generate stub pages from this table at deploy time (a
small script can generate all of them from the rows above). Stubs matter
most for the 8 blog posts, `/about-2`, `/blog`, and the 5 legal pages —
those are the indexed URLs with inbound links. For the dropped pages
(portfolio, services, book-online), stubs pointing at `/` or `/contact/`
are cheap and better than 404s. If true 301 redirects ever become a
requirement, the fix is moving hosts to Netlify or Cloudflare Pages (free,
same static deploy, real redirect rules via a `_redirects` file) — not a
reason to delay the launch.

After the switch: verify a sample of old URLs lands on the new pages, and
submit the new `sitemap.xml` to Google Search Console so the new structure
is re-crawled.
