---
name: 19-editor-feature-flags
description: Form-based UI for managing feature flags with validation, warnings, and save/discard
---

# Feature Flags Editor — Configuration UI

Build UIs for controlling feature flags, configuration, and runtime settings.

## Layout

- **Header** — Filename (e.g., `flags.production.json`)
- **Warning banner** (if showing) — Clay color, show when unsaved changes exist
- **Main form** — Groups of flag configurations
- **Sidebar** (sticky) — Quick reference, flag definitions, validation status
- **Toolbar** — Save, Discard, Reset buttons

## Components

### Flag Group
```
┌─ Group name ──────────────┐
│ ┌─ Flag 1 ───────────┐    │
│ │ Name: "feature-x"  │    │
│ │ Enabled: [toggle]  │    │
│ │ Value: [text]      │    │
│ └────────────────────┘    │
│ ┌─ Flag 2 ───────────┐    │
│ │ ...                │    │
│ └────────────────────┘    │
└────────────────────────────┘
```

- **Group header** — Group name (mono), collapsed/expanded toggle
- **Flag card** — White bg, 1.5px gray border, padding 20px
- **Field types** — Toggle (for booleans), text input, select (enums), number input
- **Validation** — Shows error inline if value is invalid (e.g., "must be integer")

### Toolbar
- **Save** — Writes changes, shows success toast
- **Discard** — Revert to last saved state, ask for confirmation if changes exist
- **Reset** — Revert to default/production state
- **Validation status** — Shows "✓ Valid" or "⚠ Invalid" with error count

### Sidebar
- **Group definitions** — List of flag names and their types
- **Validation errors** — Live list of issues preventing save
- **Production values** — Compare current vs production (show diff)

## Gotchas

- **Unsaved changes detection** — Track dirty state. Show banner/modal before nav away if unsaved.
- **Type validation** — Catch type errors before sending (e.g., "must be a number"). Monospace error text.
- **Read-only fields** — Some flags may be immutable in production. Mark with padlock icon, disable editing.
- **Rollback safety** — Require confirmation before deploying flags to production. Show "deploy to production?" modal with change summary.
- **Nested objects** — If flags have structure (e.g., `{ rollout: { percent: 50 } }`), use nested form groups or JSON editor
- **Syntax highlighting** — If editing raw JSON, use syntax highlighting (not just monospace)

## Example Values

```json
{
  "comments-on-cards": {
    "enabled": true,
    "rollout-percent": 100,
    "beta-users-only": false
  },
  "notifications-queue": {
    "enabled": true,
    "batch-size": 50,
    "timeout-ms": 5000
  }
}
```

## Full Example Editor

See `resources/19-editor-feature-flags.html` for a complete flags editor with grouped flags, validation, unsaved-changes banner, and save/discard toolbar.
