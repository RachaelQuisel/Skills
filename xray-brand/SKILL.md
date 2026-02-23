---
name: xray-brand
description: Apply XRAY's official 2026 brand identity — colors, typography, logo, and component styles — to any document, presentation, web artifact, or design output. Use this skill any time someone asks to create or style something for XRAY, apply XRAY's brand, generate XRAY-branded materials, or produce documents that should follow XRAY's visual identity. Triggers include: "XRAY branded", "make it look like XRAY", "apply our brand", "XRAY style", "brand this document", "XRAY presentation", or any request to produce a deliverable for the company XRAY (Workflow Automation Consultancy). This skill should always be used when producing XRAY-branded outputs, even if the user doesn't explicitly say "brand guidelines."
---

# XRAY Brand Skill

## Overview

XRAY is a **Workflow Automation Consultancy** with the tagline _"Workflow Automation That Actually Works."_

**Brand personality:** Professional, clear, modern, warm, approachable. Minimal and purposeful decoration — hand-drawn line art, geometric patterns (dots, arcs, circles), subtle background illustrations. Simplicity over complexity.

---

## 1. Color System

> **Never** use pure black (`#000`) for text or backgrounds.  
> **Page background** is always `floralwhite` — never pure white.

### Core Palette

| Role | Name | Hex |
|------|------|-----|
| Headings, dark backgrounds | Gray 900 | `#0e1c2d` |
| Footer borders, secondary dark | Gray 800 | `#2c3845` |
| Body text (default) | Gray 600 | `#686f76` |
| Muted/tertiary text | Gray 500 | `#868b8e` |
| Footer text on dark, disabled | Gray 300 | `#c3c2bf` |
| Borders, dividers, card bg | Gray 200 | `#e1ded8` |
| Subtle tinted bg | Gray 100 | `#0e1c2d0d` |
| Page/navbar background | Off-White 100 | `floralwhite` |
| FAQ/pricetag backgrounds | Off-White 200 | `#feefcf` |
| Card surfaces, button text | White | `#ffffff` |

### Brand Blues (Primary Action Color)

| Role | Name | Hex |
|------|------|-----|
| **Primary CTA, links, accents** | Blue 500 | `#1566b9` |
| Button hover, active link | Blue 700 | `#0f4185` |
| Deepest blue (rare) | Blue 900 | `#192f4f` |
| Ghost button hover border | Blue 300 | `#8cb8e0` |
| Ghost button default border | Blue 200 | `#b9d6f0` |
| Ghost button hover bg | Blue 100 | `#e6f1fb` |

### Accent Colors

| Role | Name | Hex |
|------|------|-----|
| Alert, decorative circle | Red 500 | `#f55647` |
| Highlight accent, special cards | Yellow 500 | `#f5cf45` |
| Modal backdrop | Overlay | `#0e1c2dcc` |

### Color Rules Summary
- **Light mode:** Gray 900 text on Off-White 100 background
- **Dark mode/sections:** Gray 300 text on Gray 900 background
- **Links:** Blue 500, hover Blue 700
- **CTAs:** Always Blue 500 background, white text

---

## 2. Typography

### Font Families

| Role | Primary Font | Google Fonts Fallback |
|------|-------------|----------------------|
| Headlines & Buttons | `new-order` (Adobe Fonts) | `Urbanist` |
| Body & UI text | `mundial` (Adobe Fonts) | `Figtree` |

```html
<!-- Google Fonts fallback (use when Adobe Fonts unavailable) -->
<link href="https://fonts.googleapis.com/css2?family=Urbanist:wght@400;600;700&family=Figtree:wght@400;600;700&display=swap" rel="stylesheet">
```

### Type Scale

