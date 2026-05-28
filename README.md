# Counsel Skill

Router for thinking and second-opinion workflows.

Counsel is the canonical entry point for the older `grill-me`,
`critical-thinking`, `magi`, and `innovate` workflows. Use `--panel` for the
multi-model council behavior that previously lived in `magi`.

## Modes

- `--interview`: one-question-at-a-time grilling
- `--adversarial`: rigorous critique or premortem
- `--panel`: multi-model council
- `--wildcard`: single highest-leverage novel addition

## Installation

```bash
ln -sfn ~/Developer/Personal/skill-counsel/skills/counsel ~/.claude/skills/counsel
ln -sfn ~/Developer/Personal/skill-counsel/skills/counsel ~/.codex/skills/counsel
```

## Notes

- `--panel` calls Gemini directly and checks `~/.gemini/.env` for
  `GEMINI_API_KEY` when non-interactive auth fails.
- Codex still uses an adapter when available because that transport avoids
  stdin hangs in subagent environments.
