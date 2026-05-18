---
name: 14-research-feature-explainer
description: Multi-section explainer with sticky sidebar nav, TLDR callout, and file references
---

# Feature Explainer — Educational Content with Navigation

Teach a complex feature (rate limiting, auth, caching) through narrative + visuals + code pointers.

## Layout

- **Left sidebar** — Sticky TOC (table of contents) with section links, file references at bottom
- **Main content** — Narrative sections with code examples, embedded SVG diagrams, callouts
- **Typography** — Large headings, comfortable line-height (1.65), max-width 680px for prose

## Components

- **TLDR callout** — Left clay border, white background, key takeaway summarized (~2 sentences)
- **File reference list** — Monospace paths at bottom of sidebar, shows where to find code
- **Subsections** — H2 headings with sticky navigation (sidebar updates as you scroll)
- **Code blocks** — Monospace font, dark bg, with optional syntax highlighting
- **Emphasis** — Use `<span class="term">` with dotted clay underline for first mention of new concepts

## Gotchas

- **Sidebar sticky positioning** — On desktop, sidebar is `position: sticky; top: 32px`. On mobile (<920px), set to `display: none` or let it scroll normally
- **TOC links with scroll-margin-top** — Each section should have `scroll-margin-top: 24px` so it appears below the fixed header (if any)
- **File paths without backslashes** — Use forward slashes even on Windows; convention for code.
- **Color contrast in subsections** — gray-500 text on ivory can feel low-contrast. Use gray-700 for body text, gray-500 only for secondary labels
- **Navigation updates on scroll** — JS should update `.active` class on TOC links as you scroll. Avoid jarring updates; highlight current section only.

## Writing Guidelines

- Start with the **problem** — Why does this feature exist?
- Explain the **mechanism** — How does it work? Use simple terms for complex concepts.
- Show the **practice** — Code snippets, configuration, common patterns.
- End with **implications** — What happens if you misconfigure it? Edge cases?

## Full Example

See `resources/14-research-feature-explainer.html` for rate limiting explainer with sticky sidebar TOC, TLDR, code references, and narrative sections.
