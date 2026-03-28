# Project 1 — Static Webpage Design
**Horizon Studio** | Foundation of Visual Architecture & Integrity

---

## Overview

A pixel-perfect static webpage built with pure HTML and CSS — no frameworks, no JavaScript, no shortcuts. This project establishes the visual and structural foundation before any dynamic logic is introduced.

> *"Access to dynamic logic is locked until the visual architecture passes audit."*

---

## Tech Stack

- **HTML5** — Semantic markup only
- **CSS3** — External file, BEM methodology, CSS custom properties
- **Fonts** — Google Fonts (Bebas Neue, DM Sans, DM Mono)
- **Images** — WebP format via Unsplash CDN, explicit width/height on all assets

---

## Architecture Decisions

### Information Architecture
Sitemap defined before any code was written:

```
Home
├── Work        (Selected Projects)
├── Services    (What We Do)
├── About       (Studio Info)
└── Contact
```

Nav items: **4** (rule: < 5). Depth: **1 level** (rule: < 3).

### HTML — Semantic DOM
Every tag carries explicit meaning for browsers, search engines, and screen readers.

| Tag | Purpose |
|---|---|
| `<header>` | Site-wide banner / nav container |
| `<nav>` | Primary + footer navigation |
| `<main>` | Primary page content |
| `<section>` | Thematic content regions |
| `<figure>` / `<figcaption>` | Images with captions |
| `<address>` | Contact information |
| `<dl>` / `<dt>` / `<dd>` | Stats definition list |
| `<footer>` | Site-wide footer |

**One `<h1>` per page** — heading hierarchy never skipped (h1 → h2 → h3).

### CSS — Separation of Concerns
- Zero inline styles
- No IDs used for styling — classes only
- **BEM** (Block Element Modifier) naming: `.project-card__image`, `.service-item__body`, `.btn--primary`
- **DRY Principle** — all design tokens defined once as CSS custom properties in `:root`
- **Grid** for macro page layout, **Flexbox** for micro component alignment

### Assets — Stability Matrix
All `<img>` tags carry explicit `width` and `height` attributes to prevent Cumulative Layout Shift (CLS). Browser reserves space before the image data arrives.

---

## Quality Gate Checklist

| Audit | Status |
|---|---|
| W3C HTML Validation | ✅ Zero errors |
| Semantic landmarks (`<nav>`, `<main>`, `<footer>`) | ✅ Present |
| One `<h1>` per page | ✅ |
| No inline styles | ✅ |
| No IDs for styling | ✅ |
| BEM class naming | ✅ |
| Explicit image dimensions (CLS prevention) | ✅ |
| WebP image format | ✅ |
| Keyboard focus styles (`:focus-visible`) | ✅ |
| ARIA labels & roles | ✅ |
| Nav < 5 items, depth < 3 | ✅ |
| No catch-all nav buckets | ✅ |

---

## Accessibility (A11Y)

Non-negotiable. The web must be perceivable by all users and assistive technologies.

- `role="banner"`, `role="contentinfo"`, `role="list"` on appropriate elements
- `aria-label` on navigation landmarks and ambiguous links
- `aria-hidden="true"` on decorative/redundant elements (ticker, badge text)
- `:focus-visible` outline styles for keyboard navigation
- Descriptive `alt` text on every image
- `<address>` wrapping contact information

---

## Design System

CSS custom properties defined in `:root` — change once, updates everywhere.

```css
--clr-accent:    #c8f23a;   /* Primary accent — lime green */
--clr-bg:        #0a0a0a;   /* Page background */
--clr-text:      #f0ede6;   /* Primary text */
--ff-display:    'Bebas Neue', sans-serif;
--ff-body:       'DM Sans', sans-serif;
--ff-mono:       'DM Mono', monospace;
```

---
