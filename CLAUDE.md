# CLAUDE.md — Nexor AI Website

## Always Do First
- **Read `README.md` and `docs/01-brand.md` through `docs/05-reference.md` in order** before writing any code in a new session.
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

## Project Context (Quick Reference)

- **Product:** Nexor AI — AI automation system for local service businesses (HVAC, roofing, plumbing, etc.)
- **Goal of site:** Convert visitors into booked demo calls.
- **Primary CTA everywhere:** "Book a Demo"
- **Single source of truth for copy:** `docs/04-copy.md` — do not invent headlines or body text.
- **Single source of truth for design tokens:** `docs/02-design-system.md` — do not invent colors or fonts.

## Reference Image Rules

- `reference/old-website.jpeg` is the **previous** Nexor site. Treat it as a **partial reference**, not a clone target.
- **Mirror these sections from the reference** (layout, spacing, structure):
  - Services display (stacked, alternating, with bullets + image)
  - "How It Works" 3-step section
  - "Why Businesses Choose Nexor AI" benefits grid
  - FAQ section
- **Do NOT copy** the calendar booking widget, the hero exactly as shown, or the testimonial styling. See `docs/05-reference.md` for full breakdown.
- For mirrored sections: match layout, spacing, hierarchy. Swap copy from `docs/04-copy.md`. Swap colors/type to match `docs/02-design-system.md` (which IS based on the reference, but verify).

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL.
- Start the dev server: `node serve.mjs` (serves the project root at `http://localhost:3000`)
- `serve.mjs` lives in the project root. Start it in the background before taking any screenshots.
- If the server is already running, do not start a second instance.

## Screenshot Workflow
- Puppeteer is installed at `C:/Users/nateh/AppData/Local/Temp/puppeteer-test/`. Chrome cache is at `C:/Users/nateh/.cache/puppeteer/`.
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots are saved automatically to `./temporary screenshots/screenshot-N.png` (auto-incremented, never overwritten).
- Optional label suffix: `node screenshot.mjs http://localhost:3000 label` → saves as `screenshot-N-label.png`
- After screenshotting, read the PNG from `temporary screenshots/` with the Read tool — Claude can see and analyze the image directly.
- **Do at least 2 comparison rounds** against `reference/old-website.jpeg` for any mirrored section. Be specific in critique:
  - "heading is 32px but reference shows ~24px"
  - "card gap is 16px but should be 24px"
  - "green is too saturated — reference uses #065F46, current is using default Tailwind emerald"
- Check every pass: spacing/padding, font size/weight/line-height, exact hex colors, alignment, border-radius, shadows, image sizing.
- Stop only when no visible differences remain on mirrored sections, or user says so.

## Output Defaults
- Single `index.html` file, all styles inline, unless user says otherwise.
- Tailwind CSS via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Configure Tailwind theme via inline `tailwind.config` to register Nexor brand tokens from `docs/02-design-system.md`. Don't rely on default palette.
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Service section mockup images: leave as placeholders sized correctly. User will generate and provide real images later.
- Mobile-first responsive.

## Brand Assets
- Always check `brand_assets/` first. If a logo file exists, use it. If a color file exists, those values override `docs/02-design-system.md`.
- If `brand_assets/` is empty, fall back to `docs/02-design-system.md` and use a wordmark "Nexor AI" in the display font as the logo.

## Anti-Generic Guardrails
- **Colors:** Never use default Tailwind palette (indigo-500, blue-600, emerald-500, etc.). Use the exact hex values from `docs/02-design-system.md`. Register them in `tailwind.config` as named tokens (e.g., `nexor-emerald`, `nexor-ink`).
- **Shadows:** Never use flat `shadow-md`. Use layered, color-tinted shadows with low opacity (emerald-tinted on key surfaces).
- **Typography:** Pair a display serif with a clean sans per `docs/02-design-system.md`. Tight tracking (`-0.03em`) on large headings, generous line-height (`1.7`) on body.
- **Gradients:** Avoid generic ones. If used, layer multiple radial gradients. Add subtle SVG noise filter for depth.
- **Animations:** Only animate `transform` and `opacity`. Never `transition-all`. Use spring-style easing.
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states. No exceptions.
- **Images:** Service mockup images sit on subtle gradient backgrounds with soft drop shadow, not flat on white.
- **Spacing:** Use intentional, consistent spacing tokens from the design system — not random Tailwind steps.
- **Depth:** Surfaces should have a layering system (base → elevated → floating), not all sit at the same z-plane.

## Hard Rules
- Do not add sections, features, or content not listed in `docs/03-page-structure.md`.
- Do not "improve" copy — pull it verbatim from `docs/04-copy.md`. If something feels off, flag it; don't rewrite silently.
- Do not stop after one screenshot pass.
- Do not use `transition-all`.
- Do not use default Tailwind blue/indigo as primary color.
- Do not use buzzwords like "revolutionary AI," "cutting-edge," "next-gen." Tone is direct, confident, no hype (see `docs/01-brand.md`).
