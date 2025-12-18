---
name: Design Tokens
description: This skill should be used when the user asks about "CSS variables", "custom properties", "Tailwind config", "design tokens", "theme generation", "CSS from brand", "generate styles", "token format", or needs to generate code from brand specifications. Provides patterns for generating CSS custom properties, Tailwind configurations, and design token files from brand definitions.
version: 0.1.0
---

# Design Tokens

## Purpose

This skill provides guidance for generating code artifacts from brand specifications. It covers CSS custom properties, Tailwind CSS configurations, and design token formats for use across platforms.

## When to Use

Activate this skill when:

- Generating CSS variables from a brand config
- Creating Tailwind CSS theme configurations
- Outputting design tokens in JSON format
- Converting between token formats
- Setting up theme switching systems

## Core Concepts

### What Are Design Tokens?

Design tokens are the atomic values of a design system:
- Colors (primary, secondary, semantic)
- Typography (font families, sizes, weights)
- Spacing (margins, padding, gaps)
- Other values (shadows, radii, breakpoints)

Tokens are platform-agnostic and can be transformed into any format.

### Token Naming Conventions

Use semantic names that describe purpose, not appearance:

```
✓ --color-primary (purpose)
✗ --color-blue (appearance)

✓ --color-text-muted (purpose)
✗ --color-gray-400 (appearance)

✓ --spacing-md (relative)
✗ --spacing-16 (absolute)
```

### Token Hierarchy

Organize tokens in layers:

1. **Primitive tokens**: Raw values (colors, numbers)
2. **Semantic tokens**: Purpose-based references
3. **Component tokens**: Specific component styles

```css
/* Primitive */
--blue-500: #0066ff;

/* Semantic (references primitive) */
--color-primary: var(--blue-500);

/* Component (references semantic) */
--button-bg: var(--color-primary);
```

## CSS Custom Properties

### Basic Generation

From a `.brand.yaml`, generate CSS:

```css
:root {
  /* Colors */
  --color-primary: #00ff41;
  --color-secondary: #ffb000;
  --color-accent: #ff2a6d;
  --color-background: #0a0a0f;
  --color-surface: #111118;
  --color-text: #ffffff;
  --color-text-muted: #888888;

  /* Semantic colors */
  --color-success: #00d26a;
  --color-warning: #ffb000;
  --color-error: #ff4757;
  --color-info: #3498db;

  /* Typography */
  --font-display: 'Press Start 2P', monospace;
  --font-body: 'Space Mono', monospace;
  --font-mono: 'Fira Code', monospace;

  /* Type scale (1.25 ratio) */
  --text-xs: 0.64rem;
  --text-sm: 0.8rem;
  --text-base: 1rem;
  --text-lg: 1.25rem;
  --text-xl: 1.563rem;
  --text-2xl: 1.953rem;
  --text-3xl: 2.441rem;

  /* Spacing (4px base) */
  --space-xs: 0.25rem;
  --space-sm: 0.5rem;
  --space-md: 1rem;
  --space-lg: 1.5rem;
  --space-xl: 2rem;
  --space-2xl: 3rem;

  /* Border radius */
  --radius-sm: 0.25rem;
  --radius-md: 0.5rem;
  --radius-lg: 1rem;
  --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.3);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.3);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.3);
}
```

### Dark/Light Mode

Use CSS custom properties for theme switching:

```css
:root {
  /* Light mode (default) */
  --color-background: #ffffff;
  --color-text: #1a1a1a;
}

[data-theme="dark"] {
  --color-background: #0a0a0f;
  --color-text: #ffffff;
}

/* Or use media query */
@media (prefers-color-scheme: dark) {
  :root {
    --color-background: #0a0a0f;
    --color-text: #ffffff;
  }
}
```

### Multiple Themes/Skins

For applications with multiple visual themes:

```css
/* Base structure (shared) */
:root {
  --font-display: 'Press Start 2P';
  --space-md: 1rem;
}

/* Theme: Arcade */
[data-skin="arcade"] {
  --color-primary: #00ff41;
  --color-background: #0a0a0f;
  --font-display: 'Press Start 2P';
}

/* Theme: Explorer */
[data-skin="explorer"] {
  --color-primary: #8b4513;
  --color-background: #f4e4c8;
  --font-display: 'Cinzel';
}

/* Theme: Grimoire */
[data-skin="grimoire"] {
  --color-primary: #d4af37;
  --color-background: #12101a;
  --font-display: 'Cinzel Decorative';
}
```

## Tailwind CSS Configuration

### Theme Extension

