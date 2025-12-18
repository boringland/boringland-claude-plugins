# Branding Toolkit

A Claude Code plugin for comprehensive brand management in web applications. Covers visual identity, brand voice, naming, and compliance auditing.

## Features

- **Visual Identity Management** - Colors, typography, spacing, logos
- **Brand Voice Guidelines** - Tone, vocabulary, messaging patterns
- **Code Generation** - CSS variables, Tailwind configs, design tokens
- **Compliance Auditing** - Proactive checks for brand drift
- **Naming Assistance** - Brainstorm names that fit your brand

## Installation

```bash
claude --plugin-dir /path/to/branding-toolkit
```

Or add to your project's `.claude/plugins/` directory.

## Setup

1. Run `/branding-toolkit:brand-init` to create your `.brand.yaml` configuration
2. Define your brand's visual identity, voice, and attributes
3. Use `/branding-toolkit:brand-generate` to create CSS/Tailwind configs

## Commands

| Command | Description |
|---------|-------------|
| `/branding-toolkit:brand-init` | Create a `.brand.yaml` config with guided setup |
| `/branding-toolkit:brand-generate [format]` | Generate CSS variables, Tailwind config, or design tokens |
| `/branding-toolkit:brand-audit [scope]` | Run comprehensive brand compliance check |
| `/branding-toolkit:brand-docs` | Generate brand documentation |
| `/branding-toolkit:brand-name [concept]` | Brainstorm names matching brand attributes |

## Brand Configuration

The plugin uses a `.brand.yaml` file at your project root:

```yaml
name: "Your Brand"
tagline: "Your tagline here"

attributes:
  - generative
  - adventurous
  - accessible

colors:
  primary: "#00ff41"
  secondary: "#ffb000"
  accent: "#ff2a6d"
  background: "#0a0a0f"
  text: "#ffffff"

typography:
  display: "Press Start 2P"
  body: "Space Mono"
  scale: 1.25

voice:
  tone: "friendly, enthusiastic, clear"
  vocabulary:
    prefer: ["create", "adventure", "discover"]
    avoid: ["simple", "just", "obviously"]
```

## Skills

The plugin provides knowledge about:

- **brand-guidelines** - Visual identity best practices
- **brand-voice** - Tone and messaging patterns
- **design-tokens** - Code generation patterns

## Agents

- **brand-auditor** - Proactively checks for brand compliance when you write CSS or user-facing copy
- **brand-generator** - Generates brand-compliant code and copy on request

## Templates

Generate documentation from templates:

- Style guide
- Voice guide
- Color palette with accessibility info

## Integration with frontend-design

This plugin works alongside the **frontend-design** plugin for a complete design workflow:

| Plugin | Role | Focus |
|--------|------|-------|
| **branding-toolkit** | Defines constraints | "What colors, fonts, and voice to use" |
| **frontend-design** | Creative execution | "How to use them memorably" |

### Recommended Workflow

1. **Set up brand** - Run `/branding-toolkit:brand-init` to define your brand
2. **Generate tokens** - Run `/branding-toolkit:brand-generate css` for CSS variables
3. **Build UI** - Use frontend-design skill for creative, distinctive interfaces
4. **Verify compliance** - brand-auditor checks your work stays on-brand

### Example Usage

```
"Create a hero section for my landing page. I have a dark arcade theme
with phosphor green (#00ff41) as primary, Press Start 2P for headlines,
and Space Mono for body text."
```

The frontend-design skill will create something bold and memorable while using your brand foundations.

### Key Principle

Brand constraints don't limit creativity - they focus it. The best designs emerge when bold creative vision operates within clear brand parameters.
