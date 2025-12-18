# [Brand Name] Color Palette

## Primary Palette

### Primary
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**RGB:** [r], [g], [b]
**Usage:** Main brand color for CTAs, links, and key brand moments

**Accessibility:**
- On dark background: [contrast ratio] (AA/AAA)
- On light background: [contrast ratio] (AA/AAA)

---

### Secondary
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**RGB:** [r], [g], [b]
**Usage:** Supporting accent for highlights and secondary actions

---

### Accent
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**RGB:** [r], [g], [b]
**Usage:** Attention-grabbing elements, notifications, badges

---

## Background & Surface

### Background
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Main page background

### Surface
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Cards, modals, elevated elements

---

## Text Colors

### Text Primary
```
████ Sample text in primary color
```
**Hex:** `#[hex]`
**Usage:** Main body text, headings

### Text Secondary
```
████ Sample text in secondary color
```
**Hex:** `#[hex]`
**Usage:** Descriptions, captions

### Text Muted
```
████ Sample text in muted color
```
**Hex:** `#[hex]`
**Usage:** Placeholders, disabled states

---

## Semantic Colors

### Success 🟢
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Success messages, confirmations, positive states

### Warning 🟡
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Warnings, caution states, pending actions

### Error 🔴
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Errors, destructive actions, alerts

### Info 🔵
```
█████████████████████████████████████████
```
**Hex:** `#[hex]`
**Usage:** Informational messages, tips, help text

---

## Border Colors

### Border Default
```
────────────────────────────────────────
```
**Hex:** `#[hex]`
**Usage:** Standard borders, dividers

### Border Subtle
```
────────────────────────────────────────
```
**Hex:** `#[hex]`
**Usage:** Subtle separators, light dividers

---

## CSS Variables

```css
:root {
  /* Primary palette */
  --color-primary: #[hex];
  --color-secondary: #[hex];
  --color-accent: #[hex];

  /* Background & surface */
  --color-background: #[hex];
  --color-surface: #[hex];

  /* Text */
  --color-text: #[hex];
  --color-text-secondary: #[hex];
  --color-text-muted: #[hex];

  /* Semantic */
  --color-success: #[hex];
  --color-warning: #[hex];
  --color-error: #[hex];
  --color-info: #[hex];

  /* Borders */
  --color-border: #[hex];
  --color-border-subtle: #[hex];
}
```

---

## Tailwind Classes

```javascript
colors: {
  primary: 'var(--color-primary)',
  secondary: 'var(--color-secondary)',
  accent: 'var(--color-accent)',
  background: 'var(--color-background)',
  surface: 'var(--color-surface)',
  // ...
}
```

---

## Accessibility Matrix

| Color Combination | Contrast Ratio | WCAG Level |
|-------------------|----------------|------------|
| Primary on Background | [X.X]:1 | AA/AAA |
| Secondary on Background | [X.X]:1 | AA/AAA |
| Text on Background | [X.X]:1 | AA/AAA |
| Text on Surface | [X.X]:1 | AA/AAA |
| Success on Background | [X.X]:1 | AA/AAA |
| Error on Background | [X.X]:1 | AA/AAA |

### Requirements

- **AA (Normal text):** 4.5:1 minimum
- **AA (Large text):** 3:1 minimum
- **AAA (Normal text):** 7:1 minimum
- **AAA (Large text):** 4.5:1 minimum

---

## Color Usage Examples

### Button States

| State | Background | Text | Border |
|-------|------------|------|--------|
| Default | Primary | White | None |
| Hover | Primary (darken 10%) | White | None |
| Active | Primary (darken 20%) | White | None |
| Disabled | Muted | Text Muted | Border |

### Form Elements

| Element | Background | Text | Border |
|---------|------------|------|--------|
| Input | Surface | Text | Border |
| Input (focus) | Surface | Text | Primary |
| Input (error) | Surface | Text | Error |
| Label | Transparent | Text Secondary | None |

### Alerts

| Type | Background | Text | Icon |
|------|------------|------|------|
| Success | Success (10% opacity) | Success | ✓ |
| Warning | Warning (10% opacity) | Warning | ⚠ |
| Error | Error (10% opacity) | Error | ✕ |
| Info | Info (10% opacity) | Info | ℹ |

---

## Dark Mode Adjustments

If supporting dark mode, these colors may need adjustment:

| Light Mode | Dark Mode | Notes |
|------------|-----------|-------|
| #[hex] | #[hex] | Primary slightly less saturated |
| #[hex] | #[hex] | Background darker |
| #[hex] | #[hex] | Text lighter |

---

*Generated by branding-toolkit*
*Last updated: [Date]*
