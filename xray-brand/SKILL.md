---
name: xray-brand
description: Apply XRAY's official 2026 brand identity — colors, typography, logo, and component styles — to any document, presentation, web artifact, or design output. Use this skill any time someone asks to create or style something for XRAY, apply XRAY's brand, generate XRAY-branded materials, or produce documents that should follow XRAY's visual identity. Triggers include: "XRAY branded", "make it look like XRAY", "apply our brand", "XRAY style", "brand this document", "XRAY presentation", or any request to produce a deliverable for the company XRAY (Workflow Automation Consultancy). This skill should always be used when producing XRAY-branded outputs, even if the user doesn't explicitly say "brand guidelines."
---

# XRAY Brand Skill

## Overview

XRAY is a **Workflow Automation Consultancy** with the tagline _"Workflow Automation That Actually Works."_

**Brand personality:** Professional, clear, modern, warm, approachable. Minimal and purposeful decoration — hand-drawn line art, geometric patterns (dots, arcs, circles), subtle background illustrations. Simplicity over complexity.

## Essential Rules

- **Never** use pure black (`#000`) — use Gray 900 (`#0e1c2d`) instead
- **Page background** is always `floralwhite` — never pure white
- **All headings** use negative letter-spacing (tight tracking)
- **Logo** is single-color only — never multicolor or gradient

## Reference Files

Load these as needed for detailed specifications:

- **[references/colors.md](references/colors.md)** — Full color palette, brand blues, accents
- **[references/typography.md](references/typography.md)** — Font families, type scale, rules
- **[references/components.md](references/components.md)** — Buttons, cards, spacing system

## Logo Assets

Use these SVG files for logo placement:

- **[assets/wordmark.svg](assets/wordmark.svg)** — Full XRAY wordmark for headers, documents
- **[assets/round-logo.svg](assets/round-logo.svg)** — Round mark for avatars, favicons

**Logo rules:**
- Light backgrounds: use fill `#0E1C2D`
- Dark backgrounds: change fill to `white` or `floralwhite`
- Minimum clear space = height of the "X" letterform
- Navbar max-height: 64px

## What "Properly Branded" Means

**Important:** Proper branding is NOT just updating colors. A properly XRAY-branded deliverable must include:

1. **The XRAY logo** — wordmark or round logo, appropriately placed
2. **Correct backgrounds** — floralwhite for content, Gray 900 for dark sections
3. **Brand typography** — Urbanist headings, Figtree body
4. **Full color palette** — not just swapping a few colors

If asked to "brand" or "apply XRAY styling" to something, always add the logo and restructure to match brand guidelines — don't just find/replace colors.

## Application by Document Type

### PowerPoint / Presentations

**Required elements for proper branding:**
- Title slide: Gray 900 (`#0E1C2D`) background with white XRAY wordmark (bottom-left)
- Content slides: `floralwhite` background
- XRAY logo in header or footer on every slide
- Urbanist for headings, Figtree for body text
- Gray 900 headings, Gray 600 body text on light backgrounds

### Word Documents / PDFs
- Page background: white or floralwhite
- Headings: Gray 900, Urbanist/new-order, bold, tight tracking
- Body: Gray 600, Figtree/mundial
- Logo: top-left header, full wordmark

### HTML / Web Artifacts
- Set page background to `floralwhite`
- Import Google Fonts: Urbanist + Figtree
- Use Blue 500 (`#1566b9`) for CTAs and links

### Email Templates
- Header: Gray 900 bg with white wordmark
- Body: floralwhite bg
- CTA buttons: Blue 500, white text, 8px radius
- Footer: Gray 900 bg, Gray 300 text

## Do's and Don'ts

### Do
- Use floralwhite (not pure white) as page backgrounds
- Apply tight negative letter-spacing to all headings
- Keep logo single-color
- Use Gray 900 for all headings on light backgrounds
- Use Blue 500 as the primary interactive/CTA color

### Don't
- Use pure black `#000` anywhere
- Use pure white `#ffffff` as a page background
- Make the logo multicolor or add gradients
- Mix font weights arbitrarily — stick to 400, 600, 700
- Use Red 500 or Yellow 500 as primary colors — they are accents only

## Quick Reference

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
