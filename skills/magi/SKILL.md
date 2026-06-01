---
name: magi
description: Alias for counsel panel mode. Use when the user says "magi",
  "/magi", "ask the other models", "multi-model counsel", "model panel", or
  wants Gemini/Codex/Claude-style external advice. This alias routes to the
  counsel skill's `--panel` workflow and must not depend on the archived
  skill-magi repository.
argument-hint: "[prompt or competing plans]"
arguments:
  - prompt
license: MIT
effort: high
allowed-tools: Bash Read Glob Grep Task Write
---

# Magi Alias

`magi` is preserved user vocabulary for `counsel --panel`.

When this alias fires:

1. Load `../counsel/SKILL.md`.
2. Run the `--panel` route using `../counsel/references/panel.md`.
3. Treat any arguments as the panel prompt.
4. Do not ask the user to install or unarchive `skill-magi`.

If the user passes `--debate`, use the panel reference's debate behavior.
