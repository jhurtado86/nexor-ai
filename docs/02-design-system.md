# 02 — Design System

All values here are normative. Register them in `tailwind.config` as named tokens. Do not introduce other colors, fonts, or sizes without flagging.

## Colors

### Brand
| Token | Hex | Use |
|---|---|---|
| `nexor-emerald` | `#065F46` | Primary CTA buttons, accent words in headlines, key icons |
| `nexor-emerald-soft` | `#10B981` | Hover states, secondary accents (use sparingly) |
| `nexor-teal` | `#0F766E` | Tertiary accent — links, small flourishes only |

### Surfaces
| Token | Hex | Use |
|---|---|---|
| `nexor-bg` | `#FAFAF7` | Main page background (warm off-white, NOT pure white) |
| `nexor-surface` | `#FFFFFF` | Cards, elevated panels |
| `nexor-surface-soft` | `#F4F4F0` | Alternating section backgrounds for visual rhythm |

### Ink
| Token | Hex | Use |
|---|---|---|
| `nexor-ink` | `#0B0F14` | Headlines, primary text |
| `nexor-ink-2` | `#3F4654` | Body copy |
| `nexor-ink-3` | `#7A8290` | Captions, muted helper text |
| `nexor-line` | `#E6E6DF` | Borders, dividers |

### Color rules
- Emerald is **rare and intentional**. Used for: primary CTA, ~2 accent words in the hero headline, service icons, and the "✓" check marks in lists. That's it.
- Never use Tailwind's default `emerald-500` or `green-600` — they're too saturated. Always use `#065F46`.
- Body copy is `nexor-ink-2`, not pure black. Headlines are `nexor-ink`.

## Typography

### Fonts
- **Display (headings):** `Fraunces` — serif, expressive, with optical-size axis. Load via Google Fonts: weights 500–700, opsz 9–144.
- **Body / UI:** `Inter Tight` — clean sans, slightly condensed feel that sits well next to Fraunces. Weights 400, 500, 600.
- **Mono (small accents like badges, stats):** `JetBrains Mono` — weight 500.

NOTE: Fraunces and Inter Tight are intentional non-defaults. Do not substitute Inter, Roboto, or Space Grotesk.

### Scale (mobile → desktop)
| Role | Mobile | Desktop | Weight | Tracking | Line-height |
|---|---|---|---|---|---|
| Hero H1 | 40px | 72px | 600 (Fraunces) | -0.03em | 1.05 |
| Section H2 | 32px | 48px | 600 (Fraunces) | -0.025em | 1.1 |
| Card H3 | 22px | 26px | 600 (Inter Tight) | -0.01em | 1.25 |
| Body L | 17px | 19px | 400 (Inter Tight) | 0 | 1.6 |
| Body | 15px | 16px | 400 (Inter Tight) | 0 | 1.7 |
| Caption | 13px | 13px | 500 (Inter Tight) | 0.01em | 1.4 |
| Eyebrow | 12px | 12px | 500 (JetBrains Mono) | 0.12em UPPERCASE | 1 |

### Headline pattern
Hero and section headlines use **mixed weight emphasis**: most words in `nexor-ink`, 1–2 key words in `nexor-emerald`. See `docs/04-copy.md` for which words to color.

## Spacing

Use these tokens. Don't pick arbitrary Tailwind steps.

| Token | Px | Use |
|---|---|---|
| `space-xs` | 8 | Inline gaps, icon→text |
| `space-sm` | 16 | Tight component padding |
| `space-md` | 24 | Standard card padding, list gaps |
| `space-lg` | 40 | Component-to-component vertical |
| `space-xl` | 64 | Sub-section vertical rhythm |
| `space-2xl` | 96 | Section-to-section (mobile) |
| `space-3xl` | 128 | Section-to-section (desktop) |

Page max-width: **1200px**, centered with 24px gutters mobile / 48px gutters desktop.

## Radii

- `radius-sm`: 8px (badges, small buttons)
- `radius-md`: 14px (cards, inputs)
- `radius-lg`: 22px (large feature panels, image frames)
- `radius-pill`: 999px (CTAs, eyebrow pills)

## Shadows

Layered, emerald-tinted, low opacity. Never flat gray.

```
shadow-card:
  0 1px 2px rgba(11, 15, 20, 0.04),
  0 8px 24px -8px rgba(6, 95, 70, 0.08)

shadow-elevated:
  0 2px 4px rgba(11, 15, 20, 0.05),
  0 16px 40px -12px rgba(6, 95, 70, 0.12)

shadow-cta:
  0 1px 2px rgba(11, 15, 20, 0.06),
  0 12px 28px -10px rgba(6, 95, 70, 0.35)
```

## Buttons

### Primary ("Book a Demo")
- Background: `nexor-emerald`
- Text: white, 15px, weight 600
- Padding: 14px 26px
- Radius: `radius-pill`
- Shadow: `shadow-cta`
- Hover: lift 1px (`translateY(-1px)`), shadow intensifies
- Active: translateY(0)
- Focus: 2px ring `nexor-emerald` at 30% opacity, 2px offset

### Secondary ("See How It Works", "Book a Demo" alternates)
- Background: transparent
- Border: 1px `nexor-line`
- Text: `nexor-ink`, 15px, weight 600
- Same padding/radius as primary
- Hover: background `nexor-surface-soft`

## Components

### Eyebrow tag (above section H2s)
Small uppercase mono text in `nexor-emerald`, optionally inside a pill with `nexor-emerald` at 8% bg opacity and 1px border at 16% opacity.

### Service section card
- Two-column on desktop, stacked on mobile
- Image side: image in `radius-lg` frame, soft `shadow-elevated`, sits on subtle radial gradient backdrop
- Text side: eyebrow → H2 → 2-line description → 3–4 bullet list with emerald checkmarks → primary CTA

### FAQ row
- Borderless top, 1px `nexor-line` between rows
- Question 17px weight 600 `nexor-ink`
- Plus/minus icon right-aligned, rotates on open
- Answer 16px `nexor-ink-2`, line-height 1.7, reveal via height transition (transform/opacity only — no `transition-all`)

## Motion

- Standard easing: `cubic-bezier(0.32, 0.72, 0, 1)` (spring-feel)
- Duration: 200ms for hovers, 320ms for layout reveals
- Page-load: stagger hero elements (eyebrow → headline → sub → CTAs) at 60ms intervals using `opacity` + `translateY(8px)` only
