# Tidal Frame Systems — website

One-page static site. No build step, no external libraries, no tracking, no JavaScript.

- `index.html` — all page copy and the inline SVG diagrams
- `styles.css` — layout, colors and the status-card component
- `404.html` — not-found page (styles inline on purpose)
- `assets/` — logo mark, favicon, concept rendering (`hero.jpg`), old social preview (`social-preview.jpg`, not currently used)
- `.nojekyll` — tells GitHub Pages to serve the files as-is

Live at https://tidalframesystems.github.io/

## House rules for content

- No number goes on the site without a dated record behind it.
- Never claim prototypes, customers, partners, grants, patents, awards or results that are not real and documented.
- Concept renderings are always captioned as concepts.

## Edit copy

Open `index.html` and edit the text inside the relevant `<section>` (each one is marked with a comment such as `<!-- STATUS -->`).
**Every time you change the site, update the "Last updated" date in the footer.**

### Cache-busting

Browsers and GitHub Pages cache files for about 10 minutes. If a visitor gets new HTML with an old cached stylesheet, the page can break. So whenever `styles.css` or an asset changes, bump the `?v=YYYYMMDD` query string on **every** reference to it in `index.html` (stylesheet, favicon, logo, `hero.jpg`). Leave the small inline `<style>` safety net in `<head>` in place; it stops images from widening the page even when a stale stylesheet is cached.

## Change a technology card's status

Each card is an `<article class="tech-card" data-status="...">`. Change **both** of these together:

1. the `data-status` attribute: `exploring`, `in-development` or `coming-soon`
2. the label text in `<p class="tech-card__status">`: `Exploring`, `In development` or `Coming soon`

| Label | Meaning |
|---|---|
| Exploring | Research and concept work only; no design files or hardware yet |
| In development | Active design or build |
| Coming soon | Something real exists; public details pending |

Add a `/notes/` entry explaining why the status changed.

The Research Notes card also has a small note beside its label ("First entry in progress."). Delete that `tech-card__status-note` line when the first `/notes/` entry is published.
## Mark a roadmap phase as current

In the `<!-- ROADMAP -->` section, move `class="is-current"` and `<span class="chip chip--current">Current</span>` to the new phase, and set the previous phase's chip back to a plain `<span class="chip">` reading `Complete` (once there is a dated note to link to). Phase 1 is current as of 17 November 2026.

## Add a technical note

`/notes/` is created when the first entry exists. Make `notes/index.html` (copy the header and footer from `index.html`, and use `../styles.css` and `../assets/...` paths), and give each entry a date. Then link to it from the Research Notes card.

## Preview locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```
