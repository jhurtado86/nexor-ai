# 03 — Page Structure

Build sections in this exact order. Anchor IDs listed for nav scrolling.

## Global

### Nav (sticky)
- Left: Nexor AI wordmark/logo (links to `#top`)
- Center: `Services` (`#services`), `How It Works` (`#how-it-works`), `FAQ` (`#faq`)
- Right: `Book a Demo` (primary pill button → opens demo flow / scrolls to `#book`)
- Mobile: hamburger → slide-down panel with same links

### Footer
- Left: wordmark + one-line tagline
- Center: link columns — Company (About, Contact), Services (5 service names linking to anchors), Legal (Privacy, Terms)
- Right: small "Book a Demo" CTA + email
- Bottom strip: © Nexor AI [year]

---

## 1. Hero — `#top`

- Eyebrow pill: "AI for Service Businesses"
- H1: **Automate Your Business. Capture More Leads. Close More Jobs.** *(emerald-color the words "Capture" and "Close")*
- Sub: We build systems that capture, follow up, and convert your leads automatically — so you never miss another job.
- Two CTAs side-by-side: `Book a Demo` (primary) + `See How It Works` (secondary)
- Below CTAs: row of 5 small star icons + "Trusted by service businesses across the U.S."
- No hero image — keep it text-forward, ample whitespace. Subtle radial gradient (emerald at 4% opacity) behind headline.

## 2. Social Proof — testimonials

- Eyebrow: "RESULTS"
- H2: **Results That Speak for Themselves**
- Sub: One line. Real outcomes from real owners.
- 3 testimonial cards in a row (stack on mobile):
  - 5-star row at top
  - Quote (2–3 lines)
  - Name, business type, city
- Soft `shadow-card`. Background `nexor-surface-soft` on the section.

## 3. Systems Overview — `#services` (intro block)

- Eyebrow: "WHAT YOU GET"
- H2: **Powerful Systems, Simplified** *(emerald the word "Simplified")*
- Sub: One sentence — see copy doc.
- This is just the section opener. Five service blocks follow it.

## 4. Service Sections (stacked, alternating)

Five back-to-back service blocks. Each is its own row. Alternate image left/right starting with image RIGHT on the first.

For each: eyebrow → H2 → 2-line description → 3–4 bullets (✓ emerald checkmarks) → "See How It Works" button.

Image is a placeholder for now (`https://placehold.co/640x480` with caption "device mockup pending"). User will provide real device mockups later.

**Order:**
1. **Functional Website** — image right
2. **AI Automation System** — image left
3. **Missed Call Text Back** — image right
4. **5-Star Review Funnel** — image left
5. **Local SEO** — image right

(Full bullets and copy in `docs/04-copy.md`.)

## 5. How It Works — `#how-it-works`

- Eyebrow: "HOW IT WORKS"
- H2: **Three steps. That's it.**
- Three numbered cards in a row (1 / 2 / 3), with a thin connecting line between numbers on desktop:
  1. **Book a Demo** — short body
  2. **We Build Your System** — short body
  3. **You Start Getting More Leads** — short body
- Background: `nexor-surface-soft`

## 6. Why Businesses Choose Nexor AI

- Eyebrow: "WHY NEXOR"
- H2: **Why Businesses Choose Nexor AI**
- Sub: One line.
- 4-column grid (2x2 on tablet, 1-col mobile). Each cell:
  - Small emerald icon
  - Short label (3–4 words)
  - 1-sentence description

Cells:
1. **No Missed Leads** — Every call, every form, captured and routed instantly.
2. **Done-for-You Setup** — We install everything. You don't touch a thing.
3. **Built for Service Businesses** — Not generic SaaS. Tuned for HVAC, roofing, plumbing.
4. **Fast Implementation** — Up and running in days, not months.

## 7. Industries — "Built for Home Service Professionals"

- H3 (smaller than other sections, more like a band): **Built for Home Service Professionals**
- Sub: One sentence.
- Single row of icon + label tiles: HVAC, Roofing, Auto Glass, Plumbing, Electrical, General
- Light, almost subtle. Section padding tighter than others.

## 8. FAQ — `#faq`

- Eyebrow: "FAQ"
- H2: **Frequently Asked Questions**
- Sub: One line.
- 5–6 expandable rows. Default first row open.
- Questions in `docs/04-copy.md`.

## 9. Final CTA — `#book`

- Card-style block, centered, on `nexor-surface-soft` panel inside main background
- H2: **See How Nexor AI Can Bring You More Customers** *(emerald "More Customers")*
- Sub: We'll show you exactly how the system works and how it can be set up for your business.
- Single primary CTA: `Book Your Demo`
- No form here in v1 — CTA links to a calendar booking URL placeholder (`#`).

---

## What NOT to include

These are explicitly excluded from v1:
- Inline calendar booking widget (the green calendar grid in the reference). Just a CTA button.
- Pricing section. Pricing is mentioned only in FAQ.
- Blog or resources.
- Login / customer portal links.
- Live chat widget.
- Newsletter signup.
