---
name: Brand Guidelines
description: This skill should be used when the user asks about "brand colors", "typography", "logo usage", "visual identity", "color palette", "font choices", "brand consistency", "design system colors", or needs guidance on defining or maintaining visual brand elements. Provides comprehensive guidance for establishing and maintaining consistent visual identity across web applications.
version: 0.1.0
---

# Brand Guidelines

## Purpose

This skill provides guidance for establishing, documenting, and maintaining visual brand identity in web applications. It covers color systems, typography, logo usage, spacing, and visual consistency principles.

## When to Use

Activate this skill when working on:

- Defining or reviewing color palettes
- Selecting and implementing typography systems
- Establishing logo usage guidelines
- Creating spacing and layout systems
- Auditing visual consistency
- Building design system foundations

## Core Concepts

### Color Systems

A robust color system includes:

**Primary Palette**
- Primary color: Main brand identifier (buttons, links, key UI elements)
- Secondary color: Supporting accent (hover states, highlights)
- Accent color: Attention-grabbing moments (CTAs, notifications)

**Neutral Palette**
- Background colors (light/dark modes)
- Text colors (primary, secondary, muted)
- Border and divider colors
- Surface colors (cards, modals)

**Semantic Colors**
- Success: Confirmations, completed states
- Warning: Caution, pending states
- Error: Failures, destructive actions
- Info: Helpful information

### Color Definition Best Practices

Define colors with purpose, not just hex values:

```yaml
colors:
  primary:
    value: "#00ff41"
    usage: "Primary actions, links, key brand moments"
    contrast_on_dark: "AAA"

  secondary:
    value: "#ffb000"
    usage: "Secondary actions, highlights, accents"
```

Always verify WCAG contrast ratios:
- AA standard: 4.5:1 for normal text, 3:1 for large text
- AAA standard: 7:1 for normal text, 4.5:1 for large text

### Typography

**Font Selection Principles**

- Display font: Headlines, hero text, brand moments (can be decorative)
- Body font: Readable paragraphs, UI text (must prioritize legibility)
- Mono font: Code, technical content, tabular data

**Type Scale**

Use a consistent ratio (1.25 recommended for web):

```
base: 16px
sm: 12.8px (base / 1.25)
md: 16px (base)
lg: 20px (base * 1.25)
xl: 25px (base * 1.25²)
2xl: 31.25px (base * 1.25³)
3xl: 39px (base * 1.25⁴)
```

**Line Height Guidelines**

- Headings: 1.1-1.3 (tighter)
- Body text: 1.5-1.7 (comfortable reading)
- UI elements: 1.2-1.4 (compact but readable)

### Logo Usage

**Clear Space**

Define minimum clear space around logo (typically 1x the height of a logo element).

**Minimum Sizes**

Specify minimum display sizes:
- Digital: minimum 24px height
- Print: minimum 0.5 inch height

**Prohibited Uses**

Document what NOT to do:
- Stretching or distorting
- Changing colors outside approved palette
- Adding effects (shadows, outlines)
- Placing on busy backgrounds
- Rotating or tilting

### Spacing System

Use a consistent spacing scale based on a base unit:

```
base: 4px
xs: 4px   (1x)
sm: 8px   (2x)
md: 16px  (4x)
lg: 24px  (6x)
xl: 32px  (8x)
2xl: 48px (12x)
```

## Working with .brand.yaml

The brand configuration file defines all visual identity elements:

```yaml
name: "Brand Name"

colors:
  primary: "#00ff41"
  secondary: "#ffb000"
  accent: "#ff2a6d"
  background: "#0a0a0f"
  surface: "#111118"
  text: "#ffffff"
  text_muted: "#888888"
  success: "#00d26a"
  warning: "#ffb000"
  error: "#ff4757"

typography:
  display: "Press Start 2P"
  body: "Space Mono"
  mono: "Fira Code"
  scale: 1.25
  base_size: 16

spacing:
  base: 4

logo:
  primary: "assets/logo.svg"
  icon: "assets/icon.svg"
  clear_space: "1x height"
  min_size: 24
```

## Auditing Visual Consistency

When auditing a codebase for brand compliance:

1. **Search for hardcoded colors**
   - Look for hex codes not in the palette
   - Check for rgb/rgba values
   - Identify hsl values

2. **Check typography usage**
   - Verify font-family declarations match brand fonts
   - Check font-size values against the type scale
   - Review line-height consistency

3. **Review spacing**
   - Look for arbitrary pixel values
   - Verify margin/padding follows the spacing scale

4. **Examine component patterns**
   - Button styles consistency
   - Form element styling
   - Card/surface treatments

## Multi-Theme Considerations

For applications with multiple themes or skins:

- Define a base set of CSS custom properties
- Each theme overrides only color values
- Typography and spacing remain consistent
- Document theme-specific color mappings

## Accessibility Requirements

All visual choices must meet accessibility standards:

- Color contrast: WCAG AA minimum (4.5:1)
- Focus indicators: Visible on all interactive elements
- Motion: Respect `prefers-reduced-motion`
- Font sizes: Minimum 16px for body text

## Creative Execution with frontend-design

Brand guidelines define **what** to use. For **how** to use them memorably, leverage the **frontend-design** skill.

### The Workflow

1. **Define constraints** (this skill): Colors, fonts, spacing from `.brand.yaml`
2. **Execute creatively** (frontend-design): Build distinctive interfaces within those constraints

### When Building UI Components

After establishing brand guidelines, invoke the frontend-design skill for implementation:

```
"Create a hero section for our landing page using our brand colors and typography"
```

The frontend-design skill will:
- Use your brand palette as the creative foundation
- Apply your typography choices with flair
- Create something memorable while staying on-brand

### Brand + Creativity Balance

| Brand Guidelines Provide | frontend-design Adds |
|-------------------------|---------------------|
| Color palette | Bold color usage, unexpected accents |
| Font families | Creative typography hierarchy, spacing |
| Spacing scale | Spatial composition, asymmetry, overlap |
| Consistency rules | Distinctive execution within rules |

### Key Principle

Brand constraints don't limit creativity - they focus it. The best designs emerge when bold creative vision operates within clear brand parameters.

## Additional Resources

### Reference Files

For detailed guidance, consult:
- **`references/color-theory.md`** - Color harmony, psychology, and selection
- **`references/accessibility.md`** - WCAG guidelines and testing

### Example Files

Working examples in `examples/`:
- **`brand-config-minimal.yaml`** - Minimal brand configuration
- **`brand-config-full.yaml`** - Comprehensive brand configuration

### Related Skills

- **frontend-design** - Creative UI implementation using brand foundations
