---
description: Brainstorm names matching brand attributes
argument-hint: [concept to name]
allowed-tools: Read
---

Generate name suggestions that align with brand attributes and personality.

## Arguments

- `$ARGUMENTS` - Description of what needs a name
  - Could be: product name, feature name, project codename, component name, etc.

## Process

1. **Read brand configuration**
   Load `.brand.yaml` to understand brand attributes, personality, and vocabulary preferences.

2. **Understand naming context**

   Determine what type of name is needed:
   - **Product/Company name**: Needs to be memorable, unique, domain-available
   - **Feature name**: Should describe functionality, fit with existing features
   - **Component/Module name**: Technical clarity important, follows codebase conventions
   - **Marketing term**: Catchy, benefit-focused, target audience appropriate
   - **Codename**: Can be more playful, internal use

3. **Generate names based on brand attributes**

   For each brand attribute, generate name concepts that embody it:
   - If "adventurous": Names evoking exploration, discovery, journey
   - If "friendly": Names that are approachable, warm, inviting
   - If "professional": Names that are clear, trustworthy, established
   - If "innovative": Names suggesting newness, breakthrough, progress

4. **Apply naming strategies**

   Generate names using different approaches:

   **Descriptive**: Names that describe what it does
   - Clear, functional, easy to understand
   - May be less memorable

   **Evocative**: Names that suggest feeling/concept
   - More memorable, emotional connection
   - May need more explanation

   **Invented**: Made-up words
   - Highly unique, ownable
   - Harder to remember initially

   **Compound**: Combining two words
   - Best of both worlds
   - Can be descriptive AND memorable

   **Metaphorical**: Using metaphors
   - Creates mental imagery
   - Connects to familiar concepts

5. **Check against vocabulary**

   - Use preferred words from brand config as inspiration
   - Avoid words from the "avoid" list
   - Ensure names fit brand voice/tone

6. **Present suggestions**

   For each name suggestion, provide:
   - The name
   - Naming strategy used
   - How it connects to brand attributes
   - Potential concerns (too generic, hard to pronounce, etc.)
   - Domain availability tip (if product name)

   Group by confidence level:
   - **Strong candidates**: Best fit for brand, unique, memorable
   - **Alternatives**: Good options with trade-offs
   - **Creative wildcards**: More unusual options to consider

7. **Additional considerations**

   Note relevant factors:
   - Trademark concerns (general guidance only)
   - International considerations
   - Abbreviation potential
   - How it pairs with existing product names

## Example Output

```
Naming suggestions for: "real-time collaboration feature"

Brand attributes considered: generative, adventurous, accessible

STRONG CANDIDATES:

1. "Expedition Mode"
   Strategy: Metaphorical
   Brand fit: Embodies "adventurous", suggests journey together
   Notes: Memorable, unique in market

2. "Gather"
   Strategy: Evocative
   Brand fit: "Accessible", warm, inviting
   Notes: Simple, might conflict with other products

ALTERNATIVES:
...
```
