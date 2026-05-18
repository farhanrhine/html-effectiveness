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

## Using with Claude Code & Agents

### 1. Add skills to your project

Copy the `HTML-EFFECTIVENESS` folder to one of these locations:

**For Claude Code (project-level):**
```bash
# Option A: Client-specific location
cp -r HTML-EFFECTIVENESS ~/.claude/skills/

# Option B: Cross-client convention (recommended)
mkdir -p .agents/skills
cp -r HTML-EFFECTIVENESS .agents/skills/
```

**For any agent (user-level):**
```bash
# Cross-client (recommended)
cp -r HTML-EFFECTIVENESS ~/.agents/skills/

# Or Claude-specific
cp -r HTML-EFFECTIVENESS ~/.claude/skills/
```

### 2. Agents auto-discover skills

Once skills are placed in `.agents/skills/` or `.claude/skills/`, agents automatically discover them at startup:

**Discovery structure:**
```
.agents/skills/HTML-EFFECTIVENESS/
├── 01-exploration-code-approaches/
│   ├── SKILL.md           ← Agent loads this
│   └── resources/01-...html
├── 02-exploration-visual-designs/
│   ├── SKILL.md           ← Agent loads this
│   └── resources/02-...html
... (21 total skills)
```

**In Claude Code:**
- Open chat
- Select "Agent" mode
- Type `/skills` to see available skills
- Ask about UI patterns, components, etc.
- Skills activate automatically when relevant

### 3. Using individual skills

**Ask Claude Code directly:**
```
"Show me an example of a drag-to-reorder interaction" 
→ Loads 08-prototype-interaction skill

"How do I create a status report template?"
→ Loads 11-status-report skill

"Build a feature flag configuration form"
→ Loads 19-editor-feature-flags skill
```

**Or specify the skill:**
```
/skill 07-prototype-animation
Show me a task completion animation
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

## Getting Started

Start with `.claude/SKILL/HTML-EFFECTIVENESS/index.md` for a quick overview of all 21 skills. Each skill folder contains:
- `SKILL.md` — Problem, approach, and gotchas
- `resources/{skillname}.html` — Working example you can copy from

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
