---
name: 03-code-review-pr
description: Template for code reviews that highlight which files need attention using a risk color-coding system
---

# PR Code Review — Risk-Mapped Format

Structure code reviews so reviewers can focus effort on the riskiest changes first.

## The Three-Part Structure

1. **Summary** — What this PR does (short bullets, ~3 lines)
2. **Risk Map** — Files colored by concern level (safe/medium/attention)
3. **Detailed Files** — Expanded diffs + comments for medium/attention files only

## Risk Color Codes

- **Green (Safe)** — Type-only, additive features, no behavior change → collapsible
- **Orange (Medium)** — Behavior changes in non-critical paths → show diff, brief comment
- **Red (Attention)** — Core logic, state management, error handling → expanded, detailed comments

## Key Gotchas

- **Idempotency keys must be stable** — Don't generate in parameter defaults; mint once in onMutate and thread through the call stack. Random key per retry defeats deduplication.
- **Optimistic updates need cancelQueries()** — Call `qc.cancelQueries(key)` before `onMutate` or in-flight refetches will clobber your optimistic state → UI flicker.
- **Unused isPending vars are red flags** — If destructured but never passed to UI, either drop it or find why the pending state isn't being communicated.
- **Rollback needs user feedback** — Silent rollback on error confuses users. Wire toast/notification in onError handler.
- **Light load details = wasted review time** — If a file is safe, say so and collapse it; don't make reviewer scroll through 30 lines of harmless code.

## Review Cadence

1. Reviewer scans **Risk Map** first (~5 sec) — immediately know which files need depth
2. Expand "Needs Attention" files, read comments
3. Spot-check "Medium" files if risk summary raises questions
4. Assume "Safe" files are fine unless something smells off

## When to Use

- **Any PR with optimistic/cache updates** → Must show risk map to catch timing bugs
- **Multi-file refactors** → Risk colors prevent "review everything equally" trap
- **API changes** → Mark changed signatures as "attention" so callers are checked
- **State management** → High risk, always needs expanded comments and edge-case discussion

## Full Reference

See `resources/03-code-review-pr.html` for complete example with live PR, diff blocks, and comment threads.
