# baymax.org

Static site for the **"Can we build Baymax?"** workshop series, held annually at
IEEE-RAS Humanoids. No build step, no framework — plain HTML/CSS/JS served as files.

## Layout

- `website/` is the published web root. Everything outside it (`photoshop/`, this file)
  is source material and does not ship.
- `website/index.html` — site homepage.
- `website/workshop/<year>/` — one self-contained folder per year, 2015 through 2026.
  **Each year carries its own copy of `assets/css/`**, so a CSS change is scoped to
  that year unless you deliberately copy it across.
- `website/mixer/` — the root-level mixer page (distinct from a year's own mixer page).
- `photoshop/` — PSD/AI sources, tracked in Git LFS.

## Hard rule: do not touch past years

Only the **current year's** folder is in play. `website/workshop/2025/` and earlier are
frozen — they are the public record of workshops that already happened. This includes
not "fixing" bugs there that also exist in the current year. If a fix would be nice to
have in older years, say so and leave it.

Current year: **2026** — `website/workshop/2026/`, plus its mixer page at
`website/workshop/2026/mixer/`.

## Preview

```
./startServer.sh          # python3 -m http.server --directory website, port 8000
```

Must be run from the repo root (`--directory website` is relative). Then:

- homepage → http://localhost:8000/
- 2026 workshop → http://localhost:8000/workshop/2026/
- 2026 mixer → http://localhost:8000/workshop/2026/mixer/

## Conventions that bite if you miss them

**Page-specific CSS goes in a scoped `<style>` block in that page's own `<head>`,
placed after the stylesheet links.** `assets/css/override.css` is shared by every page
within a year, so a `#banner` or `.bighero-font` rule there repaints the sibling pages
too. The Baymax gutter (below) is the one deliberate exception.

**The Baymax gutter is driven by custom properties, not breakpoints.** `#baymax` is
absolutely positioned at the page's left edge with `left: 0`; `#banner` gets symmetric
padding derived from `--baymax-w`. Everything descends from `--baymax-h`, so change that
one value and the gutter follows. Do not reintroduce stepped per-breakpoint sizes — the
steps and the reserved gutter disagree at intermediate widths, which is the bug this
replaced. Page type that must not wrap sizes itself off `--banner-content`, never raw `vw`.

**Speaker photos must be square**, head centred with a little headroom. `.speaker_face`
is `width: 65%` with `border-radius: 50%`, so corners are clipped by the circle.

**The homepage borrows the current year's share image.** `website/index.html`'s
`og:image` and `twitter:image` point into `workshop/2026/images/banner/`. Renaming or
moving that folder during a year rollover breaks the homepage unless it is updated in
the same pass.

**Git LFS** tracks `*.psd`, `*.ai`, `*.zip`. Confirm `git lfs` is installed before
staging any PSD — committing one without the clean filter puts a ~60 MB blob in history.

## Verify by measuring, not by eyeballing

Layout claims about this site have historically been wrong when eyeballed. Use Playwright
against the local server and measure:

- *overlap* — intersect an element's box against the client rects of every visible text
  node from a `TreeWalker(SHOW_TEXT)`. This is what catches Baymax colliding with banner text.
- *horizontal overflow* — `document.documentElement.scrollWidth - innerWidth`, swept with
  `setViewportSize` on one page object (much faster than reloading), ~100ms for reflow.
- *text width / line count* — a `Range` over the text node; `getClientRects().length`
  gives the number of lines.
- *contrast* — screenshot with text hidden via `addStyleTag`, sample bands with PIL.

Re-run the 280→2560px overlap sweep after any banner or Baymax change.

## Known pre-existing issues (not yours, don't be alarmed)

- `.stamp` section titles (⚡Speakers⚡ etc.) render as blank boxes — the
  `-webkit-mask-image` points at a dead CodePen S3 asset. Affects every year.
- The 2026 Objectives block has one unclosed `<p>` and one unclosed `<li>`, inherited
  from the 2025 copy. Browsers auto-close both.
- `html { min-width: 320px }` in the vendor template makes every page wider than the
  viewport below ~323px. Vendor file, left alone.

## Background

`docs/2026-workshop-page-status.md` is the running record for the 2026 page — what has
been built, every judgement call made and why, the open questions, and the measured
numbers behind the layout. Read it before substantive work on the 2026 page.
