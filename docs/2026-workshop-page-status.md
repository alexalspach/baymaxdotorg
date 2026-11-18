# Can we build Baymax? 2026 — page status

Repo: `baymaxdotorg` · Page: `website/workshop/2026/` · Started 2026-09-10 from a copy of the 2025 page.
Older pages (2025, 2024, and earlier) were **not** modified.

> Ported into the repo 2026-11-11 from the claude.ai Project doc of the same name, so that local
> Claude Code sessions can read it. The operational sections (images, previewing, git) have been
> **rewritten for a local checkout** — the originals described a sandboxed session reaching this
> folder over a bridge, and most of those limits do not apply when running on Alex's own Mac.
> Everything else is carried over as written.

## Workshop identity

- Title: **Can We Build Baymax? Part 11: Humanoids for Characters, Performance & Creative Applications**
  (the banner shows the big "11" and the theme line; there is no separate "Part 11:" text line)
- Venue: Humanoids 2026 (25th IEEE-RAS Int. Conf. on Humanoid Robots), **Santa Clara, California, USA**
  (Santa Clara Convention Center, 5001 Great America Pkwy).
- Conference dates: December 7–9, 2026 · https://2026.ieee-humanoids.org/
- **Workshop date: Monday, December 7, 2026** — locked in 2026-10-20. Dec 7 is the conference's
  workshops-and-tutorials day. Room number still TBD.

## Page structure (top to bottom)

Banner → **Speakers** → **Objectives** → Schedule → Organizers → Related Links → Contact. Nav matches.

**Speakers and Objectives were swapped on 2026-10-29** so the confirmed speakers lead the page. The
*section wrappers and their background colours stay in their original order* and only the content
moved. So the first slot is still `<section id="one" class="wrapper style2">` (default teal) and the
second is still the same section with `style="background-color: #120935;"` (dark) — Speakers now
occupies the teal slot and Objectives the dark one. Side effect: this restores the 2025 pairing, where
speakers sat on the default style2 background. The `<span class="anchor">` targets moved with their
content, so `#speakers` and `#objectives` still land correctly.

## Organizers (2026)

Chris Atkeson (CMU) · Joohyung Kim (Illinois) · Jinoh Lee (DLR) · Aykut Onol (TRI) · Katsu Yamane (Path
Robotics) · Alex Alspach (Walden Robotics). Gordon Cheng and Yunsoo Seo were removed.

## Speakers (added 2026-10-29)

Three **confirmed** speakers are live, as cards in `#speaker_face_flex_grid`, built from the 2025 markup
pattern (circular `.speaker_face` photo → name link → credentials `<br>` block → `.text-content short-text`
bio → "More Info" toggle). Ordered alphabetically by surname, as 2025 was. Source: the
`CWBB_2026_Invited_Speakers_-_Invites.csv` invite sheet; each card's link is that row's "Website Links" URL.

| Speaker | Credentials block | Photo | Link |
|---|---|---|---|
| Eric Allard | Special Effects Supervisor / Founder, Allfx, Inc. / Creator of Johnny 5 | `Allard_Eric.jpg` 380² | allfx.com |
| Will Knight | Designer, Animator & Illustrator / Figment Ltd | `Knight_Will.jpg` 600² | willknight.com |
| Moshe Mahler | Faculty at the Entertainment Technology Center at Carnegie Mellon University / Principal and Owner, BIG eMotion Technologies | `Mahler_Moshe.jpg` 480² | momahler.com |

Section heading changed from "Speakers to be announced!" to "**Confirmed Speakers**" plus a "more being
confirmed" line. The ⚡Speakers⚡ stamp title stays commented out (see Known issues).

Judgement calls worth revisiting:

- **Eric Allard's bio was written by Claude**, from the "About Eric Allard" and company sections of
  https://www.allfx.com/ — his invite row had no bio text. An HTML comment above the bio says so. Replace
  if he sends his own. His sheet row also had no "Website Links" value; the `https://www.allfx.com/` in the
  sheet sits one row down, in **Jin Kim's** row. Alex confirmed 2026-10-29 that it is Eric's. **The sheet
  cell is still misplaced** and should be fixed at the source.
