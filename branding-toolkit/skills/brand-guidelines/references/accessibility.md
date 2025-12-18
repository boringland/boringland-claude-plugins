# Accessibility Guidelines for Brand Design

## WCAG Color Contrast Requirements

### Text Contrast Ratios

| Level | Normal Text (<18pt) | Large Text (≥18pt or 14pt bold) |
|-------|--------------------|---------------------------------|
| AA    | 4.5:1              | 3:1                             |
| AAA   | 7:1                | 4.5:1                           |

### Non-Text Contrast

UI components and graphical objects require 3:1 contrast against adjacent colors:
- Form field borders
- Icons
- Focus indicators
- Charts and graphs

## Testing Contrast

### Manual Calculation

```
Contrast ratio = (L1 + 0.05) / (L2 + 0.05)
```

Where L1 is lighter color luminance, L2 is darker.

### Tools

- WebAIM Contrast Checker: https://webaim.org/resources/contrastchecker/
- Colour Contrast Analyser (desktop app)
- Chrome DevTools Contrast Checker (inspect element)
- Figma/Sketch plugins (Stark, A11y)

## Color Blindness Considerations

### Types and Prevalence

| Type | Affected Colors | Prevalence (Male) |
|------|-----------------|-------------------|
| Protanopia | Red-green | 1% |
| Deuteranopia | Red-green | 1% |
| Protanomaly | Red-green | 1% |
| Deuteranomaly | Red-green | 5% |
| Tritanopia | Blue-yellow | 0.001% |

### Design Strategies

1. **Never rely on color alone**
   - Add icons to status indicators
   - Use patterns in charts
   - Include text labels

2. **Test with simulation tools**
   - Chrome DevTools: Rendering > Emulate vision deficiencies
   - Sim Daltonism (macOS)
   - Color Oracle (Windows/Mac/Linux)

3. **Safe color combinations**
   - Blue + Orange (safe for most)
   - Blue + Yellow (avoid if tritanopia concern)
   - Avoid red/green only distinctions

## Focus Indicators

### Requirements

- Visible focus indicator on all interactive elements
- 3:1 contrast against adjacent colors
- Focus must be obvious and not just a color change

### Best Practices

```css
/* Good: High visibility focus */
:focus-visible {
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}

/* Bad: Invisible or low contrast */
:focus {
  outline: none; /* Never do this */
}
```

## Motion and Animation

### Respect User Preferences

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Guidelines

- Avoid auto-playing animations
- Provide pause controls for motion
- Keep animations under 5 seconds
- Avoid flashing content (3 flashes/second max)

## Typography Accessibility

### Minimum Sizes

- Body text: 16px minimum
- Secondary text: 14px minimum
- Never below 12px for any text

### Line Length

- Optimal: 50-75 characters per line
- Maximum: 80 characters

### Line Height

- Body text: 1.5 minimum
- Never below 1.2

### Font Choice

- Prefer fonts with:
  - Clear letter distinction (Il1, O0)
  - Adequate x-height
  - Consistent stroke width
- Avoid:
  - Thin weights (<300) for body text
  - Decorative fonts for body text
  - All-caps for long passages

## Dark Mode Accessibility

### Additional Considerations

1. **Reduce contrast slightly**
   - Pure white (#fff) on pure black (#000) can cause halation
   - Use off-white (#e0e0e0) on dark gray (#1a1a1a)

2. **Increase font weight slightly**
   - Light text on dark appears thinner
   - Bump body from 400 to 450 weight

3. **Desaturate colors**
   - Bright colors on dark can cause eye strain
   - Reduce saturation by 10-20%

## Semantic HTML and ARIA

### Color Cannot Convey Meaning

When using color for status:

```html
<!-- Bad: Color only -->
<span class="error">Error</span>

<!-- Good: Color + icon + text -->
<span class="error">
  <svg aria-hidden="true"><!-- error icon --></svg>
  Error: Please enter a valid email
</span>
```

### Charts and Graphs

- Use patterns in addition to colors
- Provide data tables as alternatives
- Include descriptive alt text

## Testing Checklist

### Automated

- [ ] Run axe DevTools
- [ ] Check with Lighthouse accessibility audit
- [ ] Validate HTML structure

### Manual

- [ ] Test with screen reader (VoiceOver, NVDA)
- [ ] Navigate with keyboard only
- [ ] Test at 200% zoom
- [ ] Test with color blindness simulator
- [ ] Test with high contrast mode
- [ ] Test with reduced motion preference

### User Testing

- [ ] Include users with disabilities
- [ ] Test with assistive technologies
- [ ] Gather feedback on pain points
