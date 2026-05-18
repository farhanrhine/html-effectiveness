# The Unreasonable Effectiveness of HTML

A curated collection of 21 reusable UI patterns, components, and documentation templates. Each skill demonstrates a complete, production-ready pattern with working examples, gotchas, and best practices.

## Quick Start

### For Agents/Tools

Skills are organized in `.claude/SKILL/HTML-EFFECTIVENESS/` following the [Agent Skills spec](https://agentskills.io/):

1. **Discover skills** → Read `.claude/SKILL/HTML-EFFECTIVENESS/index.md` (51 lines)
2. **Load skill details** → Read individual `SKILL.md` files (~50-60 lines each)
3. **See working example** → View `resources/{skillname}.html` (full interactive example)

**Progressive disclosure:** Agents load metadata first, then skill instructions, then examples on demand.

### For Humans

```bash
# Clone the repo
git clone https://github.com/farhanrhine/html-effectiveness.git
cd html-effectiveness

# View index
cat .claude/SKILL/HTML-EFFECTIVENESS/index.md

# Open any skill in browser
open .claude/SKILL/HTML-EFFECTIVENESS/01-exploration-code-approaches/resources/01-exploration-code-approaches.html
```

## Skills by Category

### Code & Architecture
- **01-exploration-code-approaches** — Debounced search: inline useEffect vs custom hook vs library
- **03-code-review-pr** — Risk-mapped PR review format with color-coded severity
- **04-code-understanding** — Authentication flow walkthrough (5-layer call stack)

### Design & Components
- **05-design-system** — Canonical token reference (colors, typography, spacing, radius, shadows)
- **06-component-variants** — Card component: 6 structural treatments (Flat, Outlined, Elevated, etc.)
- **10-svg-illustrations** — Geometric spot illustrations with design consistency

### Interactions & Animations
- **07-prototype-animation** — Task completion animation (900ms sequence with easing curves)
- **08-prototype-interaction** — Sidebar drag-to-reorder with visual feedback
- **09-slide-deck** — Full-screen presentations with scroll-snap and dark mode

### Documentation & Communication
- **11-status-report** — Weekly engineering update with stat cards
- **12-incident-report** — Blameless RCA post-mortem format
- **16-implementation-plan** — Feature design doc with phased approach
- **17-pr-writeup** — Detailed PR description template

### Research & Education
- **14-research-feature-explainer** — Sticky TOC educational content (rate limiting example)
- **15-research-concept-explainer** — Interactive SVG demo (consistent hashing example)

### Tools & Workflow
- **13-flowchart-diagram** — SVG flowchart with clickable nodes
- **18-editor-triage-board** — Issue triage UI with filters and bulk actions
- **19-editor-feature-flags** — Feature flag configuration form
- **20-editor-prompt-tuner** — LLM prompt optimization with live preview

### Portfolio
- **index** — Portfolio landing page with projects and categories

## Project Structure

```
.
├── README.md                          # This file
├── .claude/
│   └── SKILL/
│       └── HTML-EFFECTIVENESS/
│           ├── index.md               # Master index (quick lookup)
│           ├── 01-exploration-code-approaches/
│           │   ├── SKILL.md           # Skill metadata + instructions
│           │   └── resources/
│           │       └── 01-...html     # Working example
│           ├── 02-exploration-visual-designs/
│           │   ├── SKILL.md
│           │   └── resources/02-...html
│           ... (21 total skills)
│           └── index/
│               ├── SKILL.md
│               └── resources/index.html
```

## Key Features

✅ **Agent Skills compliant** — Follows official spec with YAML frontmatter and progressive disclosure  
✅ **Working examples** — Every skill has a complete, interactive HTML file  
✅ **Production-ready** — Real patterns from shipping products  
✅ **Gotchas first** — Edge cases and tradeoffs documented upfront  
✅ **Short & focused** — SKILL.md files stay \<500 lines, examples load on demand  
✅ **Discoverable** — Master index helps agents/humans find the right skill quickly  

## Using a Skill

### Step 1: Load the index
```
.claude/SKILL/HTML-EFFECTIVENESS/index.md
```

### Step 2: Find your pattern
Scan the table or categories to find a relevant skill.

### Step 3: Read the SKILL.md
```
.claude/SKILL/HTML-EFFECTIVENESS/{skillname}/SKILL.md
```

Contains:
- **What** — What problem does this solve?
- **Gotchas** — Non-obvious issues and edge cases
- **When to use** — Decision framework
- **Reference** — Link to full working example

### Step 4: View the example (if needed)
```
.claude/SKILL/HTML-EFFECTIVENESS/{skillname}/resources/{skillname}.html
```

Complete, working implementation you can:
- Copy code from
- Adapt for your use case
- Run in a browser

## Design Principles

1. **Show, don't tell** — Every pattern has a working example
2. **Gotchas first** — Surprises and edge cases upfront
3. **Progressive disclosure** — Metadata first, details on demand
4. **One pattern per skill** — Focused, not bloated
5. **Production patterns** — Real code from shipping products

## How to Contribute

1. Add a new skill folder with the same structure
2. Write a focused `SKILL.md` (\<500 lines)
3. Include a working `resources/{skillname}.html` example
4. Update `.claude/SKILL/HTML-EFFECTIVENESS/index.md`
5. Push to main

## Spec & Standards

- **Agent Skills spec** — https://agentskills.io/
- **SKILL.md format** — YAML frontmatter + Markdown body
- **Progressive disclosure** — Metadata ~100 tokens, instructions \<5000 tokens, resources on demand
- **File structure** — `skillname/SKILL.md` + `skillname/resources/`

## Inspiration & Attribution

This project is inspired by:
- **[Thariq Shihireen's "HTML Effectiveness" concept](https://x.com/trq212/status/2052809885763747935?s=20)** — The original idea for curating effective HTML patterns
- **[ThariqS/html-effectiveness repository](https://github.com/ThariqS/html-effectiveness.git)** — Reference implementation and pattern examples

This version applies the Agent Skills framework to make patterns discoverable and usable by both humans and AI agents.

## License

MIT — Use these patterns freely in your projects.

## Author

Created by [@farhanrhine](https://github.com/farhanrhine)  
Based on work by [@trq212](https://x.com/trq212)

---

**Last updated:** May 18, 2026  
**Total skills:** 21  
**Total resources:** 21 working HTML examples
