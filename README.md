# Show Your Worth Circles

A single-page marketing site for **Show Your Worth Circles** — a transformative
10-week cohort experience rooted in Shelmina Abji's 8 intentional strategies
for career advancement and personal fulfillment, built toward each
participant's own Personal Success Plan (PSP).

This is a from-scratch rebuild using the brand's exact colors, its real logo
mark, the real 8 strategy names, and marketing copy supplied directly by the
client (mission statement + a "Why Show Your Worth Circles" one-pager).

Static site, no build step. Open `index.html` directly, or serve the folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Structure

```
index.html             Single-page site: hero, mission, what-sets-us-apart,
                        the 8 strategies (radial diagram), the 10-week
                        journey (timeline), who it's for, for organizations,
                        the framework, apply form, footer
assets/css/styles.css  Design tokens, layout, light/dark theme
assets/js/main.js      Mobile nav, scroll-reveal, footer year
```

## Design

- **Palette (exact, as supplied)** — Red `#db3c3d` / `#f04143` / `#f34a4c`,
  Navy `#1d274d`, Off-white `#f4f4f2`. Navy does double duty as the body-text
  ink color and as the dark "band" surface (hero, footer, contrast sections):
  it reads as a deep accent against the light ground, and as a raised panel
  against the dark-mode near-black ground, so the same value works in both
  themes.
- **Type** — Oswald (bold condensed, echoes the logo mark's poster energy)
  for headings, Work Sans for body copy, IBM Plex Mono for eyebrows/labels/
  numerals, Caveat only for the small script "your" flourish in the
  recreated logo badge.
- **Logo badge** — The client's real logo is a red circle with "SHOW" /
  "your WORTH" / "CIRCLES" stacked inside. That exact image file wasn't
  available to save as an asset (it arrived as an inline chat image, not an
  uploaded file), so it's **recreated in CSS/HTML** (`.badge` in
  `styles.css`) matching the same colors, layout, and lockup — it scales
  cleanly via CSS container queries from the 46px header mark up to the
  ~280px hero mark. **If you want the literal original logo file used
  instead of this recreation, attach it as a file upload (not a pasted
  image) and it can be dropped in as a real asset.**
- **The 8 Intentional Strategies** (`#strategies`) is a radial ring diagram —
  the eight strategies orbit a center "Your Worth" hub, echoing the
  "Circles" name. Collapses to a simple list under 760px.
- **The 10-Week Journey** (`#journey`) is a horizontal timeline: Week 1
  kick-off, Weeks 2–9 are the 8 strategies in order (one per week, per the
  "structured workbooks... tied to that week's strategy" detail from the
  client's one-pager), Week 10 wrap-up/PSP presentation.

## Content sourced directly from the client

- Mission paragraph — used verbatim (hero + `#mission`).
- The 8 intentional strategies and their order — used exactly as given.
- "What sets SYW Circles apart" (7 points) and "What can your organization
  expect?" (6 points) — from the supplied one-pager, lightly trimmed for
  length, not reworded in substance.
- Brand colors — used exactly as given (see above).

## ⚠️ Intentionally left out this round

Per the request to leave prior versions and build fresh from the materials
supplied, this build does **not** carry over content from earlier
iterations that wasn't part of this brief — team bios, testimonials, real
contact details, program logistics (pricing, exact schedule, signup links).
Add these back in whenever you're ready to supply them; ask and they can be
restored (verified real ones were sourced from the live site in an earlier
pass of this project, if that's useful as a starting point).

**Apply form** (`#apply`) — static markup only, `action="#"`. Needs a real
handler (your backend, Formspree, Netlify Forms, etc.) before launch.

## Browser support

Modern evergreen browsers (uses `aspect-ratio`, `color-mix()`, CSS
container queries, CSS custom properties, `prefers-reduced-motion`,
`IntersectionObserver`). No build tools, frameworks, or external JS
dependencies — only Google Fonts is loaded from a CDN.
