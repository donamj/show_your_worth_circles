# Show Your Worth Circles

Marketing site for **Show Your Worth Circles** — a 10-week cohort experience for
women, built on Shelmina Abji's eight career-advancement strategies, culminating
in each participant's own Personal Success Plan (PSP).

Static site, no build step. Open `index.html` directly, or serve the folder
with any static file server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Structure

```
index.html            All page content and section markup
assets/css/styles.css  Design tokens, layout, light/dark theme
assets/js/main.js      Mobile nav, FAQ accordion, scroll-reveal, footer year
```

## Design

- **Palette** — Ink (`#241329`), Paper (`#f2ecdf`), Plum (`#5b2a5e`), Bronze accent
  (`#a9812e`), Mauve-grey for muted text. Full light/dark theme support via CSS
  custom properties (`prefers-color-scheme` + a `data-theme` override hook).
- **Type** — Fraunces (display/headings), Work Sans (body), IBM Plex Mono
  (eyebrows, numerals, labels).
- **The 8 Strategies** section is a radial "compass" layout — the eight
  strategies literally orbit a center "Your Worth" hub, echoing the site's
  "circles" concept. It collapses to a stacked list under 760px, where a ring
  layout stops making spatial sense.
- **The 10-Week Journey** section uses numbered circle markers because it's an
  actual sequence (weeks 1–10 in four phases) — the one other place the
  "circle" motif reappears structurally rather than decoratively.

## ⚠️ Placeholder content to replace before launch

This build ships with realistic-but-invented copy so the site is fully
navigable and visually complete. The following need real content, and are
each marked with `[Placeholder: ...]` text or an HTML comment inline:

- **The 8 Strategies** (`#strategies`) — the eight strategy names and
  descriptions are drafted to fit the framework described, but are **not**
  confirmed against Shelmina Abji's actual published strategies. Confirm exact
  names/order/wording. (Flagged on-page with a small disclaimer line.)
- **Testimonials** (`#testimonials`) — three placeholder quotes with
  `[Placeholder Name]` / `[Placeholder Title]` attributions. Replace with real
  cohort feedback (get permission to use names/titles).
- **About the framework** — one to two sentences confirming Shelmina Abji's
  bio/credentials and the book or body of work the strategies are drawn from,
  plus a real link (currently `href="#"`).
- **FAQ** (`#faq`) — weekly time commitment, format (virtual/in-person/hybrid),
  cohort size, pricing/payment plans, and next cohort start date are all
  placeholders.
- **Apply section** (`#apply`) — "next cohort start date" is a placeholder.
  The form itself is static markup only: `action="#"` needs to point at a real
  form handler (Formspree, Netlify Forms, a backend endpoint, etc.) before
  launch — right now submissions go nowhere.
- **Footer contact** — `hello@showyourworthcircles.com` is a placeholder
  address, and the Instagram/LinkedIn links are `href="#"` stand-ins.

Search the codebase for `Placeholder` (case-insensitive) to find every
instance:

```bash
grep -rin "placeholder" index.html
```

## Browser support

Modern evergreen browsers (uses `aspect-ratio`, `color-mix()`, CSS custom
properties, `prefers-reduced-motion`, `IntersectionObserver`). No build tools,
frameworks, or external JS dependencies — only Google Fonts is loaded from a
CDN.
