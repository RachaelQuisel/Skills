# XRAY Components & Layout

## Spacing System

### Section Spacing

| Context | Padding |
|---|---|
| Section (default) | `48px 16px` |
| Hero | `48px 16px` |
| Footer | `96px 16px 16px` |
| Navbar | `24px 16px` |

### Container Widths

| Class | Max Width |
|---|---|
| `.container` (default) | 1280px |
| `.container._1024px` | 1024px |
| `.container._846px` | 846px |
| `.container._776px` | 776px |

### Common Gaps

| Context | Gap |
|---|---|
| Grid columns/rows | 24px |
| Section lead (title to content) | 16px |
| Section lead bottom margin | 40px |
| Button row | 10px |
| Card internal | 16px |
| Footer column items | 24px |
| Blog grid | 32px |
| Team grid | 24px col / 40px row |

---

## Buttons

### Primary Button (`.button`)

```css
background-color: #1566b9;    /* blue-500 */
color: white;
font-family: new-order, sans-serif;
font-size: 16px;
font-weight: 600;
line-height: 16px;
letter-spacing: 0;
text-transform: capitalize;
text-align: center;
border-radius: 8px;
padding: 16px 24px;
```

**States:**
- **Hover:** `background-color: #0f4185`
- **Active:** `box-shadow: inset 0 0 0 2px #0f4185`
- **Disabled:** `background-color: #c3c2bf`

### Small Button (`.button.small`)

```css
padding: 8px 16px;
```

### Ghost Button (`.button.ghost`)

```css
background-color: transparent;
box-shadow: inset 0 0 0 1px #b9d6f0;
color: #1566b9;
```

**Hover:** `background-color: #e6f1fb; box-shadow: 0 0 0 1px #8cb8e0; color: #0f4185`

---

## Inputs

```css
background-color: transparent;
border: 1px solid #000;
border-radius: 8px;
height: 48px;
padding: 10px 16px;
font-family: mundial, sans-serif;
```

**Light variant:** `border-color: #e1ded8`

---

## Cards

### Content Card (`.content-card`)

```css
background-color: floralwhite;
color: #686f76;
border-radius: 24px;
padding: 40px;
gap: 16px;
```

### Stat Card (`.stat-card`)

```css
border: 1px solid #e1ded8;
border-radius: 24px;
text-align: center;
height: 176.5px;
```

### Generic Card (`.card`)

```css
background-color: #e1ded8;
border-radius: 24px;
padding: 40px;
```

### Box (`.box`)

```css
border: 1px solid #e1ded8;
border-radius: 24px;
padding: 40px;
transition: all 0.3s;
```

**Interactive hover:**
```css
border-color: #1566b9;
background-color: white;
box-shadow: 0 14px 24px 0 #0e1c2d33, inset 0 0 0 3px #1566b9;
```

---

## Navigation

### Navbar

```css
background-color: floralwhite;
padding: 24px 16px;
position: sticky;
top: 0;
```

### Nav Links

```css
font-family: mundial, sans-serif;
font-size: 18px;
line-height: 28px;
letter-spacing: -0.5px;
border-radius: 8px;
padding: 8px;
transition: all 0.2s;
```

**Hover:** `background-color: #e1ded8; color: #1566b9`

### Dropdown Menu

```css
background-color: white;
border-radius: 24px;
padding: 24px;
box-shadow: 0 14px 64px #0e1c2d1a;
```

---

## Footer

```css
background-color: #0e1c2d;
color: #c3c2bf;
padding: 96px 16px 16px;
```

- **Links:** Gray 300, border-bottom Gray 600, hover Gray 500
- **Copyright:** border-top Gray 800, margin-top 80px

---

## Border Radius Scale

| Size | Value | Usage |
|---|---|---|
| Small | `8px` | Buttons, inputs, nav links |
| Medium | `12px` | Thumbnails, blog images |
| Large | `16px` | FAQ cards, dropdown links |
| XL | `24px` | Content cards, modals, boxes |
| Circle | `100%` | Dots, spotlight elements |

---

## Shadows

| Context | Value |
|---|---|
| Dropdown menu | `0 14px 64px #0e1c2d1a` |
| Interactive box hover | `0 14px 24px 0 #0e1c2d33, inset 0 0 0 3px #1566b9` |
| Button active | `inset 0 0 0 2px #0f4185` |

---

## Transitions

| Context | Duration |
|---|---|
| Links | 0.2s ease |
| Box/card interactions | 0.3s ease |
| Nav link hover | 0.2s ease |

---

## Grid System

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 24px;
}
```

Common configurations: `1fr 1fr`, `1fr 1fr 1fr`, `1fr 1fr 1fr 1fr`

---

## Responsive Breakpoints

| Breakpoint | Max Width | Container |
|---|---|---|
| Desktop | — | 1280px |
| Tablet | 991px | 728px |
| Mobile | 767px | 100% |
| Small mobile | 479px | 100% |

---

## Dark Sections

```css
background-color: #0e1c2d;
color: #c3c2bf;
```

- Headings: white
- Body: Gray 300
- Links: Blue 500
- Borders: Gray 800 (`#2c3845`)

---

## Component Class Reference

| Component | Class | Variants |
|---|---|---|
| Button | `.button` | `.small`, `.ghost`, `.disabled` |
| Input | `.input` | `.light` |
| Card | `.card` | `.content-card`, `.stat-card` |
| Box | `.box` | `.interactive` |
| Section | `.section` | `.bg-dark`, `.cta` |
| Container | `.container` | `._776px`, `._1024px` |
