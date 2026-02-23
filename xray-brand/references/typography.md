# XRAY Typography

## Font Families

| Role | Primary Font | Google Fallback | Variable |
|---|---|---|---|
| **Headlines & Buttons** | `new-order` | `Urbanist` | `--_brand-fonts-2026---header` |
| **Body & UI text** | `mundial` | `Figtree` | `--_brand-fonts-2026---body` |

Primary fonts are loaded via Adobe Fonts (Typekit). When unavailable, use Google Font equivalents.

### CSS Font Stacks

```css
/* Adobe Fonts (preferred) */
font-family: new-order, sans-serif;      /* headlines */
font-family: mundial, sans-serif;        /* body */

/* Google Fonts fallback */
font-family: 'Urbanist', sans-serif;     /* headlines */
font-family: 'Figtree', sans-serif;      /* body */
```

### Google Fonts Import

```html
<link href="https://fonts.googleapis.com/css2?family=Urbanist:wght@400;600;700&family=Figtree:wght@400;600;700&display=swap" rel="stylesheet">
```

---

## Type Scale

### Display Sizes (Hero/feature sections)

| Class | Size | Weight | Line Height | Letter Spacing |
|---|---|---|---|---|
| `.display-1` | 96px | 700 | 115% | -2.5px |
| `.display-2` | 72px | 700 | 80px | -2.5px |

### Heading Sizes

| Element | Size | Weight | Line Height | Letter Spacing | Font |
|---|---|---|---|---|---|
| `h1` / `.h1` | 56px | 700 | 64px | -1px | new-order |
| `h2` / `.h2` | 40px | 700 | 48px | -1px | new-order |
| `h3` / `.h3` | 32px | 700 | 40px | -1px | new-order |
| `h4` / `.h4` | 24px | 700 | 32px | -0.5px | new-order |
| `h5` / `.h5` | 18px | 700 | 24px | -0.5px | new-order |
| `h6` | 12px | 700 | 18px | — | mundial |

### Paragraph Sizes

| Class | Size | Weight | Line Height | Letter Spacing |
|---|---|---|---|---|
| `.p1` | 22px | 400 | 34px | -1px |
| `.p2` | 18px | 400 | 28px | -0.5px |
| `.p3` (default) | 16px | 400 | 24px | -0.5px |
| `.p4` | 14px | 400 | 16px | -0.2px |

### Weight Utilities

| Class | Weight |
|---|---|
| `.weight-400` | 400 (regular) |
| `.weight-600` | 600 (semi-bold) |
| `.weight-700` | 700 (bold) |

---

## Typography Rules

- **All headings use negative letter-spacing** (tight tracking) — core brand characteristic
- Body text base: 16px, weight 400, -0.5px letter-spacing
- Heading margins are zeroed — spacing handled by parent layout
- `h6` is the only heading using the body font (`mundial`)
- `.p3.quote` variant: 19px, weight 700, line-height 29px (testimonials)

### Responsive Adjustments

| Breakpoint | Changes |
|---|---|
| Tablet (≤991px) | Body `p` scales to 18px/26px |
| Small mobile (≤479px) | `.h1` → 1.6rem, `.display-1` → 47px |

---

## Text Utility Classes

| Class | Effect |
|---|---|
| `.text-white` | `color: white` |
| `.text-black` | `color: #0e1c2d` (gray-900) |
| `.text-blue` | `color: #1566b9` (blue-500) |
| `.text-gray` | `color: #868b8e` (gray-500) |
| `.text-left` | `text-align: left` |
| `.text-center` | `text-align: center` |
| `.text-right` | `text-align: right` |
