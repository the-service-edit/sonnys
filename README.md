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

## VERSIONS

Two builds are deployed, so you can compare them and say which one to change.

| | URL | What it is |
|---|---|---|
| **v2** | `/sonnys/` | Current. The refinement pass: exterior as a full-bleed figure, drinks behind disclosures, Visit in the mobile nav, wine copy, photography reassigned. **This is the link to send anyone.** |
| **v1** | `/sonnys/v1/` | Archived. The original build with the darkened exterior underlay, the full drinks list expanded, and the Chef's Selection capsule. |

- v2 lives at the repo root (`index.html`). v1 lives in `v1/index.html`.
- Both share one copy of `assets/` and `fonts/` — v1's paths point up one level (`../assets/`).
  If you delete an asset, check `v1/index.html` first.
- **v1 is `noindex, nofollow`** and is blocked in `robots.txt`. Two near-identical pages
  competing in search would cost you more than the comparison is worth.
- Mobile page height, 390px: **v1 is 8,608px, v2 is 6,920px.**
- Next time, archive the current root into `v3/` before overwriting it, and keep the root
  as whatever is current.

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

## THIS IS A MOCKUP BUILT FROM FOUND MATERIAL

Everything on the page came from Sonny's own site, their printed menus, press coverage
and the photographs you supplied. Nothing came from Sonny's directly. Before this is
shown as anything other than a pitch, every line needs their yes.

