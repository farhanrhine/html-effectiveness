---
name: 01-exploration-code-approaches
description: Choose between inline useEffect, custom hook, or external library for debounced search in React
---

# Debounced Search — Three Approaches

Choose the right pattern for your use case.

## Quick Summary

Three ways to implement debounced search in React:

1. **Inline useEffect** — Simple, no abstraction, duplicates easily
2. **Custom hook** — Reusable, owned by your team, recommended
3. **External library** — Feature-rich, adds dependency

## When to Use Each

**Inline (Approach 1):**
- Single component, never reused
- Team prefers explicit local logic

**Custom Hook (Approach 2) — RECOMMENDED**
- Multiple components share debouncing
- Want to eliminate duplication
- Dependencies are a concern
- Team can maintain simple ~10-line hook

**External Library (Approach 3):**
- Need advanced features (maxWait, flush, cancel)
- Team prefers battle-tested implementation
- Bundle size not a concern

## Key Decision Factor

Look at your codebase: How many places hand-roll debounce logic? If 2+, extract a hook. If you need only that hook's features, own it.

## Gotchas

- **Custom hook still re-renders on keystroke** — Optimizes API calls, not render count. Use useMemo/useCallback if renders themselves are expensive.
- **Async debounce in useCallback** — Make sure dependencies array is correct or you'll cancel in-flight requests unintentionally.
- **External library: controlled vs uncontrolled** — `use-debounce` uses defaultValue pattern; Acme prefers controlled inputs, so custom hook is better fit.

## Full Reference

See `resources/01-exploration-code-approaches.html` for complete comparison with code examples, tradeoff tables, and metrics for each approach.
