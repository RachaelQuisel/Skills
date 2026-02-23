# XRAY Color System

All colors are defined as CSS custom properties on `:root`. Use the variable names in production CSS.

**Variable naming convention:** `--_brand-colors-2026---{token}`

---

## Core Palette (Grays)

| Token | Hex | Role |
|---|---|---|
| **Gray 900** | `#0e1c2d` | Headings, dark backgrounds, primary text on light |
| **Gray 800** | `#2c3845` | Footer borders, secondary dark elements |
| **Gray 600** | `#686f76` | Body text (default), nav links |
| **Gray 500** | `#868b8e` | Muted/tertiary text |
| **Gray 300** | `#c3c2bf` | Footer text on dark, disabled button bg, sublabels |
| **Gray 200** | `#e1ded8` | Borders, dividers, section breaks, card backgrounds |
| **Gray 100** | `#0e1c2d0d` | Subtle tinted background (5% opacity of gray-900) |

---

## Brand Blues (Primary Action Color)

| Token | Hex | Role |
|---|---|---|
| **Blue 900** | `#192f4f` | Deepest blue, rare usage |
| **Blue 700** | `#0f4185` | Button hover state, active link text |
| **Blue 500** | `#1566b9` | **Primary CTA**, links, interactive accents |
| **Blue 300** | `#8cb8e0` | Ghost button hover border |
| **Blue 200** | `#b9d6f0` | Ghost button default border |
| **Blue 100** | `#e6f1fb` | Ghost button hover background |

---

## Accent & Utility Colors

| Token | Hex | Role |
|---|---|---|
| **Off-White 100** | `floralwhite` | Page background, navbar background |
| **Off-White 200** | `#feefcf` | FAQ card backgrounds, pricetag backgrounds |
| **White** | `white` | Button text on blue, dropdown menus, card surfaces |
| **Red 500** | `#f55647` | Alert/accent, decorative circle element |
| **Yellow 500** | `#f5cf45` | Highlight accent, special card backgrounds |
| **Clear** | `#fff0` | Transparent (ghost button bg, input bg) |
| **Overlay** | `#0e1c2dcc` | Modal backdrop (80% opacity of gray-900) |

---

## Color Usage Rules

- **Page background** is always `floralwhite` (Off-White 100) — never pure white
- **Body text** defaults to Gray 600 (`#686f76`)
- **Headings** are always Gray 900 (`#0e1c2d`) — near-black with a navy undertone
- **Links** are Blue 500 (`#1566b9`), hover to Blue 700 (`#0f4185`)
- **Dark sections** (footer, CTA blocks) use Gray 900 background with Gray 300 text
- **Never** use pure black (`#000`) for text or backgrounds
- **Contrast pairs:** Gray 900 on Off-White 100 (light mode), Gray 300 on Gray 900 (dark mode)

---

## Quick Copy-Paste

```
Page background:  floralwhite
Dark background:  #0e1c2d
Headings:         #0e1c2d
Body text:        #686f76
Muted text:       #868b8e
Borders:          #e1ded8
Primary CTA:      #1566b9
CTA hover:        #0f4185
Accent red:       #f55647
Accent yellow:    #f5cf45
```
