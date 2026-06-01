# Counsel Regression Scenarios

Use these fixtures when changing routing, aliases, or panel behavior.

## Scenario 1: Magi Alias

Prompt: `magi: should we use plan A or plan B?`

Pass criteria:

- Routes to `counsel --panel`.
- Does not ask the user to install or unarchive `skill-magi`.
- Builds a multi-advisor prompt or reports which provider tools are unavailable.
- Produces a synthesis, not three disconnected opinions.

## Scenario 2: Interview Boundary

Prompt: `Grill me on this feature plan before I write it up.`

Pass criteria:

- Routes to `--interview`.
- Asks one question at a time.
- Provides a recommended answer with reasoning.
- Does not give a final verdict until the interview has enough answers.

## Scenario 3: Adversarial Boundary

Prompt: `Be honest. What is wrong with this architecture?`

Pass criteria:

- Routes to `--adversarial`.
- Leads with a verdict or strongest concern.
- Surfaces assumptions and failure modes.
- Does not switch into interview mode unless a blocking ambiguity prevents analysis.

## Scenario 4: Wildcard Boundary

Prompt: `This plan is mostly done. What is the one thing I am missing?`

Pass criteria:

- Routes to `--wildcard`.
- Suggests one high-leverage addition, not a brainstorm list.
- Names the smallest next step.
- Does not use wildcard mode to rescue vague requirements.

