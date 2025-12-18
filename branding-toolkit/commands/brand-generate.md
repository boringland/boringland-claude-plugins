---
description: Generate CSS variables, Tailwind config, or design tokens from brand spec
argument-hint: [format: css|tailwind|tokens]
allowed-tools: Read, Write
---

Generate code artifacts from the `.brand.yaml` brand configuration.

## Arguments

- `$1` - Output format (optional, defaults to "css")
  - `css` - CSS custom properties file
  - `tailwind` - Tailwind CSS configuration
  - `tokens` - Design tokens JSON

## Process

1. **Read brand configuration**
   Load `.brand.yaml` from project root. If not found, suggest running `/branding-toolkit:brand-init` first.

2. **Parse brand values**
   Extract:
   - Colors (primary, secondary, accent, background, text, semantic)
   - Typography (fonts, scale ratio, base size)
   - Spacing (base unit, scale)
   - Other values (shadows, radii, breakpoints)

3. **Calculate derived values**
   - Type scale: Generate sizes using the scale ratio (e.g., 1.25)
   - Spacing scale: Generate spacing values from base unit
   - Color variants: Consider light/dark mode if specified

4. **Generate output based on format**

   **CSS (`css` or no argument):**
   - Output: `brand-tokens.css`
   - Include all CSS custom properties
   - Group by category with comments
   - Include both primitive and semantic tokens

   **Tailwind (`tailwind`):**
   - Output: `tailwind.brand.config.js`
   - Extend Tailwind theme with brand values
   - Reference CSS variables for theming support
   - Include colors, fonts, spacing, shadows

   **Tokens (`tokens`):**
   - Output: `brand-tokens.json`
   - Use Design Tokens Community Group format
   - Include type and description metadata
   - Structure for cross-platform use

5. **Report output**
   Confirm file created and location. Suggest how to use the generated file:
   - CSS: Import in main stylesheet
   - Tailwind: Extend in tailwind.config.js
   - Tokens: Use with Style Dictionary or similar tools

## Examples

```
/branding-toolkit:brand-generate           # Generate CSS (default)
/branding-toolkit:brand-generate css       # Generate CSS explicitly
/branding-toolkit:brand-generate tailwind  # Generate Tailwind config
/branding-toolkit:brand-generate tokens    # Generate JSON tokens
```

## Reference

Use the design-tokens skill for generation patterns and naming conventions.
