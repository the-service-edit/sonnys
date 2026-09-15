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

Two live variants of the **current** site, differing only in the Bar Lyla footer block.

| | URL | Bar Lyla block |
|---|---|---|
| **v1** | `/sonnys/v1/` | Type only: label, name, three lines, handle |
| **v2** | `/sonnys/v2/` | The Bar Lyla logo on a bone plaque, copy beside it |

- **The root redirects to v2** (`meta refresh` + `location.replace`, with a visible link as
  fallback). `/sonnys/` is still the link to hand anyone; it lands on v2.
- **v1 is `noindex` and disallowed in `robots.txt`.** Two near-identical pages competing in
  search costs more than the comparison is worth. v2 is the indexable one.
- Both share one copy of `assets/` and `fonts/`; their paths point up one level.
- **The original pre-redesign build has been retired** from the live site. It used to sit at
  `/v1/`. It is still in git history (commit `9c8a4cc`, file `v1/index.html`) and a copy is
  in `_unused/original-index.html` if you ever want the before-and-after again.

### The Bar Lyla mark

`assets/lyla-logo-300|600.png|webp`, transparent PNG trimmed to its bounding box, WebP
with alpha alongside it. The mark is `#6F021E`.

**It sits on a bone plaque, not straight on the footer.** Burgundy on `#14161A` measures
**1.47:1**; on bone it is **10.10:1**. That is also the same plaque the Sonny's wordmark
takes two blocks above, so the two venues read as a pair rather than as one venue and one
stray graphic.

The logo carries the venue name, so the text heading came out to avoid saying "Bar Lyla"
twice in a row. The name is still the `<h2>` for the outline and still in the
accessibility tree as the image's `alt`.

**Still raster.** Ask Bar Lyla for the vector. At 226px on a 2x screen the 600px PNG is
fine, but an SVG would be smaller than the 17KB WebP and sharp at any size.

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

## BREAD COPY — sourced from Sonny's own words

*"The bread is baked in-house every day and finished over the fire."*

That is not interpretation. It is Sonny's own Instagram caption (post of 2 September,
`instagram.com/p/Dcxy07NAffO/`), which reads in full: **"chef's favourite thing to make
— freshly baked in-house every day, finished over the fire and served warm with
lemon-infused Great Southern Groves olive oil and whipped salted butter."** The venue's
own words are the strongest source on this page.

Left on the table, deliberately:

- **"Famous" is not on the page.** The comments on that post include "Best bread in
  Perth", which is why the framing has a basis, but a customer comment is not a
  reputation claim you can publish. If Sonny's want it, they can say it themselves.
- **The olive oil** (lemon-infused, Great Southern Groves) is a real and unusually
  specific detail, and it is a producer name you could credit. Not used yet because the
  printed menu you photographed says only "Barbecued bread / Whipped butter". Worth
  asking which is current.

## HOURS — a third source now disagrees

Their Instagram bio says **"wed & thurs 4 - late / fri sat & sun 12 - late"**. The site
uses the Contact page version (Wed–Thu 4–10pm, Fri–Sat 12–late, Sun 12–9pm). Sunday is
the real conflict: 9pm on the site, "late" on Instagram. Add it to the list below.

## ⚠ OWNERSHIP — RESOLVE THIS ONE FIRST

The page says *"Head chef and owner Sofika Boulton"*. That came from you, not from
research, and two Broadsheet articles now say otherwise:

- The Bar Lyla piece describes Boulton as **"Head Chef at Sonny's"** and Jess Blyth as
  **"co-owner"** of Sonny's. Boulton is called an owner of *Bar Lyla*, not of Sonny's.
- The original Sonny's launch piece names **Jessica Blyth** as the person who conceived
  and drives the venue. It does not name Boulton at all (the opening chef was Aaron Read).

So the likely position is: **Blyth is the owner, Boulton is the head chef.** Getting this
wrong in a pitch is the worst error on the page, worse than any price or opening hour.

Three options:

1. **Safest, defensible under either reading:** change it to "Head chef Sofika Boulton
   runs the kitchen." True whether or not she also holds equity.
2. Keep "and owner" only if Sonny's confirm it directly. She may well have bought in
   since those articles.
3. If Blyth is the owner and that matters to the story, credit both.

**I have not changed it**, because you stated it as fact and you may know something the
press does not. But it is on the page and in the JSON-LD `employee.jobTitle`, so it needs
your answer before this goes in front of anyone.