Generate a `tailwind.config.js` theme from brand:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#00ff41',
        secondary: '#ffb000',
        accent: '#ff2a6d',
        background: '#0a0a0f',
        surface: '#111118',
        success: '#00d26a',
        warning: '#ffb000',
        error: '#ff4757',
        info: '#3498db',
      },
      fontFamily: {
        display: ['"Press Start 2P"', 'monospace'],
        body: ['"Space Mono"', 'monospace'],
        mono: ['"Fira Code"', 'monospace'],
      },
      fontSize: {
        'xs': ['0.64rem', { lineHeight: '1.2' }],
        'sm': ['0.8rem', { lineHeight: '1.4' }],
        'base': ['1rem', { lineHeight: '1.5' }],
        'lg': ['1.25rem', { lineHeight: '1.4' }],
        'xl': ['1.563rem', { lineHeight: '1.3' }],
        '2xl': ['1.953rem', { lineHeight: '1.2' }],
        '3xl': ['2.441rem', { lineHeight: '1.1' }],
      },
      spacing: {
        'xs': '0.25rem',
        'sm': '0.5rem',
        'md': '1rem',
        'lg': '1.5rem',
        'xl': '2rem',
        '2xl': '3rem',
      },
      borderRadius: {
        'sm': '0.25rem',
        'md': '0.5rem',
        'lg': '1rem',
      },
      boxShadow: {
        'sm': '0 1px 2px rgba(0, 0, 0, 0.3)',
        'md': '0 4px 6px rgba(0, 0, 0, 0.3)',
        'lg': '0 10px 15px rgba(0, 0, 0, 0.3)',
      },
    },
  },
}
```

### Using CSS Variables in Tailwind

Reference CSS variables for dynamic theming:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: 'var(--color-primary)',
        secondary: 'var(--color-secondary)',
        background: 'var(--color-background)',
        text: 'var(--color-text)',
      },
    },
  },
}
```

## Design Token JSON Format

### Style Dictionary Format

For cross-platform token management:

```json
{
  "color": {
    "primary": {
      "value": "#00ff41",
      "type": "color",
      "description": "Primary brand color for CTAs and links"
    },
    "secondary": {
      "value": "#ffb000",
      "type": "color"
    },
    "background": {
      "value": "#0a0a0f",
      "type": "color"
    }
  },
  "typography": {
    "fontFamily": {
      "display": {
        "value": "'Press Start 2P', monospace",
        "type": "fontFamily"
      },
      "body": {
        "value": "'Space Mono', monospace",
        "type": "fontFamily"
      }
    },
    "fontSize": {
      "base": {
        "value": "16",
        "type": "dimension",
        "unit": "px"
      }
    }
  },
  "spacing": {
    "md": {
      "value": "16",
      "type": "dimension",
      "unit": "px"
    }
  }
}
```

### Figma Tokens Format

For Figma plugin compatibility:

```json
{
  "global": {
    "colors": {
      "primary": {
        "value": "#00ff41",
        "type": "color"
      },
      "secondary": {
        "value": "#ffb000",
        "type": "color"
      }
    },
    "fontFamilies": {
      "display": {
        "value": "Press Start 2P",
        "type": "fontFamilies"
      }
    }
  }
}
```

## Generation Process

### From .brand.yaml to CSS

1. Read `.brand.yaml` configuration
2. Parse color, typography, spacing values
3. Generate CSS custom properties
4. Calculate derived values (type scale, spacing scale)
5. Output to `brand-tokens.css`

### From .brand.yaml to Tailwind

1. Read `.brand.yaml` configuration
2. Map brand values to Tailwind theme structure
3. Generate `tailwind.config.js` or `tailwind.config.ts`
4. Include CSS variable references for theming

### From .brand.yaml to JSON Tokens

1. Read `.brand.yaml` configuration
2. Transform to target format (Style Dictionary, Figma, etc.)
3. Add metadata (type, description)
4. Output to `tokens.json`

## Type Scale Calculation

Given a base size and ratio, calculate the scale:

```
ratio = 1.25 (major third)
base = 16px

xs:  16 / 1.25² = 10.24px
sm:  16 / 1.25  = 12.8px
base: 16px
lg:  16 * 1.25  = 20px
xl:  16 * 1.25² = 25px
2xl: 16 * 1.25³ = 31.25px
3xl: 16 * 1.25⁴ = 39.06px
```

Common ratios:
- 1.125 (major second) - subtle
- 1.200 (minor third) - moderate
- 1.250 (major third) - recommended
- 1.333 (perfect fourth) - dramatic
- 1.500 (perfect fifth) - very dramatic

## Using Tokens with frontend-design

Generated design tokens provide the foundation for creative UI development. When building interfaces:

### The Workflow

1. **Generate tokens** (this skill): Create CSS variables or Tailwind config from `.brand.yaml`
2. **Build UI** (frontend-design): Create distinctive interfaces using those tokens

### Providing Context to frontend-design

When invoking frontend-design for UI work, reference your tokens:

```
"Create a pricing page. Use our brand tokens from brand-tokens.css -
the primary color is a phosphor green, we have a dark background theme,
and Press Start 2P for display text."
```

### Token Usage in Creative Design

| Token Type | frontend-design Uses It For |
|------------|---------------------------|
| `--color-primary` | Bold accents, CTAs, brand moments |
| `--color-accent` | Attention highlights, hover effects |
| `--font-display` | Hero text, dramatic headlines |
| `--space-*` | Spatial rhythm, layout grid |

### Key Principle

Tokens are the vocabulary. frontend-design writes poetry with them. The tokens ensure consistency while frontend-design ensures memorability.

## Additional Resources

### Reference Files

For detailed patterns, consult:
- **`references/tailwind-patterns.md`** - Advanced Tailwind configurations
- **`references/token-formats.md`** - All supported token formats

### Example Files

Working examples in `examples/`:
- **`brand-tokens.css`** - Generated CSS custom properties
- **`tailwind.config.js`** - Generated Tailwind config
- **`tokens.json`** - Design token JSON output

### Related Skills

- **frontend-design** - Creative UI implementation using generated tokens
- **brand-guidelines** - Defining the brand foundation that tokens express
