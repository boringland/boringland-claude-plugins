---
name: Brand Voice
description: This skill should be used when the user asks about "brand voice", "tone of voice", "copy guidelines", "messaging", "user-facing text", "error messages style", "UI copy", "writing style", "brand personality", or needs guidance on maintaining consistent brand communication. Provides comprehensive guidance for defining and maintaining brand voice across all user-facing content.
version: 0.1.0
---

# Brand Voice

## Purpose

This skill provides guidance for defining, documenting, and maintaining consistent brand voice across all user-facing content in web applications. It covers tone, vocabulary, messaging patterns, and content guidelines.

## When to Use

Activate this skill when working on:

- Defining brand tone and personality
- Writing UI copy (buttons, labels, messages)
- Crafting error messages and notifications
- Creating onboarding flows
- Reviewing content for brand consistency
- Establishing vocabulary guidelines

## Core Concepts

### Voice vs. Tone

**Voice** is the consistent personality of the brand. It doesn't change.
- "We're always friendly and helpful"
- "We speak plainly, not technically"

**Tone** adapts to context while maintaining voice.
- Celebratory when user succeeds
- Empathetic when something goes wrong
- Encouraging during onboarding

### Voice Attributes

Define 3-5 attributes that characterize the brand personality:

| Attribute | What it means | What it doesn't mean |
|-----------|---------------|---------------------|
| Friendly | Warm, approachable, conversational | Unprofessional, overly casual |
| Clear | Direct, jargon-free, scannable | Dumbed down, patronizing |
| Enthusiastic | Excited about features, positive | Over-the-top, fake excitement |
| Helpful | Guides user, anticipates needs | Pushy, hand-holding |

### Tone Spectrum

Map tone variations to contexts:

```
Serious ←————————————————→ Playful

Error messages:  |--●--------|  (more serious)
Success states:  |--------●--|  (more playful)
Onboarding:      |------●----|  (balanced, encouraging)
Settings:        |---●-------|  (neutral, clear)
Marketing:       |---------●-|  (most playful)
```

## Vocabulary Guidelines

### Preferred Words

Create a list of words that embody the brand:

```yaml
prefer:
  - create (not "make" or "build")
  - discover (not "find")
  - adventure (not "game" or "experience")
  - explore (not "browse" or "look at")
```

### Words to Avoid

Document problematic words and why:

| Avoid | Why | Use Instead |
|-------|-----|-------------|
| simple | Subjective, can feel dismissive | straightforward, quick |
| just | Minimizes effort, can frustrate | (remove, or rephrase) |
| obviously | Assumes knowledge, can alienate | (explain instead) |
| easy | Sets expectations that may disappoint | takes about X minutes |
| please | Often unnecessary, can feel weak | (direct statements) |

### Technical Terms

Decide how to handle technical concepts:

- **Use plain language**: "save" not "persist", "connect" not "authenticate"
- **Define when necessary**: First use gets explanation, then abbreviate
- **Create a glossary**: Consistent terms for product-specific concepts

## Writing Patterns

### Buttons and CTAs

```
✓ Create adventure
✓ Start exploring
✓ Save changes

✗ Submit
✗ Click here
✗ Process
```

Guidelines:
- Start with action verbs
- Be specific about outcome
- Keep under 3 words when possible

### Error Messages

Structure: **What happened** + **Why** (if helpful) + **What to do**

```
✓ "Couldn't save your changes. Check your connection and try again."
✓ "This name is already taken. Try a different one."

✗ "Error 500"
✗ "Invalid input"
✗ "Something went wrong"
```

Guidelines:
- Never blame the user
- Avoid technical jargon
- Provide actionable next steps
- Use active voice

### Success Messages

```
✓ "Adventure created! Start adding scenes."
✓ "Changes saved"
✓ "You're all set!"

✗ "Success!"
✗ "Operation completed successfully"
✗ "Your request has been processed"
```

Guidelines:
- Celebrate appropriately (don't over-praise routine actions)
- Suggest next steps when relevant
- Keep brief

### Empty States

```
✓ "No adventures yet. Create your first one to get started."
✓ "Your inventory is empty. Pick up items as you explore."

✗ "No data"
✗ "Nothing here"
✗ "0 results"
```

Guidelines:
- Explain what would normally be here
- Provide clear path to populate
- Use illustrations when appropriate

### Onboarding

```
✓ "Let's create your first adventure"
✓ "What kind of world do you want to explore?"
✓ "Great choice! Now let's add some characters."

✗ "Step 1 of 5"
✗ "Please complete the following fields"
✗ "Required"
```

Guidelines:
- Use conversational prompts
- Show progress encouragingly
- Celebrate small wins
- Allow skipping when possible

## Content Patterns

### Headlines

- Lead with benefit, not feature
- Use active voice
- Create curiosity or urgency when appropriate

```
✓ "Bring your stories to life"
✓ "Create worlds with words"

✗ "Text-to-game generation platform"
✗ "Welcome to our application"
```

### Microcopy

Form labels, tooltips, placeholders:

```
Label: "Adventure name"
Placeholder: "The Lost Temple of..."
Helper: "This appears in your adventure list"

Not:
Label: "Name:"
Placeholder: "Enter name"
Helper: "Required field"
```

### Loading States

```
✓ "Creating your world..."
✓ "Generating scenes..."
✓ "Almost there..."

✗ "Loading..."
✗ "Please wait"
✗ "Processing"
```

## Voice in .brand.yaml

```yaml
voice:
  # Core personality
  tone: "friendly, enthusiastic, clear"
  personality: "helpful guide, creative partner"

  # Voice attributes
  attributes:
    - friendly: "Warm and approachable, never cold or corporate"
    - clear: "Plain language, no jargon, get to the point"
    - enthusiastic: "Genuinely excited about creation"
    - helpful: "Anticipates needs, guides without hand-holding"

  # Vocabulary
  vocabulary:
    prefer:
      - create
      - discover
      - adventure
      - explore
      - imagine
      - world
    avoid:
      - simple
      - just
      - obviously
      - easy
      - please
      - sorry (unless genuine apology)

  # Tone by context
  contexts:
    errors: "empathetic, solution-focused"
    success: "celebratory but not over-the-top"
    onboarding: "encouraging, guiding"
    settings: "clear, neutral"
```

## Auditing Voice Consistency

When reviewing content for brand voice:

1. **Check vocabulary**: Search for avoided words
2. **Review error messages**: Ensure helpful, not technical
3. **Examine CTAs**: Verify action-oriented language
4. **Test empty states**: Confirm helpful guidance
5. **Read aloud**: Does it sound like the brand?

## Additional Resources

### Reference Files

For detailed guidance, consult:
- **`references/content-patterns.md`** - Detailed patterns for all UI contexts
- **`references/examples.md`** - Before/after rewrites

### Example Files

Working examples in `examples/`:
- **`voice-guide-template.md`** - Template for voice documentation
