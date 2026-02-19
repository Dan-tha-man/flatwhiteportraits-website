# Sandpiper Portraits Design Language

A shared design system for web and iOS native applications.

---

## Color Palette

### Primary Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `sand-light` | `#f5f5f5` | Page backgrounds, light sections |
| `sand` | `#e0e0e0` | Card backgrounds, icon fills, dividers |
| `sand-dark` / `teal` | `#5A5858` | Primary accent — buttons, links, labels |
| `teal-dark` | `#4a4848` | Hover/active states for accent elements |
| `teal-light` | `#f5f5f5` | Alternate light background |

### Text Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `text` | `#333333` | Primary body text |
| `text-light` | `#666666` | Secondary/supporting text |
| `text-muted` | `#999999` | Captions, placeholders, metadata |

### Neutrals

| Token | Hex | Usage |
|-------|-----|-------|
| `white` | `#ffffff` | Backgrounds, card surfaces |
| `dark` | `#1a1a1a` | Footer background, overlays |
| `border` | `#e0e0e0` | Borders, separators |
| `black` | `#000000` | Image borders, high-contrast labels |

### Semantic Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `rating-gold` | `#d4a853` | Star ratings only |

### Contrast Notes

- `#5A5858` on `#ffffff` = **5.6:1** (passes WCAG AA for normal and large text)
- `#333333` on `#ffffff` = **12.6:1** (passes WCAG AAA)
- `#666666` on `#ffffff` = **5.7:1** (passes WCAG AA)
- `#999999` on `#ffffff` = **2.8:1** (use only for large text or decorative elements)

---

## Typography

### Font Families

| Role | Web | iOS Native |
|------|-----|------------|
| Display / Headings | Playfair Display (Google Fonts) | Playfair Display (bundled) |
| Body / UI | System stack (`-apple-system`, `Segoe UI`, etc.) | SF Pro (system default) |

### Web Font Loading

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
```

### Type Scale

| Level | Size | Weight | Font | Line Height | Usage |
|-------|------|--------|------|-------------|-------|
| Display | 2.4rem (38px) | 400 | Playfair Display | 1.25 | Section headings |
| H2 | 1.8rem (29px) | 400 | Playfair Display | 1.3 | Sub-section headings |
| H3 | 1.2rem (19px) | 600 | System sans | 1.4 | Card titles, labels |
| Body | 1rem (16px) | 400 | System sans | 1.7 | Paragraphs |
| Small | 0.9rem (14px) | 400 | System sans | 1.5 | Captions, metadata |
| Label | 0.8rem (13px) | 600 | System sans | 1.2 | Section labels, uppercase |

### Label Style

Section labels use uppercase with `letter-spacing: 0.12em` and the accent color (`#5A5858`).

---

## Spacing

| Token | Value | Usage |
|-------|-------|-------|
| `section-padding` | `6rem` (96px) | Vertical padding between major sections |
| `container-width` | `90%`, max `1100px` | Content container |
| `container-narrow` | max `720px` | Text-heavy content |
| `nav-height` | `72px` | Fixed navigation bar height |
| `gap-sm` | `1rem` (16px) | Small gaps between elements |
| `gap-md` | `2rem` (32px) | Medium spacing |
| `gap-lg` | `4rem` (64px) | Large spacing |

---

## Components

### Buttons

**Primary Button**
- Background: `#5A5858`
- Text: `#ffffff`
- Border-radius: `0` (sharp corners)
- Padding: `1rem 2.5rem`
- Font: system sans, `0.85rem`, weight 600, uppercase, `letter-spacing: 0.1em`
- Hover: background `#4a4848`
- Transition: `0.3s ease`

**Secondary / Outline Button**
- Background: transparent
- Border: `2px solid #5A5858`
- Text: `#5A5858`
- Hover: background `#5A5858`, text `#ffffff`

### Cards

- Background: `#ffffff`
- Border: `1px solid #e0e0e0`
- Border-radius: `0` or `12px` (context-dependent)
- Shadow: `0 2px 20px rgba(0,0,0,0.08)` for elevated cards
- Padding: `2rem`

### Navigation

- Fixed top bar, `72px` height
- Background: `#ffffff` with `backdrop-filter: blur(20px)`
- Border-bottom: `1px solid #e0e0e0` on scroll
- Logo: system sans, `1.3rem`, weight 700, `letter-spacing: 0.08em`

### Sections

- Alternating backgrounds: `#ffffff` and `#f5f5f5`
- Section label + heading + body text pattern
- Max content width `1100px`, centered

---

## Web to iOS Mapping

| Concept | Web (CSS) | iOS (SwiftUI) |
|---------|-----------|---------------|
| Accent color | `var(--color-teal)` `#5A5858` | `Color("AccentTaupe")` in asset catalog |
| Heading font | `font-family: 'Playfair Display'` | `.custom("PlayfairDisplay-Regular", size:)` |
| Body font | `font-family: var(--font-sans)` | `.body` (SF Pro, system default) |
| Primary background | `var(--color-white)` | `Color(.systemBackground)` |
| Secondary background | `var(--color-sand-light)` | `Color(.secondarySystemBackground)` |
| Primary text | `var(--color-text)` | `Color.primary` |
| Secondary text | `var(--color-text-light)` | `Color.secondary` |
| Border | `var(--color-border)` | `Color(.separator)` |
| Button style | `.btn-primary` class | `ButtonStyle` with accent fill |
| Card | border + shadow | `.background(.regularMaterial)` + shadow |
| Section padding | `6rem` vertical | `32pt` vertical (density-adjusted) |
| Transition | `0.3s ease` | `.easeInOut(duration: 0.3)` |

### iOS Asset Catalog Colors

Define these in `Assets.xcassets`:

| Name | Light | Dark (suggested) |
|------|-------|-------------------|
| `AccentTaupe` | `#5A5858` | `#A0A0A0` |
| `AccentTaupeHover` | `#4a4848` | `#B0B0B0` |
| `SandLight` | `#f5f5f5` | `#1C1C1E` |
| `Sand` | `#e0e0e0` | `#2C2C2E` |
| `RatingGold` | `#d4a853` | `#d4a853` |

---

## Motion

| Property | Value |
|----------|-------|
| Default transition | `0.3s ease` |
| Hover scale (cards) | `translateY(-2px)` |
| Fade-in | opacity `0 → 1`, `0.6s ease` |
| iOS spring | `.spring(response: 0.35, dampingFraction: 0.8)` |

---

## Image Treatment

- Portrait images use `object-fit: cover` with `aspect-ratio: 3/4`
- Black borders on framed images: `3px solid #000`
- Right-click disabled on all images (web)
- User-select disabled on images (web)
