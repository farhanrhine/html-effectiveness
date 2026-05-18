---
name: 18-editor-triage-board
description: High-volume issue triage interface with sticky toolbar, filters, and status indicators
---

# Triage Board — Issue Filtering & Workflow UI

Design interfaces for managing large backlogs (issues, PRs, bugs) with quick filtering and bulk actions.

## Layout

- **Sticky toolbar** — Position fixed or sticky, filters + summary stats
- **Filter chips** — Active filters show (e.g., "label: bug", "priority: high")
- **Issue rows** — Title, metadata (assignee, labels, time), action buttons
- **Status indicators** — Color-coded severity/priority
- **Bulk actions** — Select multiple, apply label/assign/close in batch

## Toolbar Components

- **Summary** — Monospace text: "12 issues · 3 selected · filter: bug" (bold key numbers)
- **Filter button** — Opens/closes filter panel
- **Active filter chips** — Show current filters, clickable to remove
- **Spacer** — Flex grow to push actions right
- **Quick action buttons** — Close all, archive, reassign, etc.

## Row Structure

```
[ ☐ ] | Title | Label badges | Assignee | Priority icon | Age
```

- **Checkbox** — Select for bulk actions (styled custom, not browser default)
- **Title** — Link to issue/PR detail
- **Labels** — Small rounded pills, color-coded by type
- **Assignee** — Avatar (36px) or unassigned indicator
- **Priority** — Color dot (red/orange/yellow) or status badge
- **Age** — Monospace, e.g., "2d" or "opened 3 months ago"

## Filtering

- **Faceted search** — Checkboxes for severity/priority/label (not search box)
- **Filter is persistent** — Stored in URL (`?filter=bug&priority=high`), survives refresh
- **Active filter count** — Show "3 active filters" so users know filters are applied
- **Clear all button** — One click to reset

## Gotchas

- **Sticky toolbar can hide content** — When toolbar is visible, issue rows scroll underneath. Add `padding-top` to content below toolbar.
- **Bulk selection state** — Three states: all selected, some selected, none selected. Show "select all" / "deselect all" buttons accordingly.
- **Status badges are semantic** — Use color + icon, not color alone. Red + X for closed, green + ✓ for resolved, orange + ⏳ for in progress.
- **Row height consistency** — Fixed height (54-64px) so list feels snappy; one-liner titles only.
- **Search + filter combined** — If supporting both, search is fast/fuzzy, filters narrow scope. Search titles only, not bodies.

## Performance Notes

- **Lazy-load rows** — If 1000+ issues, virtualize rows (show only visible ~20)
- **Debounce filter changes** — Reduce API calls when user adjusts filters
- **Keyboard nav** — Arrow keys to move between rows, Enter to open, ⌘+click to multi-select

## Full Example Board

See `resources/18-editor-triage-board.html` for a complete triage board (Cycle 14) with filters, sticky toolbar, bulk selection, and status indicators.
