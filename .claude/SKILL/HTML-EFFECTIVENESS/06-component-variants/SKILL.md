---
name: 06-component-variants
description: Six structural treatments of the Card component for different content densities and emphasis levels
---

# Component Variants — Card Matrix

Choose the right Card treatment based on context: density, interactivity, and prominence.

## Six Variants at a Glance

| Variant | Border | Shadow | Use When |
|---------|--------|--------|----------|
| **A. Flat** | none | none | Dense lists on tinted backgrounds, low emphasis |
| **B. Outlined** | 1.5px gray-300 | none | Default content cards on white/ivory |
| **C. Elevated** | none | shadow-md | Draggable items, popovers, floating panels |
| **D. Accent Stripe** | 1.5px + clay bar | none | Pinned, priority, or selected items |
| **E. Inset** | none | none | Cards embedded in tinted panels (oat fill) |
| **F. Horizontal** | 1.5px | none | Compact row layout, action on right |

## Customizable Dimensions

- **Padding** — 12px to 32px (tune density without changing layout)
- **Border** — none, hairline, or solid (works with all variants)
- **Shadow** — Toggle shadow-md on/off for elevation effect
- **Avatar** — Consistent 36px, positioned top-left of header

## Key Gotchas

- **Flat is not invisible** — Still clickable with 2px clay outline on hover. Use when you want low emphasis but not a spacer.
- **Inset changes text colors** — The oat background affects chip styling and button borders. Test all nested components.
- **Elevated works best with white bg** — Shadow falls flat on colored surfaces. Only use C when the card parent is white/transparent.
- **Stripe is for status, not branding** — The clay bar signals "this item needs attention", not just "it's pretty". Don't use for all cards in a grid.
- **Horizontal layout hides subtitle** — Card.sub is display:none in variant F. Plan your content for single-line titles only.
- **Padding scales readability** — Smaller padding (12-16px) for dense lists, larger (24-32px) for hero/featured cards.

## When to Combine

- **Outlined + Flat** — Use B for primary cards, A for secondary (e.g., in a two-column layout)
- **Outlined + Inset** — Use B on ivory bg, switch to E when placing cards inside an oat panel
- **Elevated + Horizontal** — Combo for draggable items with right-aligned actions
- **Stripe for one per view** — Pick the most important card as the pinned item; others should use B or C

## Full Explorer

See `resources/06-component-variants.html` for live interactive controls, sandbox to adjust padding/border/shadow, and real-time HTML snippets.
