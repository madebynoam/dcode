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

# Analyze session for reusable patterns
/dcode:mine

# End-of-session reflection
/dcode:reflect
```

## Skills

### dcode:component-detective
**Find UI components from screenshots, route paths, or component names.**

The core designer superpower: "I see this button in the app... where's the code?" Give it a screenshot, and it finds the component. Works with React, Vue, Angular, and other component-based frameworks.

| Input | Output |
|-------|--------|
| Screenshot of a pricing card | `PricingCard` component location, styles, related files |
| `settings/profile` | Files for the profile settings page |
| `DatePicker` | Component definition, usage examples, styles |

**Command:** `/dcode:find <target>`

### dcode:workflow-mining
**Turn productive sessions into reusable skills.**

At the end of a session, this skill analyzes what you did and suggests patterns worth automating. It's how these skills were born—and how you'll create your own.

**Command:** `/dcode:mine`

### dcode:session-reflect
**Capture learnings before they fade.**

A guided reflection for the end of a work session. Surfaces what you learned (technical and soft skills), how you feel, and creates a searchable record of growth over time.

**Command:** `/dcode:reflect [session-name]`

## Installation

### Option 1: Copy to your Claude config

```bash
# Clone the repo
git clone https://github.com/madebynoam/claude-skills-for-designers.git

# Copy skills
cp -r claude-skills-for-designers/skills/* ~/.claude/skills/

# Copy commands
cp -r claude-skills-for-designers/commands/* ~/.claude/commands/
```

### Option 2: Reference directly

Just mention the skill by name in your prompt:
```
"Use dcode:component-detective to find where this screenshot lives"
```

## Repository Structure

```
dcode/
├── skills/
│   ├── component-detective/SKILL.md    # Find components from visuals
│   ├── workflow-mining/SKILL.md        # Surface reusable patterns
│   └── session-reflect/SKILL.md        # Capture learnings
├── commands/
│   ├── dcode:find.md                   # /dcode:find shortcut
│   ├── dcode:mine.md                   # /dcode:mine shortcut
│   └── dcode:reflect.md                # /dcode:reflect shortcut
└── README.md
```

## Philosophy

1. **Reduce fear, increase confidence** — Codebases shouldn't be scary for designers
2. **Screenshot-first** — Visual input is a designer's native language
3. **Progressive disclosure** — Start simple, reveal complexity only when needed
4. **Learning loops** — Reflection builds lasting skills, not just task completion

## Coming Soon

- **dcode:visual-tweak** — Safe CSS changes with preview and easy revert
- **dcode:token-explorer** — Map the design system actually in use
- **dcode:feasibility** — "Can we build this?" analysis before designing
- **dcode:inconsistency** — Audit for design debt across a codebase

## About

Created by [Noam Almosnino](https://noamalmos.com), a designer at Automattic exploring how AI tools can make codebases more accessible to designers.

These skills grew out of real daily work—navigating a large React codebase, making design changes, and reflecting on what worked. They're functional prototypes: code-based artifacts that define agentic workflows.

---

*"At the intersection of code and design"*
