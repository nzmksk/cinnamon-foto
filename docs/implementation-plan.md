# CinnamonFoto — Implementation Plan

> This document captures all technical decisions and phased implementation scope agreed upon during planning.
> Reference alongside `website-revamp-requirements.md` for full project context.

---

## Core Stack (all phases)

| Layer | Choice | Notes |
|-------|--------|-------|
| Framework | Next.js | Confirmed preference |
| Hosting | Netlify | Preferred, not yet final |
| CMS / Admin | Sanity | Studio embedded at `/admin` |
| Database | Supabase | Phase 2+, free tier |
| Email | Resend | Booking notifications |
| Payment | CHIP | MYR-native; FPX, DuitNow QR, cards, e-wallets |

---

## Phase 1 — Website Revamp + Admin Dashboard

**Goal:** Replace cinnamonfoto.co with a portfolio-first marketing site. All key content is editable by the client via the Sanity admin dashboard. No booking automation yet — booking page is an inquiry form only.

### Pages

- Home
- Portfolio (index + `/portfolio/[story-slug]`)
- About
- Services & Packages
- Testimonials
- FAQ + Terms & Conditions
- Contact & Socials
- Booking (inquiry form only)
- Legal: Privacy Policy, Cookie Policy, Data Retention, T&C

### Sanity content types

```
siteSettings      → hero headline, subheadline, CTA labels, tagline, contact links
package           → category, name, starting price, inclusions[], duration, deliverables, featured flag
portfolioItem     → category, title, images[], caption, story slug, featured flag
videoReel         → title, embed URL (YouTube/Vimeo), thumbnail, category
testimonial       → client name, quote, session type, location, stars, featured flag
faqItem           → question, answer, category (booking/payment/delivery/reschedule)
beforeAfterPair   → before image, after image, label/caption
processStep       → step number, label, description
```

### What the client can manage from the admin dashboard

- Package names, starting prices, inclusions, durations, deliverables
- Portfolio photos and captions (all categories)
- Video reel embed links and thumbnails
- Testimonials (add, edit, toggle featured)
- FAQ entries (add, edit, reorder by category)
- Hero headline, subheadline, and CTA button labels
- Before/After comparison image pairs

### Sanity Studio

- Embedded in the Next.js app at `/admin`
- No separate deployment needed
- Runs on Netlify alongside the public site

---

## Phase 2 — Booking System + Payment Gateway

**Goal:** Accept and manage booking inquiries, handle availability, and collect deposits via CHIP.

### Booking flow

```
Client fills booking form (Next.js)
  → Submission saved to Supabase
  → Owner notified via email (Resend) + WhatsApp
  → Owner reviews inquiry in admin
  → Owner confirms and sends CHIP payment link for deposit
  → Client pays deposit → booking confirmed
```

> Booking is intentionally inquiry-led (not instant), matching the consultative nature of photography sessions.

### What gets built

- Booking form → Supabase table (name, phone/email, shoot type, date, location, budget, preferred contact channel, notes)
- Email notification to owner on new submission (Resend)
- Admin page in Next.js: view, filter, and manage booking submissions
- Blocked dates calendar — admin marks unavailable dates; reflected on client-facing booking form
- CHIP integration via Next.js API routes for generating deposit payment links
- Webhook handler for CHIP payment status updates (paid / failed / expired)
- Booking page CMS content (`bookingPageContent` Sanity type) — intro text, confirmation message, expected response time

### CHIP payment methods supported

- FPX (online banking)
- DuitNow QR Online
- Credit / debit cards
- E-wallets (Touch 'n Go, Boost)

### New Sanity content type (Phase 2)

```
bookingPageContent  → intro text, post-submission confirmation message, expected response time copy
```

---

## Phase 3 — Blog + Multilanguage Support

**Goal:** Enable content-led SEO expansion via a blog/journal and add Bahasa Malaysia language support.

### Blog

New Sanity document types:

```
blogPost      → title, slug, author, publishedAt, category[],
                featuredImage, excerpt, body (Portable Text), SEO fields
blogCategory  → name, slug
```

**Portable Text** (Sanity's rich text format) supports:
- Inline images with captions
- Embedded video reels
- Callout/highlight blocks
- Inline CTA components (e.g. "Book a slot" mid-article)

### Multilanguage (English + Bahasa Malaysia)

**Plugin:** `@sanity/document-internationalization`

| Content | Strategy | Reason |
|---------|----------|--------|
| Blog posts, full pages | Document-level (separate doc per language) | Content differs significantly per language |
| Packages, FAQ, site settings | Field-level (`{ en: "...", ms: "..." }`) | Same structure, translated strings only |

**Next.js routing:** `next-intl`
- `/en/...` — English
- `/ms/...` — Bahasa Malaysia

---

## Sanity Schema Growth Across Phases

```
Phase 1  →  siteSettings, package, portfolioItem,
             videoReel, testimonial, faqItem,
             beforeAfterPair, processStep

Phase 2  →  + bookingPageContent

Phase 3  →  + blogPost, blogCategory
             + @sanity/document-internationalization enabled across all types
```

No CMS migration between phases. Schema grows incrementally — the client's admin interface remains consistent throughout.

---

## Open Decisions

1. Netlify vs alternative hosting — finalize before Phase 1 launch
2. Booking form field schema — required vs optional fields, exact field list
3. WhatsApp/Telegram integration style — deep link only vs automated message routing
4. Analytics stack — GA4 vs privacy-friendly alternative (e.g. Plausible, Fathom)
5. CHIP account registration and sandbox testing — required before Phase 2 build
