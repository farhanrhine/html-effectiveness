---
name: index
description: Landing page showcasing a collection of work with grouped categories and navigation
---

# Portfolio Index — Curated Examples & Navigation

Create a portfolio landing page that showcases a collection of projects/examples with clear categories and quick navigation.

## Structure

- **Masthead** — Large heading with eyebrow, intro paragraph, optional hero figure
- **Filter/category buttons** — Quick jump between categories (Design, Engineering, etc.)
- **Project grid** — Responsive cards showing each project with:
  - Thumbnail or cover image
  - Title
  - Brief description
  - Tags (e.g., "Interaction", "Component", "Research")
  - Link to project
- **Footer** — Contact info, copyright, related links

## Masthead Design

- **Eyebrow** — Monospace, uppercase, with decorative line (clay colored)
- **H1** — Large serif, responsive font size (`clamp(38px, 5.4vw, 62px)`)
- **Emphasis** — Use `<em>` tags for italic color highlights (e.g., "unreasonable effectiveness")
- **Intro text** — 16.5px, 620px max-width, clear and inviting
- **Optional hero figure** — Grid with markdown (left) vs HTML (right) examples

## Project Cards

```
┌─────────────────────────┐
│                         │ ← Thumbnail or image
│                         │
│ Title                   │
│ Brief description (2-3) │
│ [Tag] [Tag] [Tag]       │
│ [Read more →]           │
└─────────────────────────┘
```

- **Responsive grid** — 3-column on large, 2 on medium, 1 on small
- **Card size** — Consistent aspect ratio (e.g., 16:10)
- **Hover state** — Subtle lift or shadow, text color brightens
- **Tags** — Small rounded pills, semantic colors (clay, olive, etc.)

## Navigation

- **Category buttons** — Inline at top or as sticky filter bar
- **Active state** — Clay border or bg color
- **URL state** — Categories reflected in URL (`?category=design`) so they're bookmarkable
- **Accessibility** — All cards must be keyboard-navigable; skip to main content link

## Gotchas

- **Thumbnail aspect ratios** — Use `object-fit: cover` so images don't stretch
- **Text over images** — If titles overlay images, ensure sufficient contrast. Use dark overlay or text shadow.
- **Hero grid layout** — Grid: left (text/markdown), right (image). On mobile, stacks vertically.
- **Font scaling** — Using `clamp()` for responsive sizing. Test at 320px (mobile) and 1920px (desktop).
- **Performance** — Lazy-load card images outside viewport. Use WebP with fallback to PNG.

## Category Patterns

- **Design** — Visual explorations, component libraries, animations
- **Engineering** — Code reviews, architecture docs, implementation guides
- **Research** — Feature explainers, interactive demos, case studies
- **Tools** — Calculators, optimizers, prompt tuners, configuration editors

## Full Example Portfolio

See `resources/index.html` for a complete portfolio index ("The unreasonable effectiveness of HTML") with projects, categories, responsive grid, and hero section.
