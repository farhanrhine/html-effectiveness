---
name: 09-slide-deck
description: Full-viewport slides with scroll-snap, dark invert mode, and presentation-friendly typography
---

# Slide Deck Format — Full-Screen Presentation

Build a presentation that's full-screen, scrollable, and keyboard-accessible.

## Layout

- **Viewport-fill slides** — Each slide is 100vh × 100vw, centered content with generous padding (6vw horizontal)
- **Scroll-snap** — `scroll-snap-type: y mandatory; scroll-snap-align: start; scroll-snap-stop: always` locks slides into view
- **Two color modes** — Default (ivory bg, slate text) + `.invert` (slate bg, ivory text)

## Typography Scale

- **Eyebrow** — 12px, mono, uppercase, +0.12em tracking
- **H1 (hero)** — `clamp(40px, 6vw, 64px)`, serif, 1.08 line-height, -0.01em letterspacing
- **H2 (section)** — `clamp(30px, 4vw, 42px)`, serif, 1.15 line-height
- **Subtitle/Body** — 17px max, line-height 1.6, color gray-700

## Slide Components

- **Title slide** — Ornament (SVG), H1, subtitle, byline (date + author in mono)
- **Shipped list** — Bullet points (olive dots), items grid (title + description + date)
- **Section break** — Invert mode, minimal text, breathing room
- **Call-to-action** — Bold H2, subtitle, maybe a button or link

## Gotchas

- **Font scaling with clamp()** — Responsive sizing between mobile and desktop. Test on small screens (320px) and large (1920px).
- **Scroll-snap can feel sticky** — Each slide locks in place; swipe quickly to skip. Natural behavior, don't fight it.
- **Invert mode includes all children** — Text, links, backgrounds all flip. Make sure contrast is legible in both modes.
- **Byline spacing matters** — Use flexbox with gap, not hardcoded margins. Aligns consistently across slides.
- **Images/videos in slides** — Full-bleed images should use `width: 100vw` with negative margins to break out of padding.

## Accessibility

- Use semantic HTML (header, h1/h2, nav)
- Keyboard navigation works by default (arrow keys to scroll)
- Test with screen readers; headings should make sense read aloud

## Full Presentation Example

See `resources/09-slide-deck.html` for a working multi-slide deck with title, shipped items list, and invert sections.
