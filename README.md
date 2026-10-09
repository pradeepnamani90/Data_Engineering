# Data Engineering Codex Skills

Minimal starter for reusable Codex skills. No project schemas, mappings, or business rules are supplied or assumed. Customize the template before using it for real work.

## Files

| Path | Purpose |
| --- | --- |
| `templates/codex-skill-starter/SKILL.md` | Concise skill template with required YAML metadata and core workflow. |
| `templates/codex-skill-starter/references/context.md` | Optional template for verified execution context, read only when relevant. |

The template lives outside `.agents/skills/` so it is not an active repository skill. No scripts, assets, UI metadata, or extra documentation are needed for this starter.

## Add a skill

1. Define one task, its inputs, expected output, and example requests that should trigger it.
2. Copy `templates/codex-skill-starter/` to `.agents/skills/your-skill-name/` in the repository where the skill will run. Use lowercase letters, digits, and hyphens; keep the name under 64 characters.
3. Set YAML `name` to the folder name. Replace `description` with a short statement of the task and specific triggers. Keep only `name` and `description` in frontmatter.
4. Replace the title and bracketed workflow items with verified instructions. Preserve decision rules, input/output contracts, required validation, and stopping conditions.
5. Populate `references/context.md` only with relevant, verified facts. Record the source/version and when each section applies. If no reference is needed, delete it and remove its link from SKILL.md.
6. Invoke the completed skill with `$your-skill-name` in Codex and try a representative request. Also try a request outside its scope to check the description does not trigger too broadly.

## Keep token use low

- Keep metadata short and precise; it supports skill discovery.
- Keep the SKILL.md body to the core workflow. Aim for a few dozen lines; the official guide recommends staying under 500 lines.
- Store detailed schemas, approved mappings, exceptions, and examples once in references. Link each file directly from SKILL.md and state when to read it. Never load all references by default.
- Search large references with `rg` and read the relevant section. Add a table of contents when a reference exceeds 100 lines.
- Add `scripts/` only for repeated deterministic work; document inputs, outputs, and how to run it, and test it. Add `assets/` only for files used in generated output.
- Add optional `agents/openai.yaml` only when UI metadata, invocation policy, or tool dependencies are useful; keep it consistent with SKILL.md.
- Remove general tutorials, repeated instructions, and stale facts. Preserve essential constraints and evidence paths; shorter text alone does not guarantee lower total execution cost.

## Maintain and review

Change skills on a branch and review through a pull request. Check that folder name and YAML `name` match, links resolve, and completed skills contain no template placeholders. When available, run the official skill-creator `scripts/quick_validate.py` against the completed skill folder; structural validation does not prove task correctness. Test the actual workflow and any bundled scripts after meaningful changes.

Keep the current rules in the skill and use Git history for change tracking. Refresh referenced facts when their source changes. Do not commit credentials or private production data to this public repository.

## Official guidance

- [OpenAI skill-creator guide](https://github.com/openai/skills/blob/main/skills/.system/skill-creator/SKILL.md)
- [Codex skill documentation](https://developers.openai.com/codex/skills)
