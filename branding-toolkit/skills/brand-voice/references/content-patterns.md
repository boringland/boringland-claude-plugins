# Content Patterns by Context

## Navigation

### Menu Items

- Use nouns or short noun phrases
- Be consistent (all verbs OR all nouns)
- Order by importance/frequency

```
✓ Dashboard, Adventures, Settings
✓ Create, Explore, Manage

✗ Home Page, Your Adventures List, Setting Options
✗ Go to Dashboard, Adventures, Settings (mixed)
```

### Breadcrumbs

- Show hierarchy clearly
- Use same terms as page titles
- Keep each segment short

```
✓ Adventures > The Lost Temple > Characters
✗ Back to Adventures List > Adventure: The Lost Temple > Character Management
```

## Forms

### Labels

- Be specific and descriptive
- Avoid ending with colons
- Sentence case

```
✓ Adventure name
✓ Character description
✓ Email address

✗ Name:
✗ Enter Your Character's Description Here
✗ EMAIL
```

### Placeholders

- Show format when relevant
- Don't repeat the label
- Make them deletable (not instructions)

```
✓ the-lost-temple
✓ A brave explorer seeking ancient treasures...
✓ you@example.com

✗ Enter name here
✗ Type description
✗ Your email
```

### Helper Text

- Explain requirements or provide examples
- Keep under one line
- Place below input

```
✓ URL-friendly name using letters, numbers, and dashes
✓ Visible to other players in dialogue
✓ We'll send a confirmation link

✗ This field is required
✗ Please enter a valid value
✗ Must be unique
```

### Validation Messages

Structure: What's wrong + How to fix

```
✓ Name must be at least 3 characters
✓ This email is already registered. Sign in instead?
✓ Passwords must include a number

✗ Invalid
✗ Error
✗ Please enter a valid name
```

## Dialogs and Modals

### Titles

- State purpose or question
- Use sentence case
- Keep short

```
✓ Delete this adventure?
✓ Unsaved changes
✓ Create new character

✗ Confirmation Required
✗ Are You Sure You Want to Delete?
✗ Warning!
```

### Body Text

- Explain consequences
- Be specific about what will happen
- Keep to 1-2 sentences

```
✓ This will permanently delete "The Lost Temple" and all its scenes. This can't be undone.

✗ Are you sure you want to delete this item? This action cannot be reversed and all associated data will be permanently removed from our servers.
```

### Button Labels

- Primary: Specific action verb
- Secondary: "Cancel" or alternative action
- Destructive: Repeat the action ("Delete" not "OK")

```
✓ Delete adventure / Keep it
✓ Save changes / Discard
✓ Create character / Cancel

✗ OK / Cancel
✗ Yes / No
✗ Confirm / Back
```

## Notifications

### Toast Messages

- Keep under 10 words
- No title needed for simple confirmations
- Include action when relevant

```
✓ Adventure saved
✓ Character added to scene
✓ Couldn't connect. Retry

✗ Your adventure has been successfully saved to the database
✗ Success!
✗ The operation completed
```

### System Notifications

- Clear subject line
- Specific details
- Action if needed

```
✓ "Your adventure is ready"
   "The Lost Temple" has finished generating. Play now →

✗ "Notification"
   Process complete. Click here.
```

## Status Indicators

### Progress

- Say what's happening
- Update meaningfully
- Show completion

```
✓ Generating world... (2 of 5 scenes)
✓ Saving changes...
✓ Ready!

✗ Loading...
✗ Please wait
✗ 40%
```

### States

- Badge labels: 1-2 words
- Tooltip: fuller explanation

```
Badge: Draft
Tooltip: Not yet visible to others

Badge: Live
Tooltip: Published and playable

Badge: Processing
Tooltip: Your adventure is being generated
```

## Tables

### Column Headers

- Short, scannable
- Sentence case
- Consistent formatting

```
✓ Name | Created | Status | Actions
✗ Adventure Name | Date Created | Current Status | Available Actions
```

### Empty Rows

- Explain what would be here
- Provide action

```
✓ No characters yet. Add your first character →
✗ No data available
```

## Help and Documentation

### Titles

- Task-focused
- Start with verb or "How to"

```
✓ Create your first adventure
✓ How to add characters
✓ Understanding scenes

✗ Adventure Creation Documentation
✗ Character Management Guide
✗ About Scenes
```

### Instructions

- Numbered for sequences
- Bulleted for options
- Active voice

```
1. Open the adventure editor
2. Click "Add character"
3. Enter a name and description
4. Save your changes

Not:
1. The adventure editor should be opened
2. The "Add character" button can be clicked
3. A name and description are to be entered
4. Changes must be saved
```

## Marketing Copy

### Headlines

- Lead with benefit
- Create curiosity
- Use power words

```
✓ Bring your stories to life
✓ Create worlds with words
✓ Adventures start with imagination

✗ AI-Powered Game Generation
✗ Welcome to Our Platform
✗ Get Started Today
```

### Feature Descriptions

- Benefit first, then feature
- Specific, not vague
- Show, don't tell

```
✓ Describe your world in plain language. Our AI builds playable adventures from your imagination.

✗ Our advanced AI technology uses natural language processing to generate interactive game experiences.
```

### CTAs

- Action verb + benefit
- Create urgency when appropriate
- Match the context

```
✓ Start creating free
✓ See how it works
✓ Create your first adventure

✗ Sign up
✗ Learn more
✗ Get started
```
