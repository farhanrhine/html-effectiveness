# The Unreasonable Effectiveness of HTML

21 reusable UI patterns from Thariq Shihireen's "[HTML Effectiveness](https://x.com/trq212/status/2052809885763747935?s=20)", organized as **Agent Skills** for AI agent auto-discovery (Claude Code, Cursor, GitHub Copilot, etc).

## The Idea

**Thariq's work:** Real, shipping HTML patterns + article on why HTML > Markdown for Claude Code (richer visuals, interactive, shareable, joyful).  
See: https://thariqs.github.io/html-effectiveness/

**This project:** Agent Skills wrapper for auto-discovery. Agents can now ask "Build me a feature flag editor" instead of searching GitHub.

## Installation

### For AI Agents (Claude Code, Cursor, GitHub Copilot, etc.)

**Option 1: Project-level (recommended)**
```bash
cd your-project
mkdir -p .agents/skills
cp -r path/to/html-effectiveness/HTML-EFFECTIVENESS .agents/skills/
```

**Option 2: User-level (all your projects)**
```bash
mkdir -p ~/.agents/skills
cp -r path/to/html-effectiveness/HTML-EFFECTIVENESS ~/.agents/skills/

# Or for Claude specifically
mkdir -p ~/.claude/skills
cp -r path/to/html-effectiveness/HTML-EFFECTIVENESS ~/.claude/skills/
```

### Using with Claude Code

1. Place skills in `.agents/skills/HTML-EFFECTIVENESS/` or `~/.agents/skills/HTML-EFFECTIVENESS/`
2. Open Claude Code and select **Agent** mode
3. Type `/skills` to list all available skills
4. Ask naturally: "Show me a drag-to-reorder interaction" or "Build a status report template"
5. Agent automatically loads relevant skill

### Browsing Skills Locally

```bash
# View the master index
cat .claude/SKILL/HTML-EFFECTIVENESS/index.md

# Open any example in your browser
open .claude/SKILL/HTML-EFFECTIVENESS/07-prototype-animation/resources/07-prototype-animation.html

# Or on Windows
start .claude\SKILL\HTML-EFFECTIVENESS\07-prototype-animation\resources\07-prototype-animation.html
```

## Skills (21 Total)

**Code & Architecture:** 01-exploration-code-approaches · 03-code-review-pr · 04-code-understanding

**Design:** 05-design-system · 06-component-variants · 10-svg-illustrations

**Interactions:** 07-prototype-animation · 08-prototype-interaction · 09-slide-deck

**Docs & Communication:** 11-status-report · 12-incident-report · 16-implementation-plan · 17-pr-writeup

**Research:** 14-research-feature-explainer · 15-research-concept-explainer

**Tools:** 13-flowchart-diagram · 18-editor-triage-board · 19-editor-feature-flags · 20-editor-prompt-tuner

**Portfolio:** index

## How Skills Work

Each skill folder has:
- `SKILL.md` — Problem, gotchas, when to use (progressive disclosure)
- `resources/{skillname}.html` — Working example (copy, adapt, learn)

Metadata loads at startup. Full instructions load when agents decide they're relevant. Examples load on demand.

## Attribution

**Thariq Shihireen** — "[HTML Effectiveness](https://x.com/trq212/status/2052809885763747935?s=20)" concept + 21 patterns  
**This project** — Agent Skills framework + auto-discovery

## License

MIT

---

Created by [@farhanrhine](https://github.com/farhanrhine) · Based on [@trq212](https://x.com/trq212)'s work

