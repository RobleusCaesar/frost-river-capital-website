# frostrivercapital.com

Single-page static site for Frost River Capital. Hand-written HTML and CSS —
no framework, no build step, no dependencies. Open `index.html` in a browser
and that is the site.

## Layout

| File | Purpose |
|---|---|
| `index.html` | The one-pager (Company / Founder / Contact) |
| `privacy.html`, `terms.html` | Legal pages, copy ported from the previous site |
| `404.html` | Not-found page (also catches the old `/Privacy` and `/Terms` URLs) |
| `styles.css` | All styling, shared by every page |
| `assets/` | Images, icons, self-hosted fonts |
| `CNAME` | Custom-domain marker for GitHub Pages (`frostrivercapital.com`) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is, skipping Jekyll |

## Editing

- **Copy**: edit the HTML directly — the text lives in `index.html`,
  `privacy.html`, and `terms.html`. There is nothing to compile.
- **Styling**: everything is in `styles.css`. Colors and type are defined as
  CSS variables in the `:root` block at the top.
- **Fonts**: EB Garamond 400 and Barlow 400 (latin subset, woff2) are
  committed in `assets/fonts/` and declared at the top of `styles.css`.
  Both are SIL Open Font License. No external font requests.
- **Images**: the headshot ships as WebP with a JPEG fallback
  (`assets/portrait-720.*`, 720×720). The masthead band is
  `assets/band-1240.jpg` (1240×300, shown at 620×150 so it stays sharp on
  2x displays; JPEG beat WebP on size for this photo). If you replace
  either, keep roughly those dimensions and re-compress — the whole page
  budget is 500&nbsp;KB.
- **Icons / OG image**: `assets/favicon.svg` is the master mark (glyphs are
  outlined paths, no font dependency). `assets/apple-touch-icon.png`,
  `assets/favicon-32.png`, and the 1200×630 `assets/og.png` are rasterized
  from the same artwork.

## Deploys

Pushing to `main` is the deploy. GitHub Pages serves the repository root of
`main` at https://frostrivercapital.com (via the `CNAME` file plus DNS
records at the registrar). There is no CI and no build — what is committed
is what is served. Changes are typically live within a minute or two of the
push.

Local preview: open `index.html` directly, or from the repo root run:

```
npx serve .
```
