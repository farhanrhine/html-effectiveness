---
name: 05-design-system
description: Color, typography, spacing, radius, shadows, and core components for the Acme product
---

# Design System — Token Reference

Use this as the canonical source for design tokens. Copy tokens directly into new components; don't invent new values.

## Token Layers

### Colors (CSS custom properties)
- **Primary** — clay (#D97757), slate (#141413), ivory (#FAF9F5), oat (#E3DACC)
- **Neutral** — white, gray-100, gray-300, gray-500, gray-700
- **Semantic** — success, warning, danger, info (use in alerts, status, badges)

### Typography
- **Display** — 48px, serif, 1.1 line-height (hero text only)
- **H1/H2** — 32/24px, serif, 500 weight
- **Body** — 16px, sans, 430 weight, 1.55 line-height
- **Small** — 14px, sans, 430 weight
- **Caption** — 12px, sans, 500 weight, all-caps (timestamps, labels)

### Spacing Scale
4 → 8 → 12 → 16 → 24 → 32 → 48 → 64 (all in px). Use only these values; don't add `20px` or `40px`.

### Shape Tokens
- **Radius** — 4px (xs), 8px (sm), 12px (md, default panel), 20px (lg, pills)
- **Shadows** — sm (0 1px 2px/6%), md (0 4px 10px/8%), lg (0 12px 28px/12%)

## Core Components

- **Button** — primary/secondary/ghost/danger variants, 36px height
- **Input** — 38px height, bordered, 260px default width, focus ring (clay border + shadow)
- **Checkbox** — custom appearance, clay bg when checked, white checkmark
- **Badge** — 22px height, neutral/accent/success/warning variants, pill-shaped

## Gotchas

- **Font weight 430 is not 400** — Regular sans is 430 in this system (subtly lighter). Don't replace with 400 or text will feel heavy.
- **Spacing is strict** — Only use 4, 8, 12, 16, 24, 32, 48, 64. If 24px doesn't fit, use 20px from the 16+4 slot, don't add arbitrary spacing.
- **Button focus state includes 3px shadow** — `.btn:focus { box-shadow: 0 0 0 3px rgba(217, 119, 87, 0.15); }`. If you skip it, keyboard nav will be invisible.
- **Gray-300 is the border color** — Use `--gray-300` for 1.5px borders on all panels; it's the canonical choice.
- **Semantic colors are muted** — Warning (#C78E3F) and danger (#B04A3F) are desaturated intentionally. Don't brighten them or they'll clash with the warm palette.
- **Radius consistency** — Panels = 12px, form inputs/buttons = 8px, pills (badges) = 999px. Mixed radii on related elements looks unfinished.

## When to Add New Tokens

**Don't** add a new spacing, color, or radius without asking the design team. The system is intentionally constrained.

**Do** add new semantic colors if the component truly represents a new state (e.g., "locked", "archived") that isn't covered by success/warning/danger/info.

## Full Reference

See `resources/05-design-system.html` for live swatches, typography scale, component previews, and token values.
