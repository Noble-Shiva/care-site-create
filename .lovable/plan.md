## Mantri Aroha Clinic — Landing Page

Build a single responsive landing page (`/`) that matches the two wireframes: mobile layout for narrow screens, desktop layout from `md:` up. Mobile-first, thumb-friendly, accessible.

### Design system (`src/styles.css`)
- Tokens from Brand Guide:
  - `--background` #F3FEFE, `--foreground` #2F3E46
  - `--primary` #0F8B8D (teal), `--primary-foreground` #FFFFFF
  - `--secondary` / accent surface #EAF8F7, soft teal #67C6C2
  - `--border` #DDEEEE
- Fonts via `<link>` in `__root.tsx`: serif display **Fraunces** for headings (matches wireframe's classical serif), **Inter** for body. Register in `@theme`.

### Routes
- `src/routes/index.tsx` — landing page (replace placeholder). Distinct SEO meta (title "Mantri Aroha Clinic — Care with Compassion", description, OG tags).
- Keep `__root.tsx` shell; add font links and update default meta/favicon later.

### Page sections (top → bottom)

1. **Header** (sticky)
   - Logo lockup: lung icon + "Mantri Aroha" + tagline "Care with Compassion". On desktop, secondary line "Respiratory & Family Care | Lung Health Library".
   - Desktop: nav links Home / About / Services / Lung Health Library / Book Appointment / Contact + filled "Book a visit" button.
   - Mobile: "Book a visit" pill + hamburger opening a Sheet drawer with the same nav.

2. **Hero**
   - Left: small lung icon + eyebrow "A practice built on compassion", H1 "Helping you breathe better every day", subcopy "Evidence-based care for" then condition pills (Asthma · COPD · Chronic Cough · Allergy · Preventive Lung Health).
   - Desktop CTAs: filled "Online Consultation / ఆన్‌లైన్ సంప్రదింపులు" and outlined "Book Clinic Visit / క్లినిక్‌లో సంప్రదింపులు".
   - Right: doctor portrait placeholder (soft aqua circle + neutral silhouette image until user uploads).
   - Mobile: stacks portrait above text with the lung illustration motif as shown.

3. **Trust strip** — 4 items with Lucide icons in soft-teal circles: Respiratory care for all ages, Family doctor you can trust, Second opinion & health queries, Preventive care for a healthier you. Horizontal on desktop, 2x2 grid on mobile.

4. **Service cards** (priority order: Online, In-Clinic, PFT)
   - 3 Cards with Lucide icon header (Video, Stethoscope, Activity), English + Telugu title, description, filled "BOOK NOW" button.
   - Desktop: 3-column; mobile: stacked.

5. **Lung Health Library** (desktop only per wireframe; condensed teaser on mobile)
   - 6 topic chips with icons: What is Asthma?, What is COPD?, Chronic Cough, Allergy & Breathing Problems, Quit Smoking, Pulmonary Function Test. "View all articles →" link.

6. **"Are you experiencing?" symptom checker card** (desktop sidebar in wireframe; on mobile renders as a full-width card below services)
   - Checkboxes: Persistent cough, Breathlessness, Wheezing, Chest tightness, Smoking history + "Book a consultation" CTA (no backend yet, just navigates to booking placeholder).

7. **About Dr Mantri Vijaya Bhaskar** (desktop section)
   - Portrait placeholder, bio, credentials "MBBS, DTCD, Chest Physician & Family Physician · 12+ years…", and a "Doctor's Promise" quote block.

8. **Footer**
   - Quick-action row: WhatsApp / Directions / Call / YouTube / Email — large tap targets, brand-colored icons. Mobile shows the 4-icon thumb bar from the wireframe; desktop shows the 5-up labeled version.
   - Bottom bar: © 2026 Mantri Aroha Clinic. All rights reserved. + Privacy Policy / Terms & Conditions / Disclaimer links (route stubs, not built yet).

### Links & integrations (placeholders, real-wired)
- WhatsApp: `https://wa.me/919876543210`
- Call: `tel:+919876543210`
- Email: `mailto:hello@mantriarohaclinic.in`
- Directions: Google Maps search URL placeholder
- YouTube: `#` for now
- "Book a visit" / "BOOK NOW" / "Book a consultation": all point to `#book` anchor for now (booking page comes in a later turn).

### Assets
- No AI image generation. Use Lucide icons throughout (Stethoscope, Video, Activity, ShieldCheck, ClipboardList, Users, Wind, Leaf, Cigarette, MessageCircle, MapPin, Phone, Youtube, Mail, Menu).
- Doctor portrait: neutral SVG silhouette placeholder inside a soft-aqua circle, with a visible "Photo coming soon" caption so it's obvious to swap.

### Out of scope this turn (future turns)
- About, Services, Lung Health Library, Book Appointment, Contact routes (stubs only in nav; we'll build next).
- Privacy / Terms / Disclaimer pages.
- GA4, Search Console, sitemap.xml, robots.txt, FAQ schema, favicon — covered in pre-launch pass.
- Booking backend (Lovable Cloud) — added when we wire forms.

### Technical notes
- TanStack Start file-route at `src/routes/index.tsx`; use shadcn `Button`, `Card`, `Sheet`, `Checkbox`.
- All colors via semantic tokens — no hardcoded hex in components.
- Responsive: mobile-first, `md:` breakpoint promotes to desktop layout. Use the `grid-cols-[minmax(0,1fr)_auto]` pattern for header rows.
- Telugu text rendered inline (system fonts handle Telugu on Android/desktop).