- **Eric's photo** is the only image on allfx.com showing his face: a black-and-white 1980s publicity shot of
  him with Johnny 5 (`images/J5/Eric_with_J5.jpg`), cropped to his head. It reads differently from the other
  two. Worth asking him for a current headshot.
- **Will Knight's bio** is his own copy from willknight.com, **converted to third person** at Alex's request
  on 2026-10-29. British spellings (organisations, visualising) were kept deliberately.
- **Will Knight's photo** is cropped from `WillKnightProfile.JPG` on his MA-show page
  (https://www.cambridgemashow.com/will-knight) — a selfie holding two guinea pigs; willknight.com has no
  portrait at all. Cropped tight to his face; the remaining tuft of fur falls outside the circular mask. The
  full guinea-pig version is a one-line change if that's ever wanted.
- **Will's affiliation** was blank in the sheet's "Website Affiliation" column. Alex chose **Figment Ltd**
  (his site footer reads "© FIGMENT LTD"; the sheet's Notes column said "Figment, Stealth startup").
- **Moshe's affiliation** — Alex asked for "Faculty at the Entertainment Technology Center at Carnegie Mellon
  University" on a single line (2026-10-29). The BIG eMotion Technologies line was **kept** as a second line
  since he didn't say to drop it; confirm if he wants it gone.

Not added: Rob Cochran and David Hanson (DECLINED); the seven INVITED rows (Jin Kim, Moritz Bächer,
Cheng Chi, Marc Theermann, Kawada, Figure AI, Galaxy Corporation) and the three no-status rows (Elon Musk,
Colin Angle, Scott LaValley).

## Logos in this repo — what is actually there

**`website/workshop/2026/images/logos/web/logos.png`** (1450×679) carries **six** logos in two rows:
CMU Robotics Institute · **Walden Robotics** · Illinois / DLR · Path Robotics · Toyota Research Institute.

**`photoshop/logos/logos11.psd`** (1.5 MB, canvas 1450×679) is the editable source for that strip and has
one named layer per logo. Visible: `RI`, `walden_fulllockup_black`, `UIUC`, `DLR_Logo`, `Path Logo`, `TRI`.
Hidden spares sit in the same file: `HRI`, `DR`, `Eurobench_logo_high_res`, `Bosch Logo`, `IIT`, and a
`Group 1` of placeholder frames. **`psd-tools` reads it fine** (`pip install psd-tools`, then
`PSDImage.open(...)`, iterate, `layer.composite()`), which is how the TRI logo was extracted — so
individual logos can be pulled out of the strip without opening Photoshop.

The PSD canvas is the same size as the exported PNG, so **the PSD holds no more resolution than the strip**.
For anything that needs to be larger than ~330px, get an official file from the organisation.

Also in the repo: `website/workshop/2023/images/speakers/logos/toyota.png` is the **Toyota corporate**
logo (the three-ellipse mark), *not* TRI. Don't reach for it when TRI is what's wanted.

## The Baymax gutter — responsive fix, 2026-11-06

**This is the one styling change that touches both pages**, and the only thing added to the shared
`workshop/2026/assets/css/override.css` (at the very end of the file, in a commented block). The 2025 and
earlier folders have their own copies of that file and are untouched.

**The problem.** `#baymax` is `position: absolute` at the left of the page while the banner text is centred,
and his size was set in steps — 900 / 800 / 600 / 500 px at the 1300 / 1280 / 980 breakpoints, then
`display: none` at 736. Between those steps the picture and the text collided. A width sweep on 2026-11-06
measured text running **up to 200px into him, continuously from 740px to 1540px, on the workshop page and
the mixer page alike**. This was pre-existing, not introduced by the mixer work.

**The trap.** `#baymax` had no `left`, so it sat at its static position — which is `#banner`'s *padding*
edge. Padding the banner to make room would simply have pushed him along with the text and fixed nothing.
`left: 0` has to come first. (The `margin-left: -45px` in the old 1300px rule was what put his left edge at
x=3 rather than x=48; that margin is now zeroed.)

**The fix**, three parts:

1. `left: 0` on `#baymax`, pinning him to the page edge independent of the banner's padding.
2. A **continuous** height, `clamp(300px, 47vw, 900px)`, and a continuous `top`,
   `clamp(200px, calc(950px - 38vw), 560px)`, replacing the stepped values. Continuous matters: with steps
   there is always a width where the step and the reserved gutter disagree.
3. **Symmetric** padding on `#banner` equal to his width plus air. Symmetric rather than left-only so the
   text stays centred on the page as it always has; on wide screens the lines are narrower than the content
   box anyway, so it costs nothing to look at. Below about 1000px the text simply wraps more.

Everything derives from one custom property so the picture and the gutter cannot drift apart:

```
--baymax-ratio: 0.5043          /* baymax.png is 470 x 932 */
--baymax-h:      clamp(300px, 47vw, 900px)
--baymax-w:      calc(var(--baymax-ratio) * var(--baymax-h))
--baymax-gap:    1.5rem
--baymax-gutter: calc(var(--baymax-w) + var(--baymax-gap))
--banner-content: calc(100vw - 2 * var(--baymax-gutter))
```

**Change `--baymax-h` and the gutter follows.** `--banner-content` is the real usable width of `#banner`'s
content box; it is redefined to `calc(100vw - 6em)` below 736px and `calc(100vw - 4em)` below 480px, where
Baymax is hidden and `#banner`'s own padding is what's left. Page type that must not wrap sizes itself off
`--banner-content` rather than off raw `vw` — see the mixer's `.mixer-word` and `.invite-line` — which is
what keeps those words clear of Baymax as well as of the viewport edge.

The gutter is applied under `@media (min-width: 736px)`, matching (and deliberately overlapping by 1px) the
`max-width: 736px` rule that hides him, so a fractional viewport width can't fall between the two.

**Verified** by sweeping both pages from 280px to 2560px in 10px steps, intersecting `#baymax`'s box against
the client rects of every visible text node in the document: **zero overlaps**, and no horizontal overflow
above 320px. Re-run that sweep after any banner or Baymax change.

Known floor: below ~323px the document is wider than the viewport by up to 43px. That is
`html { min-width: 320px }` in the vendor template (`main_orig.css`, lines 1565 and 3737), it applies to
every page on the site including earlier years, and 320px is the narrowest real device. Baymax is hidden
there, so it is not an overlap — left alone rather than patching the vendor file.

## Mixer page (added 2026-11-06)

New page at **`website/workshop/2026/mixer/index.html`** → `https://baymax.org/workshop/2026/mixer`.
It is a **folder**, not a sibling file like 2025's `mixer-vip.html`, so every shared asset is referenced one
level up (`../assets/…`, `../images/…`).

Built on the 2025 mixer invite's structure (header → `#banner` / `#WSTitle` → `#baymax` → `#redbar`), then
taken further over several rounds of Alex's notes the same afternoon.

Copy on the page, top to bottom:

- "Can we build Baymax?" in `.bighero-font`, then **MIXER!** as the hero word
- **You're Invited**, then "Mention you're a **"friend of Baymax"** at the door."
- 📅 TIME and LOCATION 📅 · **Mon. Dec. 7 · 7:00 – 11:00 PM**
- **Clara's Junction** · the street address, **linked** (see below) · 0.8 mi / ~17 min walk ·
  `[google maps]` `[venue site]`
- 🍻 Drinks and small bites 🍻 · On the house.
- **MIXER SPONSORED BY** + the TRI logo card (see below)
- ⚠️❗ FIRST COME, FIRST SERVED ❗⚠️ · space limited, entrance not guaranteed, arrive on time
- ✍️ RSVP ✍️ · "An RSVP helps us plan, but it is not a ticket." · the form

Removed at Alex's request: the big yellow **"11"** (`.number-11`); the **"Humanoids 2026 / Santa Clara,
California, USA"** `.workshop_year` stack; and, on 2026-11-06, the **"Designed by Alex Alspach" footer** —
the page now ends on the `#redbar`, which reads clean. The workshop page keeps its footer.

Worth knowing: the page never names the conference in its visible copy — the date, the Santa Clara address
and the header link to baymax.org carry it. The `<title>` and the og/twitter descriptions still say
"Humanoids 2026".

**It is deliberately not linked from the workshop page** — the `MIXER🍺` button in `index.html`'s
`<ul class="actions">` is still inside the "TBD: re-enable" comment block, and that comment was left alone.
Note the commented-out button points at `https://baymax.org/mixer` (the root mixer page), not
`/workshop/2026/mixer`, so the href needs updating when it is re-enabled.

### Share image (og / twitter)

The mixer has **its own** share image, `images/banner/mixer-banner.jpg` — 1200×630, 109 KB (111,716 bytes).
The workshop page and the site homepage both still use `images/banner/banner.jpg`; the mixer's `og:image`
and `twitter:image` point at the new file.

It was built from full-bleed artwork Alex supplied on 2026-11-06 (1888×1244, ratio 1.52:1). It was **not**
dropped in at native size: 1200×630 (1.905:1) is what og and `summary_large_image` expect, and at 1.52:1
every platform would have cropped it for you, each differently. It was centre-cropped to the right ratio
first, after checking the crop against the artwork's actual ink bounds — text runs from 16.6% to 86.3% of
the height, and the crop window leaves **78px clearance above the title and 43px below the last line**, so
nothing is clipped anywhere. If the artwork is ever re-cut, redo that check rather than assuming.

Link previews cache hard: after deploying, re-scrape via the Facebook debugger / LinkedIn post inspector —
the URLs are already in the page head comments.

### Three different map links

Easy to conflate, so: the **street address** links to the venue's Google Maps *place* page
(`https://www.google.com/maps/search/?api=1&query=Clara%27s+Junction%2C+2221+Tasman+Dr%2C…` — the venue
name is in the query on purpose, so it resolves to the business rather than the lot). **`[google maps]`**
is *walking directions* from the convention center. **`[venue site]`** is clarasjunction.com.

### Sponsor block (added 2026-11-06)

Alex asked for a prominent "Mixer sponsored by Toyota Research Institute" with their logo. It sits directly
under the "Drinks and small bites / On the house" lines, since TRI are the reason the drinks are free:
a yellow `MIXER SPONSORED BY` label over a **white card** holding the TRI logo, linked to
https://www.tri.global/.

The card is white because **the TRI artwork is red/black/grey on transparency and would all but vanish on
the dark banner**; white is also how TRI themselves present it, so inverting or recolouring was not an
option. It is bordered in the page's `#E3E653` so it reads as part of the design rather than a pasted-in
image, and uses `hvr-grow` from the site's existing hover.css.

`website/workshop/2026/images/logos/tri.png` was **extracted at native size (333×261) from the `TRI` layer
of `photoshop/logos/logos11.psd`** with `psd-tools`, then trimmed to its alpha bbox. That is the largest
copy of the TRI logo anywhere in the repo (the flattened strip is the same resolution). **If TRI supply an
official high-res or SVG file, swap it in.**

Sizing, after Alex asked for "a tad smaller … a bit more padding": logo `width: 250px`, card
`padding: 1.6rem 2.4rem` — 41px of air at the sides, 29px top and bottom, card 333×253 overall.

### Page-specific styling lives in a scoped `<style>` block

The background, the type treatments, the sponsor card and the RSVP form styling sit in a `<style>` block in
the mixer page's own `<head>`, placed after the stylesheet links so it wins on source order. They were kept
out of `override.css` because that file is shared with the workshop page — a `#banner` background or
`.bighero-font` change there would repaint the workshop page too. (The Baymax gutter is the deliberate
exception: it is a fix both pages needed, so it does live in `override.css`.)

### Title treatment

`MIXER!` is a `.mixer-word` div **nested inside** the `.bighero-font` div, not a sibling. That is
deliberate: its `font-size` is in `em`, so it resolves against the hero's own font-size and keeps its
proportion through `override.css`'s 600px hero breakpoint (`#banner .bighero-font {font-size: 3.5em}`)
without needing a breakpoint of its own. As a sibling it would have needed one, because the page's own
rule would out-specify the breakpoint rule.

It takes the old "11"'s colours — `-webkit-text-fill-color: #E3E653` with a whitesmoke
`-webkit-text-stroke`, stroke width in `em` so it scales with the word.

Size: `min(1.97em, calc(var(--banner-content) / 4.45))`. Alex asked for it to span nearly the width of
"Can we build" above it; measured in the browser, 1.97em lands at **97%** of that line on desktop. The cap
exists because MIXER! never wraps — at 1.97em alone it pushed the document 104px wider than a 390px
viewport. The word measures about **4.25× its font-size**; keep that ratio in mind if the text changes.

"You're Invited" is `.invite-line`, **Permanent Marker** (already in the page's Google Fonts request and in
`assets/fonts/`), rotated −2.2° so it reads scrawled rather than set, at
`min(3.2em, calc(var(--banner-content) / 7.3))` — it measures ~6.9× its font-size and would otherwise break
to two lines on a phone. Spicy Rice and Rubik Vinyl are the other fun faces the site already loads.

Both caps are divided out of `--banner-content`, not raw `vw`, so they account for the Baymax gutter too.

### Party background

Alex asked for a rainbow gradient overlay on the background image — "more party but still readable text" —
and then, seeing it, for it to be "more amorphous / blobby, less linear". Three layers on `#banner`,
topmost first:

1. **eleven rainbow blobs** — overlapping elliptical `radial-gradient`s that fade to fully transparent, so
   there is no straight edge anywhere in the wash. Both each blob's size and its centre are percentages of
   the banner box, so they stay spread over the whole page however tall it gets and however narrow the
   viewport is. The warm/yellow blobs were nudged off the title band so the yellow MIXER! sits on a cool
   backdrop; magenta sits behind it instead.
2. **dark scrim** — `radial-gradient(ellipse at 50% 28%, …)`, rgba(6,2,26) from 0.50 to 0.86. It sits
   *under* the blobs so their colour stays saturated while the photo beneath goes dark.
3. **`bg10.jpg`** — the circuit-board photo, as on the other pages. `url()` here is `../images/bg/bg10.jpg`
   because it resolves from the HTML file; `override.css`'s own copy is `../../images/…` because it
   resolves from `assets/css/`.

An earlier version used a diagonal `repeating-linear-gradient`; it is gone, but the reason it was written
that way is worth keeping: a `repeating-linear-gradient` repeats *along the gradient line* rather than
tiling as an image, so with matching first and last stops it has no seam on a tall page. A tiled diagonal
gradient would.

`#WSTitle` gets a heavier `text-shadow` to compensate for the brighter backdrop, and the RSVP inputs were
darkened (rgba(0,0,0,0.35) → 0.55, focus 0.7) with `text-shadow: none` so typed values stay crisp.

**Readability was measured, not eyeballed**: the page was rendered with the text hidden and the bare
backdrop sampled in 14 horizontal bands. Worst-case (brightest) pixel under the text column gives
**5.1:1 to 9.6:1** against whitesmoke — clears WCAG AA (4.5:1) everywhere. Re-run that check if the alphas
are ever raised.

No animation. A drifting rainbow was considered and dropped: animating `background-position` on a ~2500px
banner repaints the whole section each frame, and the obvious pseudo-element alternative needs
`position: relative` on `#banner`, which would change `#baymax`'s containing block.

### The embedded RSVP form

Alex asked for the Google Form's questions and submit button stripped out and rebuilt in the page rather
than iframed. The form is **"Baymax Mixer RSVP"**, id
`1FAIpQLSextDHvYHQteZroQgRb2tM-VIwvODXUw18CK2Ednm98jn_Rbg`. Native inputs styled to match the site POST
directly to that form's `/formResponse` endpoint, so answers still land in the same responses sheet.

| Question | Field name | Type | Required |
|---|---|---|---|
| Name | `entry.273577412` | short answer | yes |
| Affiliation | `entry.456834614` | short answer | no |
| Email Address | `entry.900075940` | short answer | yes |
| Questions and Comments | `entry.1252299877` | paragraph | no |

The `entry.*` names **are** the field ids — if the Google Form's questions are ever edited, re-read them
before touching the page. The structure was pulled from `window.FB_PUBLIC_LOAD_DATA_` on the live viewform
and cross-checked against the rendered `<input name>` attributes.

Mechanics: the form `target`s a hidden iframe so the page never navigates away; a small inline script swaps
the form for a thank-you panel on the iframe's `load`, with a 2.5 s timeout fallback in case Google refuses
to render its confirmation page in a frame (the POST still goes through either way).

**Not yet live-tested.** A real submission would put a row in the responses sheet, so it was left for Alex.
Verified structurally: field names, action URL, method, and the rendered page across the width range.

### Still open on the mixer page

- **No venue photo.** The `<img>` for a Clara's Junction shot is in the page as a commented-out line
  pointing at `../images/mixer/clarasjunction.jpeg` — uncomment once the file exists. `images/mixer/` is now
  empty.
- An **official TRI logo file** would be better than the 333px one pulled out of the PSD.
- No WhatsApp group link (2025's mixer page had one).
- "On the house." is a line Claude wrote. Alex's note gave only "🍻 Drinks and small bites 🍻", but dropping
  "on the house" would lose the fact that the drinks are free, so it was kept as the line beneath. Confirm.
- The `<meta description>` / og / twitter *text* does **not** mention the TRI sponsorship (the share
  *image* is the new banner). Add it if the sponsorship should show up in link previews.

## Working locally (rewritten 2026-11-11)

The original version of this section described a sandboxed session reaching this folder over a bridge.
Running locally in a checkout, most of those limits are gone. What still holds:

**Images.** Fetching from the web works normally here. Still worth doing first: **look inside the repo.**
The TRI logo turned out to already be here, inside a PSD — see the Logos section. `psd-tools` will pull
an individual layer out at native size without opening Photoshop.

**Previewing.** `./startServer.sh` from the repo root (port 8000, `--directory website`). The 2026 page is
at `http://localhost:8000/workshop/2026/`, the mixer at `http://localhost:8000/workshop/2026/mixer/`.
Drive it with Playwright against `localhost` — no file staging, no `file://` workarounds, and Google Fonts
load for real, so the live faces render without injecting `@font-face`.

**Measure rather than guess.** Every number in this doc came from a Playwright pass:

- *text width* — a `Range` over the text node, `getBoundingClientRect().width`; `getClientRects().length`
  tells you how many lines it broke into.
- *horizontal overflow* — `document.documentElement.scrollWidth - innerWidth`, swept across widths with
  `setViewportSize` on one page object (far faster than reloading) plus ~100ms for reflow.
- *overlap* — intersect one element's page-space box against the client rects of every visible text node
  from a `TreeWalker(SHOW_TEXT)`, skipping nodes inside that element. This is what caught the Baymax
  collisions; it checks the whole document, so it also catches an absolutely positioned element straying
  into the section below.
- *contrast* — screenshot with the text hidden via `addStyleTag`, then sample bands with PIL.
- *where artwork's content actually is* — threshold the luminance and take the row sums; that is how the
  share banner's crop was checked.

A `clip` passed to `page.screenshot` without `fullPage` is **viewport**-relative, so an element far down the
page needs `scrollIntoViewIfNeeded()` first or the clip lands outside the image and throws.

**Git.** Locally the SSH remote (`git@github.com:alexalspach/baymaxdotorg.git`) works, LFS is installed and
functioning (34 objects / 548 MB in `.git/lfs/objects`; GitHub Free gives 10 GiB), and PSDs commit through
the clean filter correctly. Deletes work. None of the bridge-session workarounds are needed.

## Key files and edits

- `assets/css/override.css` — `.number-11` (clone of the 10th-anniversary `.number-10`) for the big yellow "11";
  `.workshop_theme` uses **Fredoka** (Google font, 600, 2.45em — deliberately larger than `.workshop_year`'s 2em)
  instead of Permanent Marker; `.workshop_year` margin-top 1.1em for air above the conference block.
  `.speaker_face` is `width: 65%` with `border-radius: 50%` and a 0.3rem #E3E653 border, so **photos must be
  square** with the head centred and a little headroom; corners are clipped by the circle. The **Baymax
  gutter** block at the end of the file is the newest addition — see its own section above.
- Banner: one stack — Humanoids 2026 / Santa Clara, California, USA / December 7–9 — then `[conference site]`,
  then **"Monday, December 7, 2026 · Room TBD"**.
- Objectives: 2026 intro plus the 11 topic bullets. Now in the dark slot (see Page structure).
- Speakers: see above. Now in the first, teal slot.
- Schedule: intro line only, no table.
- `mixer/index.html` — the 2026 mixer invite (see Mixer page above).
- `images/logos/tri.png` — the TRI logo for the mixer's sponsor card.
- `images/banner/` — share images (renamed from `images/facebook/` on 2026-11-06). `banner.jpg` is the
  workshop page's **and the site homepage's**; `mixer-banner.jpg` is the mixer's. The Photoshop source
  folder is **still** `photoshop/facebook/` — only the published `website/` folder was renamed.
- `templates-from-2025.html` — the full 2025 speaker grid and schedule table, kept as copy/paste source.
  The speaker grid half has now served its purpose; keep it for the **schedule table**, delete once 2026's
  schedule is filled in.
- `images/logos/web/logos.png` — the six-logo organizer strip; see the Logos section for what is on it.
- `website/assets/images/banners/2026banner.jpg` — new banner art (1200×627), circuit-board + Baymax like
  2024/2025. Also at `images/banner/banner.jpg`. The art still carries a "PART 11:" line the page no longer
  has — regenerate if they should match.
- `website/index.html` — "Upcoming!" hero points at /workshop/2026; 2025 moved into Past Workshops; og/twitter
  image points into `workshop/2026/images/banner/`. **The homepage borrows the 2026 share image** — a future
  year's rollover breaks it unless updated in the same pass.

## Still TBD

- Room number and the conference's workshop code.
- The rest of the speakers, and the schedule.
- **Aykut Onol's photo and bio.** TRI publishes no individual researcher pages, so the bio is a draft from
  public sources (Google Scholar, his Northeastern RIVeR Lab publication history), marked with an HTML
  comment. `images/organizers/Onol_Aykut.jpg` is a generated placeholder.
- **Linking the mixer** from the workshop page — the button is written and commented out, but its href points
  at `/mixer` and needs to be `/workshop/2026/mixer`. Alex asked on 2026-11-06 for it to stay unlinked.
- Should the **TRI sponsorship** also appear on the workshop page, or only on the mixer page? Only the mixer
  page carries it as of 2026-11-06, which is what Alex asked for.
- Poster-session / demo links are commented out in the banner section.
- **`photoshop/facebook/banner.psd` has an uncommitted edit from 2026-09-13.** The exported JPGs
  (`2026banner.jpg` and the OG copy) are from 09-11 and the last commit touching the PSD is 09-10, so whatever
  changed on 09-13 was never exported and is not live. Open it, decide whether to re-export and commit or revert.

## Known issues

- **`.stamp` section titles (⚡Speakers⚡, ⚡Past⚡ Workshops) render as blank space.** The rule in
  `override.css` applies `-webkit-mask-image` from an old CodePen S3 asset
  (`s3-us-west-2.amazonaws.com/s.cdpn.io/8399/grunge.png`); when that URL fails the masked element disappears in
  Chrome/Safari but keeps its box. Affects the homepage and earlier years too. Fix: self-host the grunge texture
  under `assets/` and repoint the mask, or drop the mask.
- The **Objectives content has one unclosed `<p>` and one unclosed `<li>`** (9 open / 8 closed, 16 / 15).
  Pre-existing, inherited from the 2025 copy — browsers auto-close both, so nothing renders wrong, but it is
  worth tidying. Verified unchanged by the 2026-10-29 section swap.
- **The same Baymax/text collision exists on the 2025 and earlier pages**, which have their own copies of
  `override.css` and were left alone per the project's no-older-pages rule. The fix block is
  self-contained and could be pasted into those copies if it is ever wanted.
- `html { min-width: 320px }` in the vendor template means every page on the site is wider than the
  viewport below ~323px. See the gutter section above; left alone.
- The 2026 `images/speakers/` folder still holds the **2025 speakers' photos**, inherited when the page was
  copied (Bergamin ×2, Cheng, Cousineau ×2, Kim_Joohyung, Kim_Yongjae ×2, Mohajerani, Park ×2, Pollard).
  They are unreferenced by the 2026 page and can simply be deleted from a local checkout.
