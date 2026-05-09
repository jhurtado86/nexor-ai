# Nexor AI — Website Build

This folder contains everything Claude Code needs to build the Nexor AI marketing website.

## Read in this order

1. **`CLAUDE.md`** — workflow rules, screenshot loop, hard constraints. Read first, every session.
2. **`docs/01-brand.md`** — what Nexor is, who it serves, voice/tone.
3. **`docs/02-design-system.md`** — colors, typography, spacing, component rules.
4. **`docs/03-page-structure.md`** — section-by-section layout of the page.
5. **`docs/04-copy.md`** — exact headlines, subheads, body copy, FAQ answers.
6. **`docs/05-reference.md`** — how to use `reference/old-website.jpeg` (which sections to mirror, which to ignore).

## Folders

- `brand_assets/` — drop logo, custom fonts, hero images here. If empty, use placeholders per CLAUDE.md.
- `reference/` — `old-website.jpeg` is the previous Nexor site. **Reference, not template.** See `docs/05-reference.md`.
- `docs/` — split context. Don't mix these up; each file has one job.

## Deliverable

Single `index.html` in project root. Tailwind via CDN. All styles inline. Mobile-first.

## Servers / scripts (already in your environment)

- `node serve.mjs` → starts localhost:3000
- `node screenshot.mjs http://localhost:3000 [label]` → saves to `temporary screenshots/`
