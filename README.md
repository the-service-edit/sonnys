# Sonny's — rebuilt site

```
index.html
assets/hero-960|1440|1920|2560.webp   ← hero, responsive
assets/hero-960|1440|1920|2560.jpg    ← fallback for old browsers
assets/og-sonnys.jpg                  ← 1200×630 social preview
fonts/anybody-variable.woff2          ← the typeface, self-hosted
fonts/Anybody-OFL.txt                 ← its licence (SIL OFL, free commercially)
wordmark.svg                          ← the logo, standalone
```

No build step, no dependencies, no framework. Keep `index.html` and `fonts/`
together and it runs anywhere — GitHub Pages, Netlify, a folder on a desktop.

---

## ⚠ PRICE CONFLICT — RESOLVE FIRST

The printed menu you sent says **THREE COURSE CHEFS SELECTION / 75pp**.
Their website says **$85**. I've used **75** on the page and in the schema because
the printed card is the more likely current source — but confirm before this goes
live. It's in two places: the `.mset` line in the Menu section, and
`hasMenuSection → Chef's Selection` in the JSON-LD.

## MENU — transcribed from your photos

The full food and cocktail lists are now on the page and in the structured data
(37 items with prices). Transcribed by eye from the menu photographs, so **proof
every line against the current card** before launch — dish names, spellings and
prices. Their house style of slash-separated dishes (`fresh oyster / fingerlime`)
is preserved; prices are bare numbers as printed, with one "All prices in AUD" note.

**Wine is deliberately not reproduced.** You only sent one page (sparkling, white,
orange) and a list that long changes constantly — publishing it creates a staleness
problem and a maintenance job nobody will do. The page carries a short, accurate
description and tells people to ask. If the client wants the list online, the right
answer is a dated PDF they replace, not 60 rows of HTML.

Not on the page because they weren't in the photos: red wine, dessert wine, spirits,
and whatever the oyster `6 / 30 / 55` and cheese `16 / 30 / 40` tiers actually mean
(1/6/12? one/three/five?). Worth labelling those on the site once you know.

## CONFIRM BEFORE LAUNCH

These came from third-party sources (WA Good Food Guide, Broadsheet), not from the
venue. Every one is on the page — get a yes from Sonny's before it goes live.

| # | Claim on the page | Source | Action |
|---|---|---|---|
| 1 | "The name comes from a rescue greyhound" | WA Good Food Guide | Confirm, or cut the line — it now sits as a small aside, not a headline |
| 2 | Head chef **Sofika Boulton** | Both | Confirm still current |
| 3 | Wheelchair accessible | WAGFG listing | Confirm |
| 4 | Dog friendly outside, bowls at the door | WAGFG listing | Confirm |
| 5 | Outdoor seating out front | Photo + WAGFG | Confirm |
| 6 | Award: Winner, Best Bar Dining, WA Good Food Guide 2025 | wagoodfoodguide.com/award/best-bar-dining-2025 | Verified winner. Confirm wording they prefer |
| 7 | `priceRange: "$$$"` in schema | Inferred from the set menu | Confirm or change |
| 8 | Wine described as "small growers, leftfield varieties, selection by the glass" | Broadsheet + the wine list photo | Confirm the wording |

## CONFLICTS IN THE CURRENT SITE — resolved as follows

- **Hours.** Home page said "Wed & Thu 4pm–late, Fri/Sat/Sun 12pm–late". Contact page
  said Wed–Thu 4–10pm, Fri–Sat 12–late, Sun 12–9pm. I used the Contact page version
  (more specific). Confirm.
- **Address.** Visible copy says 126**A** Hobart St; their old schema said 126 Hobart
  Street. I used 126A everywhere. Confirm.
- **"Late"** on Fri/Sat has no real closing time. Schema needs one, so it's set to
  `00:00`. Replace with the actual licensed close.

## STILL MISSING — ask the venue

- **A phone number.** There isn't one anywhere on the current site. A bar with no
  phone number loses walk-in and same-day bookings. Get one, add it to the Contact
  column and to `telephone` in the JSON-LD.
- **More photography.** Five usable images exist. A site like this wants 10–14.
- **A real favicon** (currently an inline SVG placeholder).
- Parking / walk-in policy / group bookings / corkage — add as an FAQ block later and
  mark it up as `FAQPage`. High value for AI answer engines.

## BRAND

- **Blue is `#0058E2`** — sampled directly from the wordmark file you sent. It carries
  the primary CTAs, hover states and the open-now dot. Bone on blue measures 4.93:1,
  so button text passes AA.
- **The wordmark is now an inline SVG**, traced from your file and drawn once as a
  `<symbol>`, then referenced three times (header, hero, footer). ~3KB, crisp at any
  size, and it takes its colour from `currentColor` — so it can be bone on dark or
  blue on light with no second asset. This removes the last Wix dependency for the
  logo; they were serving a 321px PNG that softened on retina.
- `wordmark.svg` is included separately if you want it for anything else.
- Hero is centre-composed: wordmark, positioning line, both CTAs and the live
  open/closed line stacked and centred, with the award on a quiet rail at the base.
  The header wordmark is hidden at the top of the page and fades in once you scroll,
  so the mark never appears twice at once.

## IMAGES

**The hero is self-hosted.** Built from the 3072×2047 original you supplied, cut to
four widths as WebP with JPEG fallbacks, served through `<picture>` + `srcset` and
preloaded at high priority. Largest file a phone will pull is 55KB; a 5K desktop
tops out at 225KB. This is the LCP element, so it's the one that had to be local.

