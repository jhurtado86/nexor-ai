# Brand Assets

Drop the following here when you have them. Claude Code will check this folder before falling back to placeholders.

## What goes here

- `logo.svg` or `logo.png` — Nexor AI logo (preferably SVG, transparent background)
- `logo-dark.svg` — dark-mode variant if you have one
- `favicon.ico` or `favicon.svg`
- `colors.json` — optional override of the design-system color tokens. Format:
  ```json
  {
    "nexor-emerald": "#065F46",
    "nexor-bg": "#FAFAF7"
  }
  ```
- `fonts/` — only if you're self-hosting fonts instead of Google Fonts
- `service-mockups/` — when you generate the device mockup images for service sections, drop them here named:
  - `service-1-website.png`
  - `service-2-automation.png`
  - `service-3-missed-call.png`
  - `service-4-reviews.png`
  - `service-5-seo.png`

## Rules for Claude Code

- If a file exists here, use it. Real beats placeholder.
- If `colors.json` exists, its values **override** `docs/02-design-system.md`.
- If this folder is empty, use the wordmark "Nexor AI" in Fraunces 600 as the logo and `https://placehold.co/640x480` for service images.
