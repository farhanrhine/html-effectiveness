---
name: 08-prototype-interaction
description: Drag handles and drop indicators for reordering list items with smooth transitions
---

# Prototype Interaction — Sidebar Drag-to-Reorder

Let users drag sidebar items to reorder, with visual feedback for grab/dragging/drop states.

## User Flow

1. **Hover item** → Background tints, grip dots brighten (visual affordance)
2. **Grab (mousedown on grip)** → `cursor: grabbing`, item slightly rotates (2deg), opacity → 35%
3. **Drag** → Drop indicator line appears above/below target
4. **Drop (mouseup)** → Item fades back in, list reorders, animation settles

## Key Elements

- **Grip handle** — 2×3 dot grid (6 circles), pure CSS. Hover state increases dot visibility.
- **Item hover state** — Subtle background tint (--gray-50), easier to see drop target
- **Dragging state** — Opacity 35%, rotate 2deg, cursor: grabbing
- **Drop indicator** — Thin horizontal line showing where item will land
- **Counts** — Right-aligned badge (e.g., "12") that stays fixed during drag

## Gotchas

- **Grip is not the whole item** — Only the left 10px×16px area is the drag handle. Full-item drag is too aggressive.
- **Drop indicator needs z-index** — Position: absolute, appears above/below items. Can be obscured if siblings have background color.
- **Rotation (2deg) is intentional** — Signals "lifted". Remove it and drag feels heavy/stuck. Keep it small (<3deg).
- **Counts don't move during drag** — Use `margin-left: auto` with `flex-shrink: 0` so they stay right-aligned as item fades.
- **Background color during drag** — Item bg stays --gray-50 while dragging, not white. Helps it "float" visually.
- **Snap-back animation** — After drop, item should smoothly return opacity/rotation to normal (~120ms ease-out).

## Implementation Notes

- Use HTML5 Drag and Drop API or a library (react-dnd, dnd-kit) if building real
- The indicator line position updates on `dragover` events
- Drop reorders the DOM; transitions handle the visual settling
- Sidebar width should be fixed (not responsive) for grab zones to stay predictable

## Full Interactive Prototype

See `resources/08-prototype-interaction.html` for working demo with real drag-and-drop, live list reordering, and smooth settling animation.
