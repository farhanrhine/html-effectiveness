---
name: 10-svg-illustrations
description: Geometric spot illustrations for headers and empty states with downloadable SVG assets
---

# SVG Illustrations — Reusable Asset Library

Ship geometric SVG illustrations that match the product palette and scale cleanly.

## Design Principles

- **Geometric, not realistic** — Use simple shapes (circles, rectangles, lines) with the product's color palette
- **Consistent stroke width** — Usually 1.5px or 2px (matching the design system's --border)
- **Limited color palette** — Primary (clay, olive, oat) + grays. Don't invent new colors.
- **Approx. 1:1 aspect ratio** — Square-ish illustrations work best for headers (can be landscape too)
- **SVG viewBox** — Standardize on `viewBox="0 0 320 240"` or similar. Makes scaling predictable.

## Asset Structure

```
figures/
  ├── background-jobs.svg
  ├── empty-tasks.svg
  ├── feature-launch.svg
  └── ... (one per concept)
```

Each SVG should have:
- Title/description comment at top
- Clear viewBox
- Semantic color names (use CSS tokens if inlining)
- Minimal prettification (no extra groups)

## Usage Patterns

- **Hero headers** — Full-bleed above fold, ~240px height, centered
- **Empty states** — Smaller (~120px), centered inline
- **Feature callouts** — Inline with text, ~80px, left-aligned
- **Download option** — Provide `.svg` and `.png` fallbacks; link both

## Gotchas

- **Strokes don't scale equally** — A 2px stroke at 100px looks thin; at 300px, it looks thick. Use `vector-effect="non-scaling-stroke"` if you want consistent stroke width at any size.
- **Colors in inline SVG** — Can't use CSS custom properties directly (`fill="var(--clay)"` won't work). Either inline the hex code or use filters/masks.
- **Accessibility** — Add `aria-label` and `role="img"` to SVG root if it's meaningful content. Use `aria-hidden="true"` if decorative.
- **Export from Figma** — Clean up the SVG (remove extra groups, defs). Tools like SVGO help.
- **Responsive sizing** — Use `max-width: 100%; height: auto;` on img or SVG tag. Avoid fixed pixel dimensions unless you want locked aspect ratio.

## File Size

- Keep SVGs under 10KB each (optimize with SVGO or similar)
- Base64 encode for <2KB assets (avoid extra HTTP requests)
- Larger graphics stay as external .svg files

## Full Library

See `resources/10-svg-illustrations.html` for a gallery of illustrated concepts with captions, color swatches, and downloadable SVG links.
