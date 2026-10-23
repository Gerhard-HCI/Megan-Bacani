# Megan-Bacani

Guest itinerary site for **Megan Bacani & Jay Patel** — Tokyo, 7–16 November 2026.
Two guests, nine nights, built on the Happy Camper itinerary template.

- **Live:** https://megan-jay.happycamper.food (GitHub Pages, custom domain via `CNAME`)
- **Source of truth:** *HCI Canvas/Program for Megan BACANI 2026/10* (Google Sheets) — CANVAS, Confirmation, Wish List and Diet tabs
- **Deliverable:** `index.html`, a single self-contained file (no build step, no dependencies beyond Google Fonts and the Open-Meteo weather call)

## Tabs

Itinerary · Discover · Wish List · Visited · Diet · Utilities · Statement · Contacts & Emergency

The Statement tab is encrypted client-side (AES-GCM, PBKDF2 250k rounds) with two
separate blobs — a guest view and an internal view that additionally shows cost and
margin. Access codes are **not** stored in this repo; they are shared with the guest
and the team directly. To re-encrypt after editing figures, open the site with
`#encrypt` appended to the URL and use the console.

## Programme status

**Confirmed**

| Date | Time | Booking |
|---|---|---|
| Mon 9 Nov | 12:00 | Sushi Meino — private buyout |
| Wed 11 Nov | 12:00 | Tempura Naruse — private buyout |
| Fri 13 Nov | early | Toyosu Market — VIP guided visit |
| Fri 13 Nov | 12:00 | Sushi Saito (3★) |
| Sat 14 Nov | 20:30 | Kaiseki Suetomi — food settled on the night, est. ¥100,000 pp |

**Outstanding priorities** — Sugita, Ikkou, Arai. Four evenings still open to place
them: 8, 10, 12 and 15 November.

**Also discussed** — Amamoto; a snow-crab or seasonal kaiseki evening; Mekumi (would
need a west-coast overnight); Hikita (pencilled previously, now off the canvas).

**Diet** — nothing submitted yet. The tab shows a placeholder and asks for allergies
and preferences ahead of the first counter on 9 November.

## Change log

### 2026-10-24 — sync to live canvas (`8945c89`)
The earlier build came from a stale `.xlsx` export. Rebuilt against the live sheet:

- Statement: added the second payment (Invoice 2314258) and the Suetomi reservation
  fee; re-dated to today; FX note set to the Confirmation sheet's rate
- Kaiseki Suetomi promoted from suggestion to confirmed, 14 Nov at 20:30
- Sugita (8 Nov) and Hikita (12 Nov) removed — both dropped off the canvas
- Wish List and banner chips reordered to match

### 2026-10-24 — open days (`f187041`)
Tied the unbuilt days to the outstanding sushi targets so the day notes and the Wish
List tab agree.

### Initial build
Generated from the Happy Camper master template: navy/gold branding, tab shell,
JST clock, per-city weather, and the encrypted statement module carried over
unchanged. Content replaced throughout from the Bacani canvas — itinerary, wish
list, 22 previously-visited restaurants, Tokyo-only Discover tab, and the currency
converter switched to JPY ↔ USD.

## Notes for whoever picks this up

- Trip content lives in the `TRIP`, `WL_*`, `VISITED`, `DISCOVER` and `DIET`
  variables near the top of the script block in `index.html`
- The sheet still shows `Totyosu Market` (typo) on CANVAS row 5, and the two payment
  rows on Confirmation carry no dates — the statement lists them by invoice number
- The repo is public, so the page is reachable by anyone with the link and can be
  indexed; adding a `robots.txt` disallow would keep it out of search results
