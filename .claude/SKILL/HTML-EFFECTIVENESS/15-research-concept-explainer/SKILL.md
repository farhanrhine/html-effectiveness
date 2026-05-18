---
name: 15-research-concept-explainer
description: Educational content with embedded interactive SVG demo, controls, and narrative explanation
---

# Concept Explainer — Interactive Visualization Demo

Teach abstract concepts (consistent hashing, load balancing, queuing) through live, interactive visualizations.

## Layout

- **Narrative + demo sections** — Text explains the concept, demo shows it live
- **Interactive SVG** — Clickable elements, animated transitions (300ms), real-time state updates
- **Controls panel** — Buttons/sliders to adjust visualization (add/remove nodes, change keys, etc.)
- **Sidebar** — Key definitions, terminology, learning objectives

## Demo Pattern

```
┌─ Text explanation ─────────────┐
│ "Consistent hashing maps keys  │
│  to a ring..."                 │
│                                │
│ ┌─ Interactive demo ─────────┐ │
│ │  SVG ring with nodes       │ │
│ │  Drag to add/remove nodes  │ │
│ │  Watch keys rebalance      │ │
│ └────────────────────────────┘ │
│                                │
│ ┌─ Controls ──────────────────┐ │
│ │ [Add Node] [Remove Node]   │ │
│ │ Show legend [✓]            │ │
│ └────────────────────────────┘ │
└────────────────────────────────┘
```

## SVG Interaction Pattern

- **Ring visualization** — `<circle class="ring track">` with `<arc class="arc">` segments
- **Nodes** — `<circle class="node">` at angles, clickable, animated cx/cy transitions
- **Labels** — Positioned absolutely over the ring, monospace font
- **Animations** — `transition: cx 300ms, cy 300ms; stroke-dasharray transitions` for smooth motion

## Controls Design

- **Buttons** — Monospace font, light bg on default, inverted on hover
- **Sliders** — Custom range input with clay thumb, shows current value
- **Checkboxes** — For toggling legend, advanced info, etc.
- **Live output** — Show current state in code block or table below

## Gotchas

- **SVG coordinate system** — (0,0) is top-left, not center. Use `transform="translate(cx, cy)"` or calculate properly.
- **Animation delays** — If adding multiple elements, stagger animations slightly (50ms apart) so they don't look like a glitch
- **State in JavaScript** — Model the visualization state outside the SVG (objects/arrays), then render SVG based on state. Don't store data in DOM attributes.
- **Touch support** — If adding drag/touch, use `pointerdown` events instead of `mousedown` for mobile
- **Performance** — For 100+ nodes, consider canvas instead of SVG (redraws faster)

## Learning Outcomes

Each explainer should have a clear learning objective:
- "Understand how consistent hashing maintains load balance"
- "See why token buckets are better than fixed limits"
- "Visualize the birthday paradox with collisions"

State it at the top, reinforce with the demo.

## Full Interactive Example

See `resources/15-research-concept-explainer.html` for consistent hashing demo with interactive ring, add/remove node controls, and animated key rebalancing.
