---
name: 20-editor-prompt-tuner
description: Interactive UI for testing and iterating on LLM system prompts with live preview
---

# Prompt Tuner — LLM Prompt Optimization UI

Build interfaces for crafting and testing LLM prompts, with live feedback and versioning.

## Layout

- **Sticky toolbar** — Mode selector (system / user roles), Copy/Save buttons, hints
- **Main area** — Two-column: prompt editor (left), live output (right)
- **Editor** — Textarea with syntax highlighting for prompt variables
- **Output** — Live preview of LLM response, updated as you type
- **History** — Sidebar showing past versions, timestamps, saved versions

## Editor Features

- **Syntax highlighting** — Highlight variables (${variable}) in one color
- **Line numbers** — Monospace, left-aligned
- **Auto-indent** — Preserve indentation when adding new lines
- **Variable hints** — Show available variables (${user_context}, ${task}, etc.) in autocomplete or sidebar
- **Word count** — Show at bottom ("287 words") so you can optimize for token limits

## Output Preview

- **Live streaming** — If using streaming API, show tokens arriving one-by-one (slower feedback than batch)
- **Token count** — Show token usage (input + output)
- **Response time** — Show latency (e.g., "completed in 0.8s")
- **Error state** — Show API errors, rate limits, validation failures
- **Copy button** — Quick copy output to clipboard

## Toolbar Actions

- **Save version** — Snapshot current prompt with timestamp, optional notes
- **Copy to clipboard** — Copy the full prompt text
- **Test with** — Dropdown to switch test user/context
- **Mode** — Toggle between system prompt, user message, few-shot examples
- **Clear output** — Reset the right pane

## Sidebar Reference

- **Available variables** — List of ${...} variables you can use
- **Version history** — Chronological list of saved prompts
- **Quick templates** — Pre-written prompts for common tasks (e.g., "customer support response")
- **Settings** — Temperature, max tokens, top-p, etc. (LLM hyperparameters)

## Gotchas

- **Variables are contextual** — Not all variables available in all modes. Show "not available" hint if user types ${invalid_var}.
- **Token counting is approximate** — Different tokenizers give different counts. Show "~287 tokens" with the approximation caveat.
- **Rate limiting** — LLM API may throttle requests. Debounce the output preview (300-500ms) so rapid typing doesn't spam the API.
- **Streaming vs batch** — Streaming is faster feedback but harder to debug. Show both modes.
- **Prompt injection** — If testing with user-provided input, warn about prompt injection. Highlight where user input enters the prompt.
- **Cost tracking** — Optionally show API cost per request (useful for expensive models)

## Workflow Example

1. User writes system prompt in editor
2. Types test user message in input field
3. Clicks "Run" → Output preview loads (or streams)
4. User refines prompt based on output
5. Clicks "Save version" → Snapshot saved with timestamp
6. User compares versions side-by-side (or via diff)

## Full Example Tuner

See `resources/20-editor-prompt-tuner.html` for a complete prompt tuner (support reply) with live preview, syntax highlighting, version history, and streaming output.