## BAR LYLA — the new venue, in the footer

Every fact on the page is from Broadsheet, not written by me:

| On the page | Source |
|---|---|
| Bar Lyla | Broadsheet, both articles |
| Opening October | "Opening in October 2026" |
| Two-minute walk away, Scarborough Beach Road | "a two-minute walk from Sonny's"; address given as 1/155 Scarborough Beach Road |
| Old La Madonna Nera space | "the former La Madonna Nera space" |
| Drinks first, small plates, about fifteen wines by the glass | "It's drinks first, and the food's going to be the kind of food that goes well with drinks"; ~15 rotating wines by glass/bottle |
| From Sofika Boulton and Jess Blyth | Both named as Bar Lyla owners |
| @bar.lyla | Handle given in the article |

Deliberately left off: the "more feminine energy than Sonny's" quote (Boulton's words
about Bar Lyla, not Sonny's to publish on their site), the hibashi grill (detail without
a job on a footer note), and the unit number in the address (their site should carry it,
not Sonny's).

**Two things to watch:**

- **The suburb is disputed.** The article body says Mount Hawthorn; its own headline says
  North Perth. The page avoids the suburb and names the street, which is true either way.
  Confirm before adding one.
- **"Opening October" goes stale in weeks.** After they open, it becomes "now open" or the
  block comes out. Put a reminder in the calendar; a stale "opening soon" is worse than no
  mention at all.

Not added to the JSON-LD. A second business inside Sonny's `Restaurant` graph muddies
which business the page is about. It stays visible content only.

**The neon photograph was cut.** It ran briefly in a two-column version of this block.
It is an out-of-focus mood shot: it tells a reader nothing they cannot get from the three
lines of copy, and at any size small enough to belong in a footer the glow filled the
frame and the black had nowhere to go. The block is now type only, which also makes it
read consistently with the awards row directly beneath it.

If it ever goes back, the working files are in `_unused/` and the encoding that suited it
was 4:4:4 chroma at q92 JPEG / q90 WebP. Saturated red on black is the case 4:2:0
subsampling destroys, and a long smooth glow is what low quality bands.

## FOOTER WORDMARK — blue, on a ground that carries it

You asked for the footer wordmark in the brand blue. Straight onto the footer, `#223E99`
on `#14161A` measures **1.91:1** — under the 3:1 minimum for non-text graphics, and it
turns to mud on a dimmed phone or in daylight.

It now sits on a bone plaque: **7.76:1**, and blue-on-light is how the real sign on the
stone and the favicon both work. `see footer-logo-compare.png` for the two side by side.
If you would rather it sat bare on the dark, the token is `.ftr__brand` and removing the
background is a one-line change, but I would not ship it.

## CONFIRM BEFORE LAUNCH

These came from third-party sources (WA Good Food Guide, Broadsheet), not from the
venue. Every one is on the page — get a yes from Sonny's before it goes live.

| # | Claim on the page | Source | Action |
|---|---|---|---|
| 2 | **Sofika Boulton, head chef and owner** | You told me the owner part. **Two published sources now contradict it** | See the section immediately below. Resolve before this is shown to anyone |
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

- **Blue is `#223E99`** (your choice, replacing the sampled `#0058E2`). It carries the
  primary CTAs, hover states and the open-now dot. Three tokens, all measured:

  | Token | Value | Where | Contrast |
  |---|---|---|---|
  | `--blue` | `#223E99` | Button fills | Bone on it **7.76:1** (AAA) |
  | `--blue-lift` | `#294CBA` | Button hover | Bone on it **6.07:1** |
  | `--blue-bright` | `#5979E4` | Link hover, open-now dot | On ink **4.82:1**, on the menu band **4.55:1** |

  The lift and the accent are computed at the brand hue (226°), not eyeballed: the accent
  is the lowest lightness at that hue that still clears 4.8:1 on the ink ground. The old
  palette measured 4.93:1 on the button, so this is a genuine accessibility gain as well
  as a calmer one against the candlelit photography.

  **It also sits closer to the real sign.** Sampled off the new frontage photograph, the
  SONNYS lettering reads `#122947` in shade. That is darker than any brand value (it is
  shadow, not paint), but `#223E99` is nearer to it than `#0058E2` was.

  Changed with it: `msapplication-TileColor`, the `mask-icon` colour, the open-now dot
  glow, `assets/favicon.svg`, `assets/wordmark-s.svg`, and the three PNG icons
  (re-rasterised from the SVG at 16 / 32 / 180, not recoloured pixel by pixel).

  **Not changed:** the `accent=33,15,243` parameter on the Nowbookit gift-card URL. That
  came from the original Wix site, does not match either brand blue, and it is a
  third-party widget parameter. Worth asking Nowbookit what format it expects before
  touching it.
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

**The bread replaced the window seat** in that section. It is the dish the heading is
about, it is self-hosted (`assets/bread-560|840|1073.webp|jpg`, 4:5), and its near-black
table blends into the ink ground so the loaf reads as if it is floating. The blue rim of
the table also happens to sit right next to the brand blue.

The room now has no photograph. If you want one back, `ebaa3f_349e22161c1a4e4c9e42edf24017baf7~mv2.jpg`
("Sonny's-3.jpg", on their gift-card page) is the interior with the **BREAK BREAD NOT
HEARTS** mural painted on the wall, which is where the footer line comes from. It is a
better room shot than the window seat was. Not added: five photographs is already enough.

| Photograph | Job |
|---|---|
| Blurred dinner table | The feeling of an evening. Hero. |
| Barbecued bread | The signature dish, charred over the fire, beside the sentence about it. Self-hosted. |
| Wood fire | The cooking method, next to the sentence about it. |
| Desserts | The dessert end of the food list, beside it. |
| Exterior | Recognising the place from the street. |

The remaining three photographs still come from the Wix CDN via Wix's own
`/v1/fill/w_…,h_…,enc_auto/` transform, which generates each `srcset` step on the fly.
They're below the fold and lazy-loaded, so the cost is low — but **before launch**,
pull them down and self-host them alongside the hero for consistency and to remove
the last third-party dependency. Source IDs:

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
| under 700px | `assets/visit-street-520\|780\|1042.webp\|jpg` | 1042:1421 | The frontage you sent: gum tree, umbrella tables in use, the window |
| 700px and up | `assets/visit-wide-960\|1440\|1774.webp\|jpg` | 1774:887 | The whole frontage: umbrellas, stone, the blue sign, the entrance |

**Both frames are now real photographs.** The wide band was briefly a reconstruction
(the only copy left in the project had been tone-mapped, so the treatment was inverted
to recover it). That is retired: the 1774×887 original replaced it.

**The wide band uses an explicit height, not an aspect ratio.** `height:clamp(400px,42vw,620px)`
with `object-fit:cover` and `object-position:center 62%`. A `max-height` on an
`aspect-ratio` box shrinks the width along with it and the full bleed is lost. The 62%
keeps the sign, the entrance and the umbrellas and trims sky instead.

Mobile source is 1042×1510, trimmed 5.9% off the top to match the framing already signed
off, served at 520 / 780 / 1042. A Pro Max at 3x renders it at 430×586 from the 1042
candidate. Desktop source is 1774×887, served at 960 / 1440 / 1774.

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
   confirm list. The line underneath is back at your request, but rewritten: the old
   one only restated the heading. It now ends on a reason to book —
   *"It changes every week, so if something here is the reason you're coming, come
   this week."* The fabricated "Updated \<date\>" is still gone and should stay gone.

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

## IMAGE PROTECTION — what it does and does not do

Right-click "Save image as" and drag-to-desktop are blocked on imagery: `contextmenu` and
`dragstart` are cancelled for anything inside `img`, `picture`, `.ph` or the wordmark SVG,
plus `-webkit-touch-callout:none` to kill the iOS long-press save sheet and
`user-select:none` on those elements.

**Scoped deliberately.** Right-click still works on text, so a customer can copy the
address, the email and the hours. Blocking the whole document would be hostile and would
break "open link in new tab" and browser translation.

**Be clear with the client about the limit.** This stops casual saving. It cannot stop
anyone who wants the file: every image has to reach the browser to be displayed, so
DevTools, the network tab, view-source, disabling JavaScript, or just requesting
`/assets/visit-street-1042.jpg` directly all still work. A screenshot always works.

If the photographer's licensing is the real concern, the levers that actually matter are:
keep the web copies at web resolution (the largest file here is 1042px wide, unusable for
print), and watermark anything that must not be reused. The three Wix-hosted photographs
are served from Wix's public CDN and are outside this protection entirely.

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
