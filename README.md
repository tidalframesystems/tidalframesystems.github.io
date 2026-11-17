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

Currently all five cards use `data-status="coming-soon"`, but the visible labels escalate on purpose, one per card in page order: "Coming soon", "Coming soon-ish", "Coming eventually", "Coming after a lot more coffee", "Coming before the heat death of the universe". When a card is promoted, replace its joke label with the plain label for its new status.

## Mark a roadmap phase as current

In the `<!-- ROADMAP -->` section, move `class="is-current"` and `<span class="chip chip--current">Current</span>` to the new phase, and set the previous phase's chip back to a plain `<span class="chip">` reading `Complete` (once there is a dated note to link to). Phase 1 is current as of 17 November 2026.

## Add a technical note

`/notes/` is created when the first entry exists. Make `notes/index.html` (copy the header and footer from `index.html`, and use `../styles.css` and `../assets/...` paths), and give each entry a date. Then link to it from the Research Notes card.

## Preview locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```
