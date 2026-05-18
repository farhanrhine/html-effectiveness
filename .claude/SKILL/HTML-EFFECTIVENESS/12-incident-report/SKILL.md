---
name: 12-incident-report
description: Format for documenting incidents with TL;DR, timeline, root cause, and action items
---

# Incident Report Template — Structured RCA Format

Document incidents in a structured, scannable way that supports post-mortems and knowledge capture.

## Header Section

- **Incident ID** — `INC-YYYY-MMDD` (e.g., INC-2025-0412)
- **Title** — Clear, specific summary (e.g., "Elevated 502s on task sync")
- **Severity pill** — Color-coded (red for critical, orange for high, yellow for medium) + duration
- **Status pill** — Resolved (green), investigating (yellow), or open (gray)
- **Duration** — Start time, end time, total impact (e.g., "2h 14m")

## TL;DR Section

- **Background panel** — Dark (--slate) with ivory text
- **Problem statement** — What broke, impact scope (e.g., "500 affected users, task sync failed")
- **Root cause** — One-sentence explanation (e.g., "Query timeout in sessions table under concurrent load")
- **Fix** — What we did (e.g., "Added index on user_id, reverted query optimization")

## Timeline Section

- **Chronological events** — Detection time, escalation, mitigation, resolution
- **Each entry** — Timestamp, action, owner
- **Spacing** — Breathing room between entries, easy to scan

## Root Cause Section

- **Narrative** — Detailed explanation of what went wrong and why
- **Contributing factors** — List of things that made it worse (e.g., "No monitoring on this endpoint", "Index was missing")
- **Detection delay** — Why it took 8 minutes to notice
- **Propagation** — How users were affected

## Action Items

- **Preventive** — Fix the bug (code change, deploy timeline)
- **Detective** — Add monitoring/alerting (so next time we catch it faster)
- **Reactive** — Communication, rollout coordination, documentation

## Gotchas

- **Severity pills need consistency** — Use exact same color/text across all reports. `sev-critical`, `sev-high`, etc.
- **Timestamps are UTC** — Specify timezone once in header; all times should be comparable.
- **Root cause != blame** — Focus on systems and processes, not "Engineer X made a mistake". Blameless culture.
- **Action items need owners and deadlines** — `[ ] Add session query index (Alice, due Tue)`. Don't leave items hanging.
- **Post-mortem appendix** — Include error logs, metrics graphs, deployment history as appendix. Readers want evidence.

## Accessibility

- Semantic HTML (h1, h2, h3, ul, li)
- Color + icon for severity (not color alone)
- Code blocks use monospace font, sufficient contrast

## Full Example Report

See `resources/12-incident-report.html` for a complete incident post-mortem with TL;DR, timeline, root cause analysis, and action items.
