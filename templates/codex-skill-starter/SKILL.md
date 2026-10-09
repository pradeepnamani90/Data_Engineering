---
name: codex-skill-starter
description: "Scaffold for a task-specific Codex skill. Use only when explicitly asked to customize this starter; replace this description with the completed skill's task and trigger conditions before activation."
---

# Codex Skill Starter

Treat bracketed items as authoring placeholders, not execution instructions. Customize them from user-provided or verified sources before activating the skill.

## Workflow

1. Confirm [required inputs], [task scope], and [output contract]. Ask for missing information only when it blocks correct execution.
2. Read [references/context.md](references/context.md) only when the task requires its contracts, approved rules, or exceptions. Read the relevant section; do not preload unrelated material.
3. Execute [ordered task steps]. Preserve [required constraints and decision rules]. Do not invent schemas, mappings, joins, or business logic.
4. Validate [acceptance checks] against [authoritative evidence]. If required evidence is missing or contradictory, identify the affected work and request clarification before proceeding with that part.
5. Return [deliverable and location], a concise validation result, and unresolved assumptions or blockers. Do not claim success for unverified work.
