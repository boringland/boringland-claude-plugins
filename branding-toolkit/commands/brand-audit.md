---
description: Run comprehensive brand compliance check
argument-hint: [scope: visual|voice|all]
allowed-tools: Read, Grep, Glob
---

Audit the codebase for brand compliance issues.

## Arguments

- `$1` - Audit scope (optional, defaults to "all")
  - `visual` - Check colors, typography, spacing only
  - `voice` - Check user-facing copy only
  - `all` - Complete brand audit

## Process

1. **Load brand configuration**
   Read `.brand.yaml` from project root. If not found, report that brand config is required.

2. **Visual audit** (if scope is "visual" or "all")

   Search for brand violations in style files:

   **Hardcoded colors:**
   - Search CSS/SCSS files for hex codes not in brand palette
   - Check for rgb/rgba/hsl values
   - Look for color names (red, blue, etc.)
   - Patterns: `#[0-9a-fA-F]{3,8}`, `rgb\(`, `rgba\(`, `hsl\(`

   **Typography issues:**
   - Font-family declarations not using brand fonts
   - Font sizes not matching type scale
   - Line heights outside guidelines

   **Spacing inconsistencies:**
   - Arbitrary pixel values in margin/padding
   - Values not matching spacing scale

   Files to check:
   - `**/*.css`
   - `**/*.scss`
   - `**/*.less`
   - `**/*.styled.{js,ts}`
   - `**/tailwind.config.{js,ts}`

3. **Voice audit** (if scope is "voice" or "all")

   Search for brand voice violations:

   **Avoided words:**
   - Search for words in the "avoid" vocabulary list
   - Check user-facing strings in templates and components

   **Error messages:**
   - Look for generic error messages ("Error", "Invalid", "Failed")
   - Check for technical jargon in user-facing code

   **UI copy patterns:**
   - Generic button labels ("Submit", "Click here", "OK")
   - Passive or weak language

   Files to check:
   - `**/*.{jsx,tsx}` - React components
   - `**/*.{html,erb}` - Templates
   - `**/locales/**/*.{json,yml}` - i18n files
   - `**/*.vue` - Vue components

4. **Generate report**

   Structure findings by severity:

   **Critical** (must fix):
   - Hardcoded brand colors in main stylesheets
   - Wrong fonts in production CSS
   - Error messages with technical jargon

   **Warning** (should fix):
   - Arbitrary spacing values
   - Generic UI copy
   - Avoided vocabulary usage

   **Info** (consider):
   - Minor inconsistencies
   - Suggestions for improvement

   For each issue include:
   - File path and line number
   - What was found
   - Brand guideline being violated
   - Suggested fix

5. **Summary**

   Provide:
   - Total issues by severity
   - Files with most issues
   - Quick wins (easy fixes)
   - Recommended priority order

## Example Output

```
Brand Audit Report
==================

Visual Issues: 12
Voice Issues: 5
Total: 17

CRITICAL (3):
• src/styles/buttons.css:42 - Hardcoded color #ff0000
  → Use var(--color-error) instead

WARNING (8):
• src/components/Error.tsx:15 - Generic error "Something went wrong"
  → Use specific, actionable message per brand voice guidelines
...

Quick Wins:
1. Replace 3 hardcoded colors in buttons.css
2. Update error messages in Error.tsx
```
