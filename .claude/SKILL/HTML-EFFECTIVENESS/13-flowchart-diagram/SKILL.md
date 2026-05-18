---
name: 13-flowchart-diagram
description: SVG flowchart with clickable nodes, interactive side panel, and keyboard navigation
---

# Flowchart Diagram — Annotated System Flow

Document complex processes visually with SVG flowcharts that are interactive and keyboard-accessible.

## Structure

- **Left side** — Large SVG flowchart with nodes, decision diamonds, edges
- **Right sidebar** — Node details, linked to selected node
- **Responsive** — 2-column grid on desktop, stacks on mobile

## Node Types

- **Process** — Rectangle (white bg, gray border)
- **Terminal** — Rounded rectangle (gray-150 bg)
- **Decision** — Diamond shape (decision path branches yes/no)
- **Success path** — Rectangle (olive outline, light olive bg)
- **Error path** — Rectangle (rust outline, light rust bg)

## Visual Language

- **Solid edges** — Normal flow (slate color)
- **Yes edges** — Olive color, solid
- **No/error edges** — Rust color, dashed
- **Active node** — Clay border (2px), highlights details in sidebar
- **Hover state** — Slight lift (transform: translateY(-1px))

## Interaction

- **Click node** — Highlights it, loads details in sidebar
- **Keyboard** — Tab through nodes, Enter to activate
- **Responsive** — Sidebar becomes static on mobile (not sticky)

## Gotchas

- **SVG viewBox scaling** — Use a fixed aspect ratio viewBox (e.g., 0 0 800 600) so the chart scales proportionally
- **Arrow markers** — Use SVG `<marker>` elements with `marker-end="url(#arrow)"` for arrowheads. Create variants for different stroke colors (clay, olive, rust).
- **Text labels in SVG** — Use `<text>` with monospace font, 12px, and `pointer-events: none` so they don't interfere with clicks
- **Side panel doesn't scroll independently** — It's sticky top but shares scroll with main. If needed, add `overflow-y: auto; max-height: 60vh;` to the sidebar
- **Node active state via JavaScript** — Add `.active` class on click; SVG sees it via CSS (`.node.active rect { stroke: var(--clay); }`)

## Common Patterns

- **Decision branching** — Both yes/no edges should exit at 45° angles for clarity
- **Horizontal vs vertical** — Keep flows either left-to-right or top-to-bottom, not diagonal
- **Spacing** — 100-160px between nodes so labels don't overlap edges

## Full Example

See `resources/13-flowchart-diagram.html` for a complete deploy pipeline diagram with clickable nodes, decision paths, and animated highlights.
