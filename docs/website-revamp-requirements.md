# CinnamonFoto Website Revamp Requirements (Draft v1)

## 1) Project Overview
CinnamonFoto will revamp its website to prioritize a stronger and more immersive portfolio presentation first, while preparing a clear path for bookings and conversion workflows.

- **Primary business priority:** Portfolio presentation quality
- **Secondary priority:** Booking system enablement
- **Geographic focus:** Sabah, Malaysia
- **Target launch:** December 2026
- **Budget:** Limited (phased implementation)

---

## 2) Goals & Success Metrics

### Core goals (priority order)
1. Improve portfolio presentation and storytelling quality.
2. Improve conversion readiness through "Book a slot" journeys.
3. Build long-term foundation for SEO, content, and automation.

### KPIs to track
- **Average session duration**
- **Bounce rate**
- **Booking conversion rate (%)**

---

## 3) Audience & Services

### Target audiences
- Wedding clients
- Family portrait clients (including Raya sessions)
- Graduation photo clients

### Services to feature
- Photography
- Videography

### Local positioning
- Primary SEO/service market: **Sabah, Malaysia**
- Initial keyword: **"wedding photographer keningau"**

---

## 4) Brand & Creative Direction

### Desired style
- Vibrant modern
- Editorial
- Documentary
- Warm cinematic

### Reference site
- https://thekhulafastudio.com

### Brand assets
- No finalized asset system yet; use placeholders in early design/dev.

---

## 5) Information Architecture (Planned Pages)

### Phase 1 launch pages (confirmed)
1. Home
2. Portfolio
3. About
4. Services & Packages
5. Testimonials
6. FAQ + Terms & Conditions
7. Contact & Socials
8. Booking

### Additional page strategy
- **Blog:** move to **Phase 3**
- Portfolio categories required (e.g., Weddings, Family/Raya, Graduation, etc.)

---

## 6) Functional Requirements

### Portfolio & media
- Category-based portfolio browsing
- Image lightbox experience
- Before vs After comparison component
- Video reels embedding/presentation

### Booking & contact
- Primary CTA: **Book a slot**
- Booking/inquiry form with custom fields (details to be finalized)
- Messaging integration:
  - WhatsApp
  - Telegram

### CMS/admin requirements
- Admin-editable packages and pricing
- Admin-editable core site content (at minimum: services, package cards, testimonials, FAQ)

### Language
- Single language only for now (no multilingual requirement)

### Performance
- Strong mobile performance and image optimization required

---

## 7) SEO Requirements

### Phase 1 SEO baseline
- On-page SEO setup for key landing pages
- Metadata and structured heading hierarchy
- Focus keyword support: "wedding photographer keningau"

### Deferred SEO scope
- City/area expansion pages: not in immediate scope
- Blog/content SEO: **Phase 3**

---

## 8) Technical Requirements

### Preferred stack
- **Next.js** (confirmed preference)

### Hosting
- Netlify is currently preferred, not final

### Tracking/analytics
- Analytics required, tooling undecided (to be finalized in implementation planning)

### Legal/compliance pages
- Privacy Policy
- Terms
- Cookie consent
- Data retention notice

---

## 9) Delivery Plan

### Phase 1 (design + MVP build)
- Core marketing pages
- Portfolio UX and visual identity implementation
- Package/pricing CMS support
- Basic inquiry/booking flow and CTA
- Baseline SEO and legal pages

### Phase 2
- Booking automations and workflow enhancements
- Analytics hardening and conversion tracking refinement

### Phase 3
- Blog/Journal implementation
- Content-led SEO expansion

---

## 10) Migration & Assets

- Existing site: **cinnamonfoto.co** (to be replaced/revamped)
- Photo/video assets available
- No redirect map required for now (subject to review before launch)

---

## 11) Open Decisions (Need Final Confirmation)
1. Final CMS choice for admin-editable packages/pricing in Next.js architecture.
2. Booking form field schema and required-vs-optional logic.
3. Preferred integration style for WhatsApp/Telegram (deep link only vs automated routing).
4. Final analytics stack (e.g., GA4 + events, privacy-friendly alternatives).
5. Hosting decision finalization (Netlify vs alternatives) based on budget/performance.

---

## 12) Recommended Next Artifacts
1. UX sitemap with page-level wireframe blocks.
2. Design system starter (typography, color direction, component styles).
3. Technical architecture decision record (Next.js + CMS + deployment).
4. Backlog with MoSCoW priorities for Phase 1.

---

## 13) Detailed Sitemap (Phase-Based)

```text
/
├── Home
├── Portfolio
│   ├── /portfolio/wedding
│   ├── /portfolio/family-raya
│   ├── /portfolio/graduation
│   ├── /portfolio/videography
│   └── /portfolio/[story-slug]
├── About
├── Services & Packages
│   ├── /services/wedding
│   ├── /services/family-raya
│   ├── /services/graduation
│   └── /services/videography
├── Testimonials
├── FAQ + T&C
│   ├── /faq
│   └── /terms-and-conditions
├── Contact & Socials
├── Booking
├── Legal
│   ├── /privacy-policy
│   ├── /terms
│   ├── /cookie-policy
│   └── /data-retention
└── (Phase 3) Blog
    ├── /blog
    └── /blog/[post-slug]
```

### Navigation recommendation
- **Primary menu (desktop):** Home, Portfolio, Services & Packages, About, Testimonials, FAQ, Contact
- **Persistent CTA button:** **Book a slot**
- **Footer nav:** Legal links, social links, WhatsApp, Telegram, location/service area

---

## 14) Page-by-Page Wireframe Content Outline

> Notes:
> - This is a **content wireframe** (block order + messaging intent), not visual UI.
> - Every page should keep a clear conversion path to **Book a slot**.

