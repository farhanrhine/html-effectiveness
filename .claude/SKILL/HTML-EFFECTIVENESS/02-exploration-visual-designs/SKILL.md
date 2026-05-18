---
name: 02-exploration-visual-designs
description: Choose between minimal, illustrated, playful, or instructional empty states based on user context
---

# Empty-State Visual Directions — Four Patterns

Pick the right tone for your empty state based on user maturity.

## The Four Directions

| Direction | Use When | Tone |
|-----------|----------|------|
| **A: Minimal** | User knows the product | Calm, confident, just text + quiet button |
| **B: Illustrated** | Need to explain object model | Educational, a small spot illustration |
| **C: Playful** | Want personality, user is patient | Animated card stack, gently bobbing |
| **D: Instructional** | User is brand new (onboarding) | Action-dense, numbered steps, high guidance |

## Key Decision Factor

**Is this for a new user or an established user in an empty view?**

- **New user** → Instructional (D) — Treat empty as onboarding tour
- **Established user** → Minimal (A) or Illustrated (B) — Assume they know what to do
- **Want personality** → Playful (C) — But only if loop time feels natural (~3 sec)

## Gotchas

- **Instructional ≠ just empty state** — Use D when *onboarding* a new user to product/feature, not just "list has no items yet"
- **Playful animation timing matters** — Bobbing stack works at 3.2s loop; faster feels twitchy, slower feels stuck
- **Illustrated tone carries weight** — The copy ("Start your first list") should match the graphic's help level; mismatch feels jarring
- **Light/dark adaptability** — All four work on both surfaces; test token flips (--panel, --line colors)

## Example Combinations

- Empty sprint board + established user → Minimal
- First time in "Lists" feature → Illustrated (explain the concept)
- New user's first login → Instructional (high guidance)
- "No messages" state + product veterans → Playful (personality, low stakes)

## Full Reference

See `resources/02-exploration-visual-designs.html` for live variants, light/dark toggle, and detailed rationales.
