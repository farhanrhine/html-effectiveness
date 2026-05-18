---
name: 11-status-report
description: Format for communicating team progress with stat cards, highlights, blockers, and next steps
---

# Status Report Template — Weekly Engineering Update

Structure weekly updates with stat cards, narratives, and actionable next steps.

## Sections

1. **Header** — Title, week range, auto-generated pill (e.g., "auto-generated")
2. **Summary Band** — 4 stat cards (e.g., PRs merged, bugs fixed, uptime, cycle velocity)
3. **Highlights** — Key wins, shipped features, milestones hit (2-4 bullet points)
4. **Blockers** — Issues slowing us down, owner, status (e.g., "Blocked on Design Review")
5. **Next Week** — What we're focused on, risks to watch
6. **Notes** — Off-calendar items, team updates, hiring notes

## Stat Card Variants

- **Standard** — Number (big serif), label (small caps), optional delta (green up, gray flat)
- **Warning** — Left border (clay), highlights at-risk metrics
- **Meta** — Smaller numbers, more context

Example: `42` (big) + "PRs Merged" (label) + `+6 from last week` (delta, green)

## Typography

- **Title** — 38px serif, -0.01em letterspacing
- **Section heads** — 24px serif, with horizontal rule below
- **Labels** — Small caps, 12px, --gray-500
- **Numbers** — 44px serif, 500 weight, tight line-height (1)

## Gotchas

- **Stat cards need breathing room** — Don't crowd them. Use 14px gap between cards; 22px below entire band.
- **Blocker cards need visual distinction** — Clay left border (4px) + warning background. Don't just use text.
- **Deltas can mislead** — `+6 PRs` is good, but `+6 bugs` is bad. Make direction clear with color (green up / red down).
- **Next week section is actionable** — Not a narrative recap. Short bullet points of what's in progress.
- **Auto-generated timestamp** — Include "auto-generated on 2025-04-14" so readers know freshness. Update weekly.

## Accessibility

- Use semantic HTML (h1, h2, hr, ul, li)
- Color + text for status pills (not color alone)
- Sufficient contrast on all backgrounds

## Full Example Report

See `resources/11-status-report.html` for a complete weekly status with stat cards, highlights section, blockers, and next week callout.