### 14.1 Home
1. **Hero (full-width visual reel/gallery)**
   - Headline: brand promise + style (vibrant/editorial/documentary)
   - Subheadline: Sabah-based photography/videography
   - CTAs: Book a slot, View portfolio
2. **Featured portfolio strips**
   - Wedding / Family Raya / Graduation / Video reels previews
3. **Why CinnamonFoto**
   - 3-4 differentiators (storytelling, direction style, turnaround, local familiarity)
4. **Services & package teaser**
   - Starting price bands (admin-editable)
5. **Before vs After section**
   - Slider comparison samples
6. **Testimonials highlight**
   - 3-5 featured reviews + trust markers
7. **Process snippet**
   - Inquiry → Consultation → Shoot → Delivery
8. **Final CTA banner**
   - Book a slot + WhatsApp + Telegram quick actions

### 14.2 Portfolio (Index)
1. **Portfolio hero + filter controls**
   - Category chips: All, Wedding, Family Raya, Graduation, Videography
2. **Masonry/grid gallery**
   - Mixed orientation cards
3. **Lightbox interaction**
   - Next/prev, keyboard nav, thumbnail rail
4. **Story cards**
   - Link to full session/case page
5. **CTA strip**
   - Like this style? Book a slot

### 14.3 Portfolio Story Detail (`/portfolio/[story-slug]`)
1. **Story hero** (cover image/video)
2. **Session context block**
   - Location, event type, style notes
3. **Narrative gallery sections**
   - Getting ready / ceremony / portraits / candid highlights
4. **Optional before vs after inserts**
5. **Related stories**
6. **Sticky CTA**
   - Book a slot / Ask on WhatsApp

### 14.4 About
1. **Founder/brand story intro**
2. **Philosophy & style manifesto**
3. **Behind-the-scenes reel/photo strip**
4. **Experience and credibility markers**
5. **CTA:** Meet us / Book a slot

### 14.5 Services & Packages
1. **Service overview hero**
2. **Service tabs/cards**
   - Wedding, Family Raya, Graduation, Videography
3. **Package cards (admin-editable)**
   - Inclusions, duration, deliverables, price
4. **Add-ons section**
5. **FAQ mini block (pricing-related)**
6. **CTA:** Check date availability / Book a slot

### 14.6 Testimonials
1. **Client quote wall**
2. **Featured stories with outcomes**
3. **Social proof links** (if available later)
4. **CTA:** Start your session

### 14.7 FAQ
1. **Accordion by topic**
   - Booking, preparation, payment, delivery, reschedule
2. **Unanswered question prompt**
   - WhatsApp/Telegram fallback
3. **CTA:** Book a slot

### 14.8 Terms & Conditions
1. **Scope of services**
2. **Payment and refund terms**
3. **Reschedule/cancellation policy**
4. **Usage rights and licensing**
5. **Liability and force majeure**

### 14.9 Contact & Socials
1. **Contact hero**
2. **Quick contact options**
   - WhatsApp, Telegram, email, social links
3. **Simple inquiry form**
4. **Service area map/text**
5. **CTA:** Go to full booking form

### 14.10 Booking
1. **Booking page intro**
   - What happens after submission
2. **Structured booking form**
   - Name, phone/email, shoot type, date, location, budget, notes
3. **Preferred contact channel selector**
   - WhatsApp/Telegram/Email
4. **Consent checkboxes**
   - Privacy + terms + data retention acknowledgement
5. **Success state**
   - Confirmation message + expected response time + fallback chat buttons

### 14.11 Legal Pages
- **Privacy Policy:** data collected, usage, retention, user rights
- **Cookie Policy:** cookie categories and consent behavior
- **Data Retention:** retention windows and deletion requests

### 14.12 Blog (Phase 3)
1. **Blog index with category filters**
2. **SEO article template**
3. **Related services CTA module**

---

## 15) Color Palette (Harmonized to Current Logo)

### 15.1 Logo-led anchor colors
Based on the supplied logo, the palette anchors around vivid magenta and deep indigo-violet tones.

- **Primary Accent (Magenta):** `#E12DEB`
- **Secondary Accent (Royal Violet):** `#3A1DC2`
- **Deep Brand Base (Indigo):** `#2A176D`

### 15.2 Supporting neutrals
- **Background (Light):** `#F7F7FB`
- **Surface (Card):** `#FFFFFF`
- **Text Primary:** `#121022`
- **Text Secondary:** `#4E4B63`
- **Border/Subtle UI:** `#DDD9EE`

### 15.3 Optional cinematic support tones
- **Warm Highlight:** `#FFC27A` (sparingly for badges/hover states)
- **Night Overlay:** `#0D0A1C` (hero overlays for readability)

### 15.4 Suggested usage ratio
- 65% neutrals (backgrounds, spacing, readability)
- 25% indigo/violet structure (headers, footers, section anchors)
- 10% magenta accent (CTAs, active states, important highlights)

### 15.5 Accessibility notes
- Prefer **white text on indigo/violet**, not on bright magenta unless darkened.
- For CTA buttons, use:
  - Primary: `#3A1DC2` background + `#FFFFFF` text
  - Hover: `#2A176D`
  - Secondary: `#E12DEB` outline/button accents with dark text `#121022`

---

## 16) Immediate Next Deliverables (Execution-Ready)
1. Low-fidelity wireframes for Home, Portfolio, Services, Booking.
2. High-level component inventory (Hero, Gallery, Lightbox, Package Card, CTA Banner, FAQ Accordion, Booking Form).
3. CMS field schema draft for package/pricing editing.
4. Tracking plan draft for KPIs:
   - session duration,
   - bounce rate,
   - booking conversion funnel.
