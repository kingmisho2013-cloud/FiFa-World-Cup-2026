# WorldPass — FIFA World Cup 2026 Ticket Booking

A booking.com-style web app for booking FIFA World Cup 2026 match tickets. Search fixtures across the 16 real host stadiums, pick a seat category, check out, and get a scannable QR ticket — all in a single self-contained HTML file with no build step.

> Demo / portfolio prototype. Not affiliated with FIFA. Fixtures and prices are sample data.

## Features

| Area | Details |
|---|---|
| Browse & search | Filter by team, host city, and stage; sort by date or price |
| Match detail | Kick-off time, stadium, capacity, and four ticket categories with live availability |
| Cart | Quantity 1–4 per match with running total |
| Checkout | Ticket-holder form + mock payment, all client-side validated |
| Confirmation | Booking reference and scannable QR code encoding `{ref, matchId, cat, qty}` |
| My Tickets | Bookings persisted in `localStorage`; re-view QR, print, or save as PDF |
| Responsive | Works down to mobile; keyboard focus preserved |

## Data

- 16 real host stadiums across the USA, Canada, and Mexico.
- 23 sample fixtures spanning group stage through the final.
- Stage-tiered pricing (Category 1–4), from group matches up to the final.

## Stack

- Vanilla JavaScript (single-page, state-driven render — no framework)
- Tailwind CSS (CDN)
- qrcodejs (CDN) for QR generation
- Google Fonts: Archivo (display) + Inter (body)

No bundler, package manager, or backend required.

## Run locally

Open `worldcup2026-tickets.html` in any modern browser. The CDN dependencies require an internet connection to load.

```bash
# optional: serve it
python3 -m http.server 8000
# then open http://localhost:8000/worldcup2026-tickets.html
```

## Deploy to GitHub Pages

1. Push `worldcup2026-tickets.html` to a repository (rename to `index.html` to serve it at the site root).
2. In **Settings → Pages**, set the source to your default branch, root folder.
3. Your app is live at `https://<username>.github.io/<repo>/`.

## Notes

- Payment is a demo only — no processor is connected and no card is charged. Do not enter real card details.
- `localStorage` persists tickets when hosted (e.g. GitHub Pages); it does not persist inside a sandboxed preview iframe.
- To adapt for production: wire the official 104-match schedule, add a payment gateway and real inventory/seat maps, and move availability server-side.

## Author

Mohamed Nassar
