# Color Theory for Brand Design

## Color Psychology

Colors evoke emotional responses. Consider these associations when building a brand palette:

### Warm Colors

**Red**
- Associations: Energy, passion, urgency, danger
- Use for: CTAs, alerts, sale notifications
- Caution: Can feel aggressive if overused

**Orange**
- Associations: Enthusiasm, creativity, warmth, friendliness
- Use for: Highlights, secondary actions, playful elements
- Caution: Can feel cheap if paired poorly

**Yellow**
- Associations: Optimism, clarity, warmth, caution
- Use for: Highlights, warnings, attention-grabbing moments
- Caution: Hard to read, use sparingly for text

### Cool Colors

**Blue**
- Associations: Trust, stability, professionalism, calm
- Use for: Corporate brands, tech, finance, healthcare
- Caution: Can feel cold or impersonal

**Green**
- Associations: Growth, nature, health, success, money
- Use for: Success states, eco brands, health, finance
- Caution: Avoid yellow-greens which can look sickly

**Purple**
- Associations: Luxury, creativity, mystery, royalty
- Use for: Premium brands, creative industries, spirituality
- Caution: Can feel immature with wrong shades

### Neutral Colors

**Black**
- Associations: Sophistication, power, elegance, formality
- Use for: Luxury brands, fashion, high-contrast designs

**White**
- Associations: Cleanliness, simplicity, space, purity
- Use for: Minimalist designs, healthcare, tech

**Gray**
- Associations: Balance, neutrality, professionalism
- Use for: Backgrounds, borders, secondary text

## Color Harmony

### Complementary

Colors opposite on the wheel (e.g., blue + orange). High contrast, energetic.

### Analogous

Adjacent colors (e.g., blue + blue-green + green). Harmonious, cohesive.

### Triadic

Three colors equally spaced (e.g., red + yellow + blue). Vibrant, balanced.

### Split-Complementary

Base color + two adjacent to its complement. Less tension than complementary.

### Monochromatic

Single hue with varied lightness/saturation. Elegant, unified.

## Building a Palette

### Step 1: Start with Primary

Choose a primary color that:
- Reflects brand personality
- Works in digital contexts
- Has sufficient contrast potential

### Step 2: Select Secondary

Choose secondary that:
- Complements primary (use color harmony)
- Provides visual variety
- Works for secondary actions

### Step 3: Add Accent

Choose accent that:
- Stands out from primary/secondary
- Can draw attention to key elements
- Is used sparingly

### Step 4: Define Neutrals

Build neutral scale that:
- Works with primary palette
- Provides text contrast
- Creates visual hierarchy

### Step 5: Add Semantic Colors

Define functional colors:
- Success (typically green)
- Warning (typically yellow/orange)
- Error (typically red)
- Info (typically blue)

## Dark Mode Considerations

When designing for dark mode:

1. **Don't just invert** - Pure black backgrounds strain eyes
2. **Reduce saturation** - Bright colors on dark feel harsh
3. **Adjust contrast** - Dark mode needs less contrast
4. **Test thoroughly** - Colors behave differently on dark

### Dark Mode Palette Shifts

| Light Mode | Dark Mode Adjustment |
|------------|---------------------|
| White background | Dark gray (#121212-#1a1a1a), not black |
| Black text | Light gray (#e0e0e0), not white |
| Saturated primary | Slightly desaturated |
| Shadows | Lighter, more subtle |

## Color Naming Conventions

### Semantic Names (Recommended)

```css
--color-primary: #00ff41;
--color-text: #ffffff;
--color-background: #0a0a0f;
--color-success: #00d26a;
```

Benefits: Self-documenting, theme-friendly

### Scale Names

```css
--blue-100: #e6f0ff;
--blue-500: #0066ff;
--blue-900: #001a40;
```

Benefits: Flexible, systematic

### Avoid

```css
--green: #00ff41;  /* What if brand changes? */
--dark-blue: #001a40;  /* Relative to what? */
```

## Testing Colors

### Contrast Checkers

Use tools to verify WCAG compliance:
- WebAIM Contrast Checker
- Stark (Figma plugin)
- Colour Contrast Analyser

### Color Blindness

Test for:
- Protanopia (red-blind)
- Deuteranopia (green-blind)
- Tritanopia (blue-blind)

Never rely on color alone for meaning.

### Device Variation

Colors appear differently on:
- Different monitors (calibration varies)
- Mobile vs desktop
- Retina vs standard displays

Test on multiple devices.
