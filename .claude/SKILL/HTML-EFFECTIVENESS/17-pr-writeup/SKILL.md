---
name: 17-pr-writeup
description: PR description template with problem statement, approach, testing, and follow-ups
---

# PR Writeup — Detailed Change Summary

Write detailed PR descriptions that tell the story of why the change matters, not just what changed.

## Structure

- **Header** — PR title (e.g., "Move notification delivery onto a queue")
- **Metadata** — Filename/count of changes, stats (files, additions, deletions)
- **Prompt box** — The original problem/context from the issue or product discussion
- **Sections**
  - What this PR does
  - Why this approach (tradeoffs considered)
  - How to test
  - Follow-ups / known limitations
  - Related PRs

## Content Guidelines

- **"What" before "how"** — Explain the problem and solution first; code details second
- **Tradeoffs matter** — Why this approach over alternatives? (Performance vs maintainability, simplicity vs flexibility)
- **Testing instructions** — Steps to reproduce the change locally: "Run X, expect Y"
- **Rollout plan** — Is this safe to deploy immediately, or needs gradual rollout? Feature flag? Monitoring?
- **Follow-ups** — What's left for future PRs? Technical debt? Known issues?

## Visual Structure

- **H1** — PR title (36px serif)
- **Metadata strip** — Monospace, count of changed files, diff stats (olive for +, clay for -)
- **Prompt box** — Gray bg, problem context (same pattern as implementation plans)
- **H2 sections** — 22px serif for "What this does", "Testing", "Known issues"
- **Code blocks** — Monospace, dark bg, relevant snippets only (not the whole diff)
- **Callout panels** — Clay left border for "breaking change" or "needs monitoring"

## Gotchas

- **Don't repeat the GitHub diff** — Link to the diff; don't paste it all. Summarize key changes.
- **"Follow-up PRs" section** — Acknowledges technical debt honestly. Sets expectations for what's not included.
- **Testing instructions must be reproducible** — If it requires 5 manual steps, document them. If it needs a feature flag enabled, say so.
- **Backwards compatibility** — Call out if old clients break. API changes? Migration needed?
- **Monitoring/rollback** — What metrics should we watch? How do we roll back if it breaks?

## Audience

- **Author** — Tells the story for future maintainers
- **Reviewer** — Provides context so they don't have to read the entire diff
- **Changelog** — Becomes the official record of what shipped and why

## Full Example PR

See `resources/17-pr-writeup.html` for a complete PR writeup (notifications on queue) with problem statement, approach, testing plan, and follow-ups.
