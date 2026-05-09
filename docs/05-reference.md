# 05 — Reference Image Guide

The file `reference/old-website.jpeg` is a screenshot of the **previous** Nexor AI website.

It is a **partial reference**, not a clone target.

## Use it for layout & spacing on these sections

When building these sections, open the reference and match the structural feel — column ratios, vertical rhythm, image sizing, bullet placement. Copy comes from `docs/04-copy.md`. Colors and type come from `docs/02-design-system.md`.

### ✅ Mirror — Service sections (stacked, alternating)
- Two-column rows
- Image on one side, text on the other
- Eyebrow → H2 → 1–2 line description → bulleted list with check icons → CTA button
- Generous vertical spacing between each service
- Alternate which side the image is on between rows

### ✅ Mirror — How It Works
- Three numbered cards in a horizontal row
- Numbers prominent (large, in emerald or in a circle)
- Short title under the number
- 1–2 line body under the title

### ✅ Mirror — Why Businesses Choose Nexor AI
- 4-cell grid (the reference shows 4 cells in one row; we'll go 4 across desktop, 2x2 tablet, 1-col mobile)
- Each cell: small icon, short label, 1-line description
- Light, airy spacing — don't crowd the cells

### ✅ Mirror — FAQ
- Stacked accordion rows
- Thin divider line between rows
- Plus/minus icon on the right
- Question bold, answer plain

## Ignore these from the reference

### ❌ Hero
The reference hero is fine but we're rewriting it. Use the structure in `docs/03-page-structure.md`. Keep it text-forward, no hero image, eyebrow + headline + sub + two CTAs + trust line.

### ❌ Inline calendar widget (bottom of reference)
The green calendar grid block at the bottom of the reference is **not** in v1. Final CTA is a card with a headline and a single "Book Your Demo" button.

### ❌ Testimonial styling
Testimonials in the reference are sparse and small. We want slightly more substantial cards — see structure in `docs/03-page-structure.md`.

### ❌ Specific copy
Do not copy any text from the reference image. All copy comes from `docs/04-copy.md`.

### ❌ Footer styling
The reference footer is generic. Use the structure described in `docs/03-page-structure.md` and style it per the design system.

## Workflow

1. Build the section based on `docs/03-page-structure.md` + `docs/04-copy.md` + `docs/02-design-system.md`.
2. Run the screenshot loop (`node screenshot.mjs http://localhost:3000`).
3. For mirrored sections, open `reference/old-website.jpeg` side-by-side with your screenshot.
4. Compare specifically — column ratios, gap sizes, image proportions, vertical spacing between rows.
5. Note differences in concrete pixel terms ("their bullet gap is ~12px, mine is 20px") and fix.
6. Repeat at least twice per mirrored section.