| Level | Size | Weight | Line Height | Letter Spacing | Font |
|-------|------|--------|-------------|----------------|------|
| Display 1 | 96px | 700 | 115% | -2.5px | new-order / Urbanist |
| Display 2 | 72px | 700 | 80px | -2.5px | new-order / Urbanist |
| H1 | 56px | 700 | 64px | -1px | new-order / Urbanist |
| H2 | 40px | 700 | 48px | -1px | new-order / Urbanist |
| H3 | 32px | 700 | 40px | -1px | new-order / Urbanist |
| H4 | 24px | 700 | 32px | -0.5px | new-order / Urbanist |
| H5 | 18px | 700 | 24px | -0.5px | new-order / Urbanist |
| H6 | 12px | 700 | 18px | — | mundial / Figtree |
| P1 | 22px | 400 | 34px | -1px | mundial / Figtree |
| P2 | 18px | 400 | 28px | -0.5px | mundial / Figtree |
| P3 (body) | 16px | 400 | 24px | -0.5px | mundial / Figtree |
| P4 | 14px | 400 | 16px | -0.2px | mundial / Figtree |
| Quote | 19px | 700 | 29px | -0.5px | mundial / Figtree |

### Typography Rules
- **All headings use negative letter-spacing** (tight tracking) — this is a core brand characteristic
- H6 is the only heading that uses the body font (mundial/Figtree)
- Heading margins zeroed out — spacing handled by parent layout
- Body text base: 16px, weight 400, -0.5px letter-spacing

---

## 3. Logo

### Wordmark (SVG — use on documents, headers, slides)

```svg
<svg width="493" height="146" viewBox="0 0 493 146" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M245.48 45.4229C245.48 15.4778 226.421 0 195.48 0H145.884V145.986H178.818V88.8532L214.914 145.986H254.59L212.734 85.6768C233.366 80.5223 245.465 65.4488 245.465 45.4084L245.48 45.4229ZM193.892 62.4889H178.818V28.3712H193.892C204.995 28.3712 211.94 34.9118 211.94 45.4373C211.94 55.9628 204.995 62.5034 193.892 62.5034V62.4889Z" fill="#0E1C2D"/>
<path d="M307.362 0L258.171 145.986H292.087L298.829 123.967H348.02L354.763 145.986H389.083L339.487 0H307.348H307.362ZM307.362 95.8125L323.23 44.0368L339.3 95.8125H307.362Z" fill="#0E1C2D"/>
<path d="M457.693 0L431.704 53.7538L405.513 0H368.421L415.042 89.0698V145.986H447.961V89.0698L492.2 0H457.693Z" fill="#0E1C2D"/>
<path d="M91.481 0L47.7185 73L91.481 146H131.417L87.6548 73L131.417 0H91.481Z" fill="#0E1C2D"/>
<path d="M0 146H39.9363L49.8265 129.497L29.8584 96.1879L0 146Z" fill="#0E1C2D"/>
<path d="M49.8265 16.503L39.9363 0H0L29.8584 49.7977L49.8265 16.503Z" fill="#0E1C2D"/>
</svg>
```

**On dark backgrounds:** change all `fill="#0E1C2D"` to `fill="white"` or `fill="floralwhite"`

### Round Logo Mark (SVG — use for avatars, favicons, compact contexts)

```svg
<svg width="400" height="400" viewBox="0 0 400 400" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M279.82 145.99H261.68V187.04H279.82C293.19 187.04 301.54 179.16 301.54 166.52C301.54 153.88 293.19 145.99 279.82 145.99Z" fill="#0E1C2D"/>
<path d="M199.69 0C89.4 0 0 89.4 0 199.69C0 309.98 89.4 399.38 199.69 399.38C309.98 399.38 399.38 309.98 399.38 199.69C399.38 89.4 309.98 0 199.69 0ZM94.59 111.87L106.49 131.72L82.47 171.79L46.55 111.87H94.6H94.59ZM94.59 287.51H46.54L82.46 227.59L106.48 267.66L94.58 287.51H94.59ZM204.65 287.51H156.6L103.95 199.69L156.6 111.87H204.65L151.99 199.69L204.65 287.51ZM305.11 287.51L261.68 218.78V287.51H222.06V111.87H281.72C318.95 111.87 341.86 130.48 341.86 166.52C341.86 190.62 327.3 208.76 302.48 214.97L352.84 287.52H305.11V287.51Z" fill="#0E1C2D"/>
</svg>
```

