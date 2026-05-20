---
name: counsel
description: >-
  Route thinking and second-opinion workflows. Use when the user wants to be
  grilled, interviewed, pushed on a plan, get adversarial critique, run a
  premortem, ask other models, compare approaches, or find one radically useful
  addition. This is an additive canonical router over grill-me,
  critical-thinking, magi, and innovate; do not edit or replace those old skills
  yet.
argument-hint: "[--interview|--adversarial|--panel|--wildcard] [question or plan]"
arguments:
  - request
license: MIT
effort: medium
allowed-tools: Bash Read Glob Grep Task Write
---

# Counsel

Pick exactly one mode first. Load only that reference file, then follow its workflow.

This skill is a shadow router. It reduces the future trigger surface, but the old skills remain the known-good implementations.

## Routing

| Intent | Mode | Load |
|---|---|---|
| "grill me", "interview me", "ask me questions", clarify a draft by conversation | `--interview` | [references/interview.md](references/interview.md) |
| "poke holes", "be honest", "what could go wrong", premortem, verdict on reasoning | `--adversarial` | [references/adversarial.md](references/adversarial.md) |
| "ask other models", "magi", "second opinion", compare approaches with external counsel | `--panel` | [references/panel.md](references/panel.md) |
| "innovate", "what am I missing", "single smartest addition", creative frontier push | `--wildcard` | [references/wildcard.md](references/wildcard.md) |

## Boundaries

- Interview mode asks one question at a time; it does not give a verdict.
- Adversarial mode gives a verdict; it does not interview unless a blocking ambiguity prevents analysis.
- Panel mode is for decisions worth external latency; do not use it for trivial questions.
- Wildcard mode is for plans that are already coherent; do not use it to rescue vague requirements.

## Handoffs

- If the user needs a durable PRD, issue, or implementation plan, route to `plan`.
- If repo/product terminology is fuzzy or conflicts with code/docs, route to `domain-model audit`.
- If the user needs findings against a concrete diff, artifact, screenshot, or release candidate, route to `review`.
- If a question uncovers an unexplained failure, route to `diagnose`.

## Output

End with a short mode-specific result:

- `--interview`: resolved decisions and remaining open questions.
- `--adversarial`: verdict, weakest assumptions, and recommended revision.
- `--panel`: synthesis and saved session path when available.
- `--wildcard`: one proposed addition, why it matters, and the smallest next step.
