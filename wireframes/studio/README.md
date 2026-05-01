# CinnamonFoto Studio — Booking System Wireframes

HTML wireframes for `studio.cinnamonfoto.co` — the Raya photoshoot studio time-slot reservation system. Separate from the main `www` site wireframes.

## Overview

This system allows clients to browse, select, and pay for a Raya studio photoshoot session. It is a guest booking flow (no account required) with online deposit payment and optional Telegram notifications.

## Pages

### Public (client-facing)
- `index.html` — wireframe pack overview and navigation
- `landing.html` — landing page: hero, packages teaser, how-it-works, FAQ, CTA
- `gallery.html` — studio space gallery + backdrop options
- `packages.html` — full package details + add-ons
- `terms.html` — terms & conditions, deposit/cancellation policy

### Booking flow (3 steps)
- `book-slot.html` — Step 1: date calendar + time slot grid
- `book-details.html` — Step 2: client info, add-ons, Telegram consent
- `book-payment.html` — Step 3: order review + deposit payment
- `book-confirm.html` — confirmation, booking reference, Telegram opt-in

### Admin
- `admin-dashboard.html` — stats, today's schedule timeline, upcoming bookings
- `admin-bookings.html` — all bookings table with filters and status management
- `admin-slots.html` — week calendar view, block/unblock dates, buffer gap visualisation
- `admin-settings.html` — buffer gap, deposit %, operating hours, packages, Telegram bot config

## Key design decisions (wired in wireframes)

| Setting | Default (wireframed) | Configurable? |
|---|---|---|
| Buffer gap between slots | 10 minutes | ✓ Admin settings |
| Slot hold timer | 10 minutes | ✓ Admin settings |
| Deposit % | 50% | ✓ Admin settings |
| Minimum booking notice | 24 hours | ✓ Admin settings |
| Client notification | WhatsApp (always) + Telegram (opt-in) | ✓ |
| Payment gateway | Placeholder (Billplz wired) | TBD |

## How to open

Option 1: Open any file directly in a browser.

Option 2: Serve locally from the repo root:
```bash
python3 -m http.server 4173
```
then open `http://localhost:4173/wireframes/studio/index.html`.
