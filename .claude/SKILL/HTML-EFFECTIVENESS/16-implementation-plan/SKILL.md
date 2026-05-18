---
name: 16-implementation-plan
description: Structured design doc with problem statement, approach, acceptance criteria, and phased rollout
---

# Implementation Plan — Feature Design & Scope Document

Document how to build a feature: the problem, approach, acceptance criteria, and phased rollout.

## Sections

1. **Header** — Feature name, eyebrow (e.g., "Product Design")
2. **Problem statement** — Prompt box explaining what users struggle with
3. **Proposed solution** — Narrative overview of the approach
4. **Phase 1, 2, N** — Numbered sections with:
   - Scope (what ships in this phase)
   - Acceptance criteria (testable conditions)
   - Dependencies (blocked by X?)
   - Effort estimate (T-shirt sizing)
5. **Risks** — Known unknowns, integration points, measurement
6. **Timeline** — Gantt or text-based phases with dates

## Layout

- **Numbered badges** — `.sec-head .num` for phase indicators (oat bg, slate text)
- **Prompt box** — Gray bg, light border, problem statement at top
- **Acceptance criteria** — Bullet list with checkboxes (or ✓ ✗ symbols)
- **Decision callouts** — Clay left border, highlight important tradeoffs
- **Metrics** — How will we know it worked? Response times? Adoption?

## Typography

- **H1** — 38px serif, problem centered
- **H2 (sections)** — 26px serif with numbered badge
- **H3 (subsections)** — 18px serif, no badge
- **Eyebrow** — Mono, 12px, uppercase

## Gotchas

- **Scope creep** — Be explicit about what's NOT in each phase. Sections labeled "Future" are clearer than silent omissions.
- **Acceptance criteria need owners** — Who tests each criterion? QA? Product? Be specific.
- **Dates are soft** — Use ranges ("late Q2") or avoid dates if uncertain. Avoid committing to specific ship dates upfront.
- **Integration dependencies** — If phase 2 depends on phase 1 being live AND on a backend change, say so explicitly. Don't hide it in prose.
- **Measurement plan** — Define how you'll measure success before shipping. A/B test? Metrics dashboard? User feedback?

## Common Patterns

- **Three-phase rollout** — MVP (minimal), scale (performance), polish (UX refinement)
- **Backwards compatibility** — Call out if older clients break
- **Data migrations** — Plan for how existing data transforms
- **Rollback plan** — What do you do if this goes wrong?

## Full Example Plan

See `resources/16-implementation-plan.html` for a complete feature plan (comment threads on task cards) with phases, acceptance criteria, timelines, and risk callouts.