### Logo Rules
- Single-color only — never multicolor or gradient
- Acceptable fills: Gray 900 (light bg), White (dark bg), Blue 500 (accent contexts only)
- Minimum clear space = height of the "X" letterform
- Navbar max-height: 64px

---

## 4. Spacing System

### Section Spacing

| Context | Padding |
|---------|---------|
| Section (default) | 48px vertical / 16px horizontal |
| Hero | 48px vertical / 16px horizontal |
| Footer | 96px top, 16px horizontal, 16px bottom |
| Navbar | 24px vertical / 16px horizontal |

### Container Widths

| Variant | Max Width |
|---------|-----------|
| Default | 1280px |
| Medium | 1024px |
| Narrow | 846px |
| Slim | 776px |

### Common Gaps

| Context | Gap |
|---------|-----|
| Grid columns/rows | 24px |
| Section title to content | 16px |
| Section bottom margin | 40px |
| Card internal | 16px |
| Blog grid | 32px |

---

## 5. Component Styles

### Primary Button
```css
background: #1566b9;
color: white;
font-family: new-order, Urbanist, sans-serif;
font-size: 16px;
font-weight: 600;
border-radius: 8px;
padding: 16px 24px;
text-transform: capitalize;
/* Hover: background #0f4185 */
/* Disabled: background #c3c2bf */
```

### Ghost Button
```css
background: transparent;
border: 1px solid #b9d6f0;
color: #1566b9;
/* Hover: background #e6f1fb, border #8cb8e0, color #0f4185 */
```

### Cards
- White background, Gray 200 borders/dividers
- 16px internal padding
- Accent variant: Yellow 500 (`#f5cf45`) background

### Dark Sections (Footer, CTA)
- Background: Gray 900 (`#0e1c2d`)
- Text: Gray 300 (`#c3c2bf`)
- Logo/icons: White

---

## 6. Application Guidelines by Document Type

### PowerPoint / Presentations
- Title slides: Gray 900 background (`#0e1c2d`), white XRAY wordmark (bottom-left), white headline text
- Content slides: Off-White (`floralwhite`) background, Gray 900 headings, Gray 600 body
- Accent elements: Blue 500 for callouts, Yellow 500 for highlights, Red 500 sparingly for alerts
- Font fallbacks: Urbanist (headings), Figtree (body) — both available via Google Fonts

### Word Documents / PDFs
- Page background: white or off-white (`floralwhite`)  
- Headings: Gray 900, Urbanist/new-order, bold, tight tracking
- Body: Gray 600, Figtree/mundial
- Accent bars/dividers: Blue 500
- Logo placement: top-left header, full wordmark

### HTML / Web Artifacts
- Use CSS variables prefixed `--_brand-colors-2026---` and `--_brand-fonts-2026---`
- Example: `--_brand-colors-2026---blue-500: #1566b9`
- Always set page background to `floralwhite`, never pure white
- Import Google Fonts fallbacks when Adobe Fonts unavailable

### Email Templates
- Background: `floralwhite`
- Header section: Gray 900 background with white wordmark
- CTA buttons: Blue 500, white text, 8px border-radius
- Footer: Gray 900 background, Gray 300 text

---

## 7. Do's and Don'ts

### ✅ Do
- Use floralwhite (not pure white) as page backgrounds
- Apply tight negative letter-spacing to all headings
- Keep logo single-color
- Use Gray 900 for all headings on light backgrounds
- Use Blue 500 as the primary interactive/CTA color

### ❌ Don't
- Use pure black `#000` anywhere
- Use pure white `#ffffff` as a page background
- Make the logo multicolor or add gradients
- Mix font weights arbitrarily — stick to 400, 600, 700
- Use Red 500 or Yellow 500 as primary colors — they are accents only

---

## 8. Quick Reference Hex Cheat Sheet

```
BACKGROUNDS:   floralwhite (page)  |  #0e1c2d (dark sections)
HEADINGS:      #0e1c2d
BODY TEXT:     #686f76
MUTED TEXT:    #868b8e
BORDERS:       #e1ded8
PRIMARY CTA:   #1566b9  (hover: #0f4185)
ACCENT RED:    #f55647
ACCENT YELLOW: #f5cf45
```