Already removed on that basis: the wine paragraph ("mostly small growers, plenty of it
from WA") and its matching schema entry. It was my reading of one photographed page,
not something Sonny's have ever said. There is now no wine claim on the page.

**Still standing on the same footing, and worth a second look:**

- *"So is the wine list. Margaret River on one page, Naoussa on the next."* in The bar.
  Both wines are on the list you photographed, so it is defensible, but it is still me
  describing their list for them. Easy cut if you'd rather nothing.
- *"A small bar in Mount Hawthorn with a very good kitchen."* is a judgement, not a fact.
  It sits above a real award, which earns it, but it is still an opinion in their voice.
- The weekly menu line assumes the weekly arrangement exists. It does not yet.

## CONFIRM BEFORE LAUNCH

These came from third-party sources (WA Good Food Guide, Broadsheet), not from the
venue. Every one is on the page — get a yes from Sonny's before it goes live.

| # | Claim on the page | Source | Action |
|---|---|---|---|
| 2 | **Sofika Boulton, head chef and owner** | You told me the owner part; my sources only had "head chef" | Confirm the ownership before this is public — it's on the page and in the schema |
| 3 | Wheelchair accessible | WAGFG listing | Confirm |
| 4 | Dog friendly outside, bowls at the door | WAGFG listing | Confirm |
| 5 | Outdoor seating out front | Photo + WAGFG | Confirm |
| 6 | Award: Winner, Best Bar Dining, WA Good Food Guide 2025 | wagoodfoodguide.com/award/best-bar-dining-2025 | Verified winner. Confirm wording they prefer |
| 6b | Award: Winner, Breakthrough Talent, Sofika Boulton | Read off the award badge on the current site | **The year is my read, not a source.** The badge carries the same WAGFG roundel, so I have grouped it under "WA Good Food Guide 2025". Confirm the year and the exact award name |
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
- **Clean award logo files.** The two award badges on the current site are Instagram
  tiles: black artboards with sponsor logos (Distl, Pardoo) and their own typography
  baked in, at two different aspect ratios. They are not press assets and they are not
  on the page — the awards are set as type in the footer instead. If you want the WA
  Good Food Guide roundel as a mark, ask the guide for the vector logo, or send me the
  badge PNGs directly (I cannot pull them off the Wix CDN from here).
- **The wine list.** The page now says what the list covers (sparkling, white and orange;
  mostly Margaret River and the rest of WA, with France, Italy and Greece; bottles about
  60 to 160) because that is what the booklet you photographed shows. **The bottles
  themselves are not on the page and must not be guessed.** For a wine bar that is the
  biggest remaining content gap. Ask for the current list as a dated PDF, or for
  permission to publish a by-the-glass selection that changes less often.
- **A real content-update date for the menu.** The page said "Updated 14 September 2026",
  which was the day it was built, not the day the menu changed. That line is gone. Do not
  reinstate a date unless the venue actually tells you when the card last changed, and
  never wire it to the visitor's clock.
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

**Each photograph now has one job.** The fire moved up beside "Most of it's cooked over
fire", where the heading and the picture finally say the same thing; the desserts moved
down into the menu, where they sit level with the dessert rows in the list beside them.
Neither was true before: the fire was an arbitrary pause between the food and the
cocktails, and the desserts were illustrating a sentence about the kitchen.

| Photograph | Job |
|---|---|
| Blurred dinner table | The feeling of an evening. Hero. |
| Window seat | What it is like to sit in the actual room. |
| Wood fire | The cooking method, next to the sentence about it. |
| Desserts | The dessert end of the food list, beside it. |
| Exterior | Recognising the place from the street. |

The remaining three photographs still come from the Wix CDN via Wix's own
`/v1/fill/w_…,h_…,enc_auto/` transform, which generates each `srcset` step on the fly.
They're below the fold and lazy-loaded, so the cost is low — but **before launch**,
pull them down and self-host them alongside the hero for consistency and to remove
the last third-party dependency. Source IDs:

- window seat `ebaa3f_56c5e098728a4288a6fc9ef02135eaa5~mv2.jpg` (1688×3000)
- wood fire `ebaa3f_5470044fb8f54945aaf292906292e9f3~mv2.jpg` (1125×2000)
- desserts `ebaa3f_e133b4cb899d4bb4b7b8c71251ac7c26~mv2.png` (2748×1912)
- wordmark `ebaa3f_509e59dc3caf4f5d974daf21a055a48e~mv2.png` (schema only)

The exterior is now self-hosted in both frames. See **THE EXTERIOR** below.

Full URL: `https://static.wixstatic.com/media/<ID>/v1/fill/w_W,h_H,al_c,q_80,enc_auto/<ID>`

## THE MENU IS A WEEKLY DELIVERABLE

The Menu section now leads with **"This week's menu."** and carries a dated line
underneath: *It changes every week — this is what's on now. Updated 14 September 2026.*

That date is the whole point — it visibly goes stale, which is what makes a weekly
update something the client can see they're paying for. **It must be changed every time
the menu is.** One edit, two places, both in the Menu section:

```html
Updated <time id="menuUpdated" datetime="2026-09-14">14 September 2026</time>
```

`datetime` is machine-readable (keep it `YYYY-MM-DD`), the text is what people see.
If the retainer doesn't happen, delete the whole sentence — a stale date is worse than
no date.

## MENU CAPITALISATION — the rule

One rule across all three lists, so it reads as considered rather than inconsistent:

- **Dishes and ingredients stay lowercase**, matching their printed card's house style.
- **Proper nouns are capitalised**: Great Southern, La Delizia, Goolwa, Basque,
  Cambray Farm, Republic of Fremantle, Campari, Nixta, Thai basil, T-bone.
- **Drinks brands are Title Case, never caps-lock**: `CAPI` → Capi,
  `STRANGELOVE` → StrangeLove. XPA stays capitalised (it's a style, not a word).

If Sonny's want the list reproduced exactly as printed — all lowercase, shouty brands
and all — it's a find-and-replace, but the page will look less deliberate.

## THE EXTERIOR — no longer an underlay

The exterior used to sit behind the Visit section, tone-mapped into grey 20–64 so text
could clear it. That treatment is what erased the blue sign, which the copy right beside
it told people to look for. The underlay is gone. The photograph is now a **full-bleed
figure** at its own exposure, with the practical text on plain ink below it, so neither
has to be compromised for the other.

**Two frames, art-directed.**

| Width | File | Ratio | Shows |
|---|---|---|---|
| under 700px | `assets/visit-street-466\|932.webp\|jpg` | 466:642 | The frontage you sent: gum tree, umbrella tables in use, the window |
| 700px and up | `assets/visit-wide-960\|1440\|1920.webp\|jpg` | 1920:655 | The whole frontage: umbrellas, stone, the blue sign, the entrance |

**The wide frame was recovered, not sourced.** The only copy of that photograph left in
the project was the tone-mapped one. The treatment is invertible, so it was inverted:
undo the chroma taper, undo the luminance compression, assume the original spanned the
full range. The sign, the stone and the doorway all came back. But it was reconstructed
from a file with roughly 44 luminance levels, so the sky is blown and the dark upper
box is blocky. **It holds up at a band that size and it should still be replaced.**

**What to ask for:** the original full-resolution frontage photograph, and ideally a
second frame that has both the umbrella tables and the blue sign in one portrait crop —
that would let mobile and desktop run the same image. The file you sent is 466×682,
which is under 2x for a 390px phone, so it is soft on a retina screen.

**"Look for the blue sign on the stone"** is now a wayfinding line in the Address column
rather than a caption, because the mobile frame does not show the sign and a caption
would have contradicted the picture above it. The desktop frame does show it.

## TYPOGRAPHY RULES

- **No em dashes anywhere.** Full stops, commas or colons instead. Checked: zero in the file.
- **En dashes stay in ranges only** (`Mon – Tue`, `4pm – 10pm`), which is correct typography.
- **Menu items are capitalised at the start of every slash-separated part**:
  *Grilled market fish / Roast chicken butter / Goolwa pipis*. Proper nouns keep their
  capitals wherever they fall. Drinks descriptions start with a capital.
- **Drinks brands are Title Case, never caps-lock**: Capi, StrangeLove. XPA stays capitalised.

## CTA SHAPE — the radius stays, the pair does not

The full pill picks up the circular bowls in the wordmark and it is a single token,
`--radius`. It stays. What changed is that the hero no longer offers **two** near-identical
pills: *Book a table* is the blue pill, *See the menu* is a quiet underlined link. One
decision, one route. The glass blur that was on the second button is gone.

The Chef's Selection panel that also used `--radius` has been removed — it read as
something you were meant to click. It is now an ordinary menu row.

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

## DELIBERATELY KEPT, AGAINST ADVICE

Three things a reviewer might expect to have changed and did not:

1. **The pill radius.** It is drawn from the wordmark, and you chose it. The problem was
   never the shape, it was two of them side by side. That is fixed instead.
2. **"Sonny was a rescue greyhound."** Still out. You cut it twice as AI-sounding. It is
   your venue and your call, and it has not been reinstated.
3. **"This week's menu."** Kept because you want the weekly framing to support a
   retainer. It is still an arrangement that does not exist yet, so it stays on the
   confirm list. The sentence that explained it underneath is gone — the heading
   already said it.

## MOBILE — iPhone Pro / Pro Max

**The black band under the status bar was `theme-color`.** iOS Safari paints the status
bar area with that meta value. It was `#0E0F12`, the page ground. The thing actually
sitting under the status bar is the top of the hero photograph, which composites to
`#281C17` — warmer and lighter. `theme-color` is now `#281C17`, measured off a render at
393×852, and the seam is gone (top strip reads `#271B17`).

**The hero fills the viewport.** It was `88svh`, which left ~100px of the next section
showing under Safari's floating toolbar — a broken-looking fold rather than a deliberate
one. It is `100svh` now: 852px on a 15 Pro, 932px on a Pro Max, exactly.

**Safe areas.** `.wrap` pads to `max(--gut, env(safe-area-inset-left/right))` so landscape
on a notched phone never runs text under the notch. The hero rail and the booking bar
both add `env(safe-area-inset-bottom)` to clear the home indicator.

## STICKY BOOKING BAR

Below 720px, booking moves to the thumb zone.

- **The header button is hidden below 720px.** There is never more than one blue pill on
  screen: the hero carries its own, and the bar takes over once the hero is out of view
  (IntersectionObserver on `.hero`, not a scroll listener).
- It carries the **live open/closed line** in a short form computed alongside the long one
  — `Opens Wed 4pm`, `Open until 10pm` — so the bar is worth its 67px rather than being a
  floating button.
- `visibility:hidden` while off, so it is out of the tab order until it is actually there.
- Transition is zeroed under `prefers-reduced-motion`.
- The footer gains `92px + safe-area` of bottom padding below 720px. Measured clearance
  between the last legal line and the bar: **25px**.

## MOBILE — the drinks are no longer in the way

At 390px the menu section used to be 4,371px of an 8,485px page: every cocktail, beer
and soft drink stood between a phone and the address. Cocktails and "Beer, cider and
soft drinks" are now native `<details>` disclosures.

- They are **closed in the markup** and opened by a one-line script above 760px, which
  runs during parse so nothing flashes open and shut.
- The content is in the DOM either way, so crawlers, AI answer engines and find-in-page
  all still see every item. Chrome auto-expands `<details>` for Ctrl+F.
- Keyboard operable, focus-visible, no animation, `Show` / `Hide` in plain words.

Menu section is now 2,214px of a 6,920px page. Visit is also back in the header at every
width — it used to disappear under 720px, which meant a phone could not reach the address
without scrolling the whole drinks list.

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
