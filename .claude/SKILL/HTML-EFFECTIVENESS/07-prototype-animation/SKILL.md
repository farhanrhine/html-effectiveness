---
name: 07-prototype-animation
description: CSS-only animation for task completion with easing curves, timing, confetti, and playback controls
---

# Prototype Animation — Task Completion Micro-Interaction

A single click should feel rewarding. Circle fills, check draws, label strikes, confetti bursts, then the row steps back.

## The Animation Sequence (900ms total)

| Step | Timing | What Happens | Duration |
|------|--------|--------------|----------|
| 0ms | — | Click → .done class applied | — |
| 80ms (delay) | — | Check circle starts filling | — |
| 180ms | start + 180ms | Check circle filled, check path visible | 180ms |
| 120ms (delay) | start + 120ms | Strikethrough and label color fade | 200ms |
| 200ms (delay) | start + 200ms | Confetti particles launch | 520ms |
| 600ms (delay) | start + 600ms | Row collapses, fades to 60% opacity | 280ms |

## Easing Curves That Matter

- **Linear** — Mechanical, feels cheap (use only for loading spinners)
- **Ease-out** `cubic-bezier(.16, 1, .3, 1)` — Settles quickly, natural deceleration
- **Spring** `cubic-bezier(.34, 1.56, .64, 1)` — Bouncy overshoot, playful. Overshoot (1.56) must be ≤ 1.8 or feels brittle

## Key Gotchas

- **Spring overshoots can look broken if too high** — 1.56 is the sweet spot for this interaction. Anything over 1.8 feels like a physics bug, under 1.2 feels sluggish.
- **Confetti timing needs gaps** — Start confetti at 200ms (after check settles). Start too early and it collides with the check animation; too late and the payoff feels disconnected.
- **Stroke-dasharray for drawing animation** — Check path uses `stroke-dasharray: 20; stroke-dashoffset: 20` at rest, animates to `stroke-dashoffset: 0` on done. Don't hardcode dash values; measure your SVG path length.
- **Reset state requires class removal** — Using JavaScript `.classList.toggle('done')` so users can click again to reset. CSS-only doesn't support true "reverse" on repeated plays.
- **Delay stacking via `transition-delay`** — Each property has its own delay chain. Check fill (180ms base), label (120ms base), confetti (200ms base). Overlapping creates "cascade" feel.
- **Confetti particles need CSS variables** — Each `.confetti.c1-6` has `--dx`, `--dy`, `--rot` to vary trajectory. Calculate positions in a circle around the check, not random.

## Tuning Checklist

- **Does the check feel snappy?** (should be ~180ms, not 300+)
- **Does strikethrough sync with color fade?** (same timing, slightly delayed from check)
- **Is confetti launching from the right spot?** (measure SVG viewBox, position particles at check center)
- **Can I replay without lag?** (test rapid clicks; transitions should queue smoothly)
- **Does spring curve match product brand?** (playful? use 1.56; serious? use ease-out instead)

## Full Interactive Sandbox

See `resources/07-prototype-animation.html` for live easing curve swapper, timeline visualization, and replayable animation. Test different cubic-bezier curves in real-time.
