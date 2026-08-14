# Maxis Fibre — Landing Page + Admin Dashboard

Premium, dark-themed, conversion-focused landing page for **Maxis Home Fibre** (referenced from applymaxisfiber.com EasyUni5 plans), with a full admin dashboard for editing all content — **no coding required**.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Landing page (reads content from localStorage) |
| `admin.html` | Admin dashboard (password-gated, writes to localStorage) |
| `screenshots/` | Visual references |

## Quick Start

1. Serve the folder (localStorage needs a server origin, not `file://`):
   ```bash
   cd maxis-fiber-landing
   python3 -m http.server 8080
   ```
2. Open `http://localhost:8080/index.html` — landing page.
3. Open `http://localhost:8080/admin.html` — admin dashboard.
4. Log in with password: `admin123` ⚠️ **change it first** — edit `ADMIN_PASSWORD` at the top of the `<script>` block in `admin.html`.

## Landing Page Sections

- **Sticky nav** — brand, section links, Apply Now CTA
- **Hero** — promo badge, bold H1 with yellow highlight, subheadline, dual CTAs (Apply Now + WhatsApp), trust checkmarks, live-speed gauge card, floating whole-home coverage card
- **Stats strip** — 1 Gbps / 100% unlimited / 3 min apply / 24/7 support
- **Plans** — 3 pricing cards (100Mbps RM89, 300Mbps RM99 ★Best Value, 500Mbps RM149 ★Most Popular with FREE 2× Mesh WiFi) — real prices from the Maxis EasyUni5 page
- **Benefits** — 6 feature cards (speed, unlimited, free install, router+mesh, postpaid discount, trusted network)
- **How It Works** — 3 steps
- **FAQ** — animated accordion (contract, penalty, installation, postpaid discount, phone line, activation time)
- **CTA band + lead form** — form opens WhatsApp with name / phone / chosen plan pre-filled
- **Footer** — brand, links, contact, legal disclaimer, discreet Admin link
- **WhatsApp float button** — pulses bottom-right

## Admin Dashboard

- **Login gate** — password `admin123` (change it!)
- **Sidebar sections** — General, Hero, Stats, Plans, Benefits, How It Works, FAQ, CTA Band, Footer, Colors
- **Per-card save** with Saved/Unsaved badges
- **List editors** — add/remove/edit plans (price, promo, features one-per-line, highlight toggle), stats, benefits, steps, FAQs
- **Colors & Style** — change primary CTA color, background, surface, text colors with live hex pickers
- **Backup** — Export JSON / Import JSON / Reset to defaults
- **Live refresh** — changes appear on the landing page instantly via the `storage` event (same browser, same origin)

## WhatsApp Integration

- Number + default message configured under **General** in the admin
- Every Apply button, plan card CTA, hero CTA, float button and the lead form build a `wa.me` link with a context-specific pre-filled message
- Default number is a placeholder (`60123456789`) — **set your real number in the admin before going live**

## Hosting

Any static host works: GitHub Pages, Netlify, Vercel, or the user's own Pi (serve with nginx or `python3 -m http.server`). Admin and landing page must be served from the **same origin** so they share localStorage.

## Notes

- Prices/plans scraped from the reference agent page (applymaxisfiber.com) — verify current Maxis pricing before launch.
- Trademarks belong to Maxis Broadband Sdn. Bhd.; the footer carries a standard disclaimer.
- Fonts: Inter (Google Fonts). Zero dependencies, zero build step.
