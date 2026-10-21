# Rooms on Autopilot — DESIGN.md

Client presentation for a room-rental platform in Athens. One HTML file, a 1600×900 stage scaled to fit any screen.

## Principles
- One idea per scene. A headline, then at most one supporting element.
- Type does the work. Large, tight headlines; quiet secondary text; no boxes around everything.
- Color is rare. Neutrals carry the page; blue marks the one thing to notice; orange only for a deadline, green only for "done".
- Motion explains, never decorates. Elements arrive in reading order, fast and soft, and never bounce.

## Tokens
| Token | Value | Use |
|---|---|---|
| `--bg` | `#F5F5F3` | light scenes |
| `--surface` | `#FFFFFF` | white scenes, cards on light |
| `--ink` | `#1D1D1F` | primary text |
| `--ink2` | `#6B6B70` | secondary text (4.9:1 on `--bg`) |
| `--ink3` | `#8E8E93` | labels, struck-through items |
| `--hair` | `#E3E3E0` | 1px separators |
| `--night` | `#0A0A0B` | dark scenes |
| `--n-ink` / `--n-ink2` | `#F5F5F7` / `#A1A1A6` | text on dark |
| `--accent` / `--accent-n` | `#0A66E8` / `#4D9BFF` | the one highlight, light / dark |
| `--warn` | `#C2410C` | deadlines only |
| `--ok` | `#15803D` | completed states only |

## Type
- Family: Geist (text and display), Geist Mono (labels, figures). Fallback: system sans.
- Scale on the stage: 176 / 128 display · 80 headline · 32 subhead · 26 body · 20 small · 17 mono label.
- Headlines: weight 600, letter-spacing −0.04em, line-height ≈1. Body: weight 400, −0.01em.
- Figures use tabular numbers.

## Layout
- Stage padding 96px top/bottom, 120px sides. Footer row 44px from the bottom.
- Lists are typographic: a 1px top rule, a title, one line of detail. Grids of 3 or 4 columns.
- Devices (laptop, phone) are the only rounded, shadowed objects.

## Motion
- Easing: `cubic-bezier(.16,1,.3,1)` for entrances, `cubic-bezier(.65,0,.35,1)` for scene crossfades.
- Enter: opacity 0→1, translateY 14px→0, blur 6px→0, 800ms. Stagger 60–150ms in reading order.
- Scene change: 450ms crossfade, no slides or zooms.
- Numbers count up once (1.2s, ease-out quartic) where the number is the point.
- Buttons press to scale .96 in 150ms.
- `prefers-reduced-motion`: everything appears at rest, no animation.

## Controls
Arrow keys, space, tap left or right of the stage, swipe, Play for an automatic run (each scene sets its own duration).
