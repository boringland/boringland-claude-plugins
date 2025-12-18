---
description: Generate brand documentation
allowed-tools: Read, Write
---

Generate comprehensive brand documentation from the `.brand.yaml` configuration.

## Process

1. **Read brand configuration**
   Load `.brand.yaml` from project root. If not found, suggest running `/branding-toolkit:brand-init` first.

2. **Generate documentation**

   Create a `BRAND.md` file in the project root containing:

   **Overview section:**
   - Brand name and tagline
   - Brand attributes/personality
   - Brief brand statement

   **Visual Identity section:**

   *Color Palette:*
   - Primary, secondary, accent colors with hex values
   - Usage guidelines for each color
   - Semantic colors (success, warning, error, info)
   - Background and text colors
   - Accessibility notes (contrast ratios)

   *Typography:*
   - Display and body font families
   - Type scale with all sizes
   - Font weights available
   - Line height guidelines
   - Where to use each font

   *Spacing:*
   - Base unit and scale
   - When to use each spacing size
   - Common patterns

   *Other Visual Elements:*
   - Border radius values
   - Shadow system
   - Animation/motion guidelines (if defined)

   **Brand Voice section:**

   *Tone:*
   - Overall tone description
   - Tone variations by context

   *Vocabulary:*
   - Preferred words and why
   - Words to avoid and why
   - Industry-specific terminology

   *Writing Patterns:*
   - Button/CTA guidelines
   - Error message format
   - Success message format
   - Empty state patterns

   **Usage Examples section:**
   - Color usage examples
   - Typography examples
   - Voice examples (before/after)

   **Quick Reference section:**
   - CSS variable names
   - Tailwind class mapping
   - Common patterns cheatsheet

3. **Format considerations**

   - Use tables for color palettes and scales
   - Include color swatches using emoji or badges: 🟢 🔵 🟡 🔴
   - Group related information
   - Make it scannable with clear headings
   - Include code snippets where helpful

4. **Output**

   Write to `BRAND.md` in project root.

   Also mention:
   - The file can be used for team onboarding
   - Consider adding to project wiki or docs site
   - Keep in sync when updating `.brand.yaml`

## Template Reference

Use the brand-guidelines skill for structure and the brand-voice skill for voice documentation patterns. Reference templates in `${CLAUDE_PLUGIN_ROOT}/templates/` for formatting.
