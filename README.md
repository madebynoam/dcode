# dcode: Claude Skills for Designers

**A toolkit for designers who work in code but don't live there.**

`dcode` = design + code. These skills bridge the gap between "I have Figma" and "I need to ship this."

Most Claude Code skills assume you're a developer. These are different—they're designed for the designer's journey through a codebase: finding components, understanding design systems, making safe visual changes, and prototyping without fear.

## Quick Start

```bash
# Find where a component lives
/dcode:find screenshot.png
/dcode:find "settings/profile"
/dcode:find "UserCard"

# Improve UI copy with proven frameworks
/dcode:uxcopy "Submit"
/dcode:uxcopy -audit              # Interactive walkthrough
/dcode:uxcopy -list               # Show all frameworks

# Analyze session for reusable patterns
/dcode:mine

# End-of-session reflection
/dcode:reflect
```

## Skills

### dcode:find-component
**Find UI components from screenshots, route paths, or component names.**

The core designer superpower: "I see this button in the app... where's the code?" Give it a screenshot, and it finds the component. Works with React, Vue, Angular, and other component-based frameworks.

| Input | Output |
|-------|--------|
| Screenshot of a pricing card | `PricingCard` component location, styles, related files |
| `settings/profile` | Files for the profile settings page |
| `DatePicker` | Component definition, usage examples, styles |

**Command:** `/dcode:find <target>`

### dcode:improve-copy
**Improve UI microcopy using proven UX writing frameworks.**

Turn "Submit" into "Get started." Audit a component for bland buttons, vague errors, and empty states. Apply industry-standard frameworks:

| Framework | Turns this... | Into this... |
|-----------|---------------|--------------|
| **JTBD** | "Submit" | "Get my results" |
| **Benefit-first** | "Enable notifications" | "Never miss updates" |
| **Error patterns** | "Invalid input" | "Email looks wrong. Try name@example.com" |
| **Empty states** | "No results" | "No projects yet. Create one to get started." |
| **Loading states** | "Loading..." | "Finding your files..." |
| **Confirmation** | "Are you sure?" | "This will delete all data. Continue?" |
| **Voice & tone** | — | Formal ↔ casual, serious ↔ playful spectrums |
| **4 C's checklist** | — | Clear, Concise, Conversational, Consistent |

**Interactive audit mode** — Walk through each copy item with choices. Skip, apply, or hit `r` to apply your choice to all remaining items of the same type. Context-aware: auto-detects the file you're working on.

| Mode | Usage |
|------|-------|
| Suggest | `/dcode:uxcopy "Submit"` — Framework-based alternatives |
| Audit | `/dcode:uxcopy -audit` — Interactive walkthrough |
| Batch | `/dcode:uxcopy -audit --batch` — Table view, no prompts |
| Reference | `/dcode:uxcopy -list` — Show all frameworks |

**Command:** `/dcode:uxcopy [text] [-audit] [-list] [--batch]`

### dcode:mine-patterns
**Turn productive sessions into reusable skills.**

At the end of a session, this skill analyzes what you did and suggests patterns worth automating. It's how these skills were born—and how you'll create your own.

**Command:** `/dcode:mine`

### dcode:reflect-session
**Capture learnings before they fade.**

A guided reflection for the end of a work session. Surfaces what you learned (technical and soft skills), how you feel, and creates a searchable record of growth over time.

**Command:** `/dcode:reflect [session-name]`

## Installation

### Option 1: Copy to your Claude config

```bash
# Clone the repo
git clone https://github.com/madebynoam/dcode.git

# Copy skills
cp -r dcode/skills/* ~/.claude/skills/

# Copy commands
cp -r dcode/commands/* ~/.claude/commands/
```

### Option 2: Reference directly

Just mention the skill by name in your prompt:
```
"Use dcode:find-component to find where this screenshot lives"
```

## Repository Structure

```
dcode/
├── skills/
│   ├── find-component/SKILL.md     # Find components from visuals
│   ├── improve-copy/SKILL.md       # Improve UI microcopy
│   ├── mine-patterns/SKILL.md      # Surface reusable patterns
│   └── reflect-session/SKILL.md    # Capture learnings
├── commands/
│   ├── dcode:find.md               # /dcode:find shortcut
│   ├── dcode:uxcopy.md               # /dcode:uxcopy shortcut
│   ├── dcode:mine.md               # /dcode:mine shortcut
│   └── dcode:reflect.md            # /dcode:reflect shortcut
└── README.md
```

## Philosophy

1. **Reduce fear, increase confidence** — Codebases shouldn't be scary for designers
2. **Screenshot-first** — Visual input is a designer's native language
3. **Progressive disclosure** — Start simple, reveal complexity only when needed
4. **Learning loops** — Reflection builds lasting skills, not just task completion

## Coming Soon

- **dcode:tweak-visuals** — Safe CSS changes with preview and easy revert
- **dcode:explore-tokens** — Map the design system actually in use
- **dcode:check-feasibility** — "Can we build this?" analysis before designing
- **dcode:audit-consistency** — Audit for design debt across a codebase

## About

Created by [Noam Almosnino](https://noamalmos.com), design lead at [Automattic](https://automattic.com).

These skills grew out of real daily work—navigating a large React codebase, making design changes, and reflecting on what worked. They're functional prototypes: code-based artifacts that define agentic workflows.

---

*"At the intersection of code and design"*
