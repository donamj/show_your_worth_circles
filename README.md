# Show Your Worth Circles

A 5-page marketing site for **Show Your Worth Circles** — a 10-session cohort
program for women, built on Shelmina Abji's 8 intentional strategies from her
book *Show Your Worth: 8 Intentional Strategies for Women to Emerge as
Leaders at Work*, culminating in each participant's own Personal Success
Plan (PSP).

This is a from-scratch redesign of [showyourworthcircles.com](https://www.showyourworthcircles.com/),
rebuilt with real content pulled from the live site (its React/Vite bundle
was read directly, since the page renders client-side) — real program facts,
real team bios, real testimonials, real signup links. Nothing here is
placeholder copy except where noted below.

Static site, no build step. Open `index.html` directly, or serve the folder
with any static file server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Structure

```
index.html             Home — hero, why-join, what-you'll-gain, session
                        structure (10-session ring diagram), ways-to-join teaser
about.html              Mission, Shelmina Abji's bio, team/advisors/ambassadors
testimonials.html       Full testimonials from Apurva Bhagali, Krishnapriya
                        Gelli, and Anara Satkeeva
join-us.html            Full "ways to join" (city-based / workplace) with real
                        signup links, global locations, become-a-facilitator flow
contact.html            Contact info + inquiry form (matches the live site's
                        real inquiry types)
assets/css/styles.css   Design tokens, layout, light/dark theme
assets/js/main.js       Mobile nav, scroll-reveal, footer year
```

## Design

- **Palette** — derived from the brand's real primary color
  (`hsl(348 83% 47%)`, a crimson/rose): Ink (`#241017`), Paper (`#f6efe4`),
  Wine (`#5c1a35`, mid/dark surface), Crimson accent (`#b3123f`), with a
  brighter Crimson variant for text on the dark wine surface. Full
  light/dark theme support via CSS custom properties.
- **Type** — Fraunces (display/headings), Work Sans (body), IBM Plex Mono
  (eyebrows, numerals, labels) — a deliberate upgrade over the live site's
  default system-font/Tailwind look, while keeping its real brand color.
- **The 10 Sessions** (`index.html#program`) is a radial ring diagram —
  Kick-off, 8 workbook sessions, and a Wrap-up arranged around a center hub,
  echoing the "Circles" name with something that's actually a real,
  accurate sequence (not invented content).

## Real content sourced from the live site

- Mission statement, hero copy, "Why Join a Circle?", "What You'll Gain"
  (4 items), and Session Structure facts (10 sessions incl. kick-off +
  8 workbooks + wrap-up; 7 participants per circle; alternating virtual/
  in-person; trained facilitators) — from the Home page.
- Shelmina Babai Abji's full bio, Dona Maria Jose's bio, advisors (Monica
  Mora, Karuna Thomas, Chinara Satkeeva), and ambassadors (Meenu Agarwal,
  Aashima Narula), with their real titles and LinkedIn links — from the
  About page.
- All 3 testimonials (Apurva Bhagali, Krishnapriya Gelli, Anara Satkeeva),
  full text, real names/roles — from the Testimonials page.
- Ways-to-join details (benefits, real ClickUp signup/request-info links),
  the 5 active locations (San Francisco, Seattle, Dallas, Cape Town,
  Bangalore), and the become-a-facilitator process + real "Apply to Lead"
  link — from the Join Us page.
- Contact info (email, phone, Seattle HQ, hours) and the real inquiry-type
  options — from the Contact page.
- Images are hot-linked to the org's own asset host
  (`horizons-cdn.hostinger.com`) — the same URLs the live site already
  serves publicly. This sandbox's network policy couldn't reach that host to
  verify them directly, so they're unverified from here, but they're the
  live site's own working image URLs. If any come back broken once
  deployed, re-save those specific images from the live site and swap in
  local paths.

## ⚠️ Still placeholder / needs your input

- **The 8 individual workbook/strategy titles** — the live site never names
  them individually (only "8 themed workbooks based on Shelmina Abji's
  book"), so the ring diagram labels sessions generically ("Workbook 1"–
  "Workbook 8") rather than inventing chapter titles. If you have the real
  chapter names, add them to the `.ring-node-label` text in `index.html`.
- **Contact form** (`contact.html`) — static markup only, `action="#"`.
  Needs a real handler (your backend, Formspree, Netlify Forms, etc.)
  before launch. The live site posts to `localStorage` client-side, which
  isn't a real backend either.
- **Pricing** — the live site doesn't publish pricing anywhere; this
  rebuild doesn't either. If the program has public pricing now, add it.

Search for the word "placeholder" to find every remaining spot:

```bash
grep -rin "placeholder" *.html
```

## Browser support

Modern evergreen browsers (uses `aspect-ratio`, `color-mix()`, CSS custom
properties, `prefers-reduced-motion`, `IntersectionObserver`). No build
tools, frameworks, or external JS dependencies — only Google Fonts is
loaded from a CDN, plus hot-linked images from the org's existing asset host.