The other four photographs still come from the Wix CDN via Wix's own
`/v1/fill/w_…,h_…,enc_auto/` transform, which generates each `srcset` step on the fly.
They're below the fold and lazy-loaded, so the cost is low — but **before launch**,
pull them down and self-host them alongside the hero for consistency and to remove
the last third-party dependency. Source IDs:

- window seat `ebaa3f_56c5e098728a4288a6fc9ef02135eaa5~mv2.jpg` (1688×3000)
- wood fire `ebaa3f_5470044fb8f54945aaf292906292e9f3~mv2.jpg` (1125×2000)
- desserts `ebaa3f_e133b4cb899d4bb4b7b8c71251ac7c26~mv2.png` (2748×1912)
- exterior `ebaa3f_304a3495242342abaee4a32da35b0f2e~mv2.png` (1366×768 — low res, reshoot)
- wordmark `ebaa3f_509e59dc3caf4f5d974daf21a055a48e~mv2.png`

Full URL: `https://static.wixstatic.com/media/<ID>/v1/fill/w_W,h_H,al_c,q_80,enc_auto/<ID>`

## ⚠ THE VISIT UNDERLAY IS TUNED BLIND

The exterior shot now sits behind the whole Visit section instead of below it.
**I could not fetch that photo to check the result** — it lives on Sonny's Wix CDN and
this sandbox has no egress to it, so every render I did shows the section with the
image missing. The treatment is set from contrast maths, not from looking at it:

```
filter: brightness(.72) contrast(.62) saturate(.55)   /* lifts the dark facade */
scrim:  .80 → .66 → .82 vertical gradient
```

Open it on your machine. Two things to judge:

1. **Is the building actually visible?** The contrast is deliberately compressed to lift
   a dark facade into view without blowing out the sky. If it reads as a flat dark field,
   raise `contrast()` toward `.75` and drop the mid scrim stop toward `.58`.
2. **Does the text still hold?** Against a pure-white test image the underlay peaks at
   grey 66 against a budget of 74, so bone-70 text stays at 4.5:1 — but that's the
   worst case, not the real one. In this section nothing drops below 70% opacity for
   exactly this reason (`.sect--bg` overrides the faint greys).

Send me the exterior photo and I'll dial it in properly. Worth noting it's only
1366×768 — thin for a full-bleed background. A reshoot of the frontage is the real fix.

## CTA SHAPE

Buttons are now fully rounded to pick up the circular bowls in the wordmark. It's a
single token — `--radius` at the top of the CSS. Set it to `10px` if the full pill
reads too soft next to the photography; everything else on the page stays square, so
the curve is reserved for actions and the one Chef's Selection panel.

## TYPE — Anybody

One family across the whole site. Anybody is a variable face (weight 100–900,
**width 50–150**), which is why a single 57KB file covers every register here:

| Where | Setting |
|---|---|
| Headings, menu names, hero line | `font-weight:500` · `font-stretch:108%` · tight tracking |
| Body and UI | `font-weight:400` · `font-stretch:100%` |
| Small uppercase labels | `font-weight:600` · `font-stretch:94%` · `.19em` tracking |

It shares its construction with the SONNYS wordmark — same wide geometric O and S —
so the logo now reads as part of the type system rather than sitting on top of it.
That's the main argument for it. The cost is that it's a display face doing body
work; at 16px it has more personality than a neutral grotesque. Look at the
paragraphs in "The bar" section and decide whether that's right for the client.

Self-hosted rather than pulled from Google Fonts: one request instead of two,
no third-party DNS, no FOUT from a cross-origin stylesheet. Licence is SIL OFL,
so self-hosting and commercial use are both fine.

## TECHNICAL
- Hero composition is tuned to this specific photograph. The motion blur does most of
  the legibility work — there's no sharp detail for the type to destroy — and the scrim
  has a separate, heavier gradient below 760px because the phone crop puts the CTAs
  right on top of a lit plate. The ghost button carries its own translucent fill and
  blur so it holds over any part of the image. **If the hero is ever swapped, re-check
  both gradients** — a sharp, bright-centred photo will fight the centred type.
- Motion: one scroll-reveal primitive + a hero settle. Both disabled under
  `prefers-reduced-motion`.
- Open/closed indicator in the hero computes from `HOURS` in the inline script and
  always resolves in `Australia/Perth`, whatever timezone the visitor is in.
  Hours live in one place — edit `HOURS` and the `<dl>` in the Visit section.
- Schema: `Restaurant` + `WebSite` in one `@graph`, with `hasMenu`, `ReserveAction`,
  `openingHoursSpecification`, `award`, `employee`, `amenityFeature`.
- Booking and gift cards point at the existing NowBookIt account. Nothing to migrate.
- Tested 360 / 390 / 834 / 1280 / 1512. No horizontal overflow, no JS errors,
  zero WCAG AA contrast failures, headings in order, all images have alt text
  and intrinsic dimensions.

## TO DO AFTER DEPLOY

1. Point `sonnysbar.com.au` at the new host; keep `/menu`, `/contact-4`, `/general-9`
   alive as 301s to `/#menu`, `/#visit` and the gift-card URL.
2. Add `robots.txt` + a one-line `sitemap.xml`.
3. Claim/refresh the Google Business Profile with identical NAP + hours — the schema
   and GBP must agree or local ranking suffers.
4. Re-test with PageSpeed Insights on the live domain.
