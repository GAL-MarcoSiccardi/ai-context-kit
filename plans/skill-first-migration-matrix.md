# Skill-First Migration Matrix

## Purpose
Track migration progress from prompt-authoritative workflows to skill-authoritative workflows.

## Status Keys
- `migration_status`: `planned`, `migrated`, `validated`
- `current_authority`: current canonical source of operational workflow behavior
- `target_authority`: intended canonical source after migration

## Workflow Matrix
| workflow_id | canonical_skill_path | current_authority | target_authority | prompt_wrapper_path | migration_status | duplication_risk_notes |
| --- | --- | --- | --- | --- | --- | --- |
| `create-usercontext-instructions` | `skills/create-usercontext-instructions/` | `prompts/create-usercontext-instructions.prompt.md` | `skills/create-usercontext-instructions/` | `prompts/create-usercontext-instructions.prompt.md` | `planned` | `High: large discovery + generation/checklist blocks duplicated in prompt` |
| `create-project-instructions` | `skills/create-project-instructions/` | `prompts/create-project-instructions.prompt.md` | `skills/create-project-instructions/` | `prompts/create-project-instructions.prompt.md` | `planned` | `High: section/command table templates and checklist are prompt-heavy` |
| `create-agents-md` | `skills/create-agents-md/` | `prompts/create-agents-md.prompt.md` | `skills/create-agents-md/` | `prompts/create-agents-md.prompt.md` | `planned` | `Medium: phased discovery + validation checklist duplicated` |
| `validate-usercontext-instructions` | `skills/validate-usercontext-instructions/` | `prompts/validate-usercontext-instructions.prompt.md` | `skills/validate-usercontext-instructions/` | `prompts/validate-usercontext-instructions.prompt.md` | `planned` | `High: pass criteria/report schema/scoring repeated in prompt` |
| `validate-project-instructions` | `skills/validate-project-instructions/` | `prompts/validate-project-instructions.prompt.md` | `skills/validate-project-instructions/` | `prompts/validate-project-instructions.prompt.md` | `planned` | `High: detailed phase gates/report rubric/scoring repeated in prompt` |
| `validate-agents-md` | `skills/validate-agents-md/` | `prompts/validate-agents-md.prompt.md` | `skills/validate-agents-md/` | `prompts/validate-agents-md.prompt.md` | `planned` | `High: operational contract checks/report schema/scoring repeated in prompt` |
| `create-skill` | `skills/create-skill/` | `prompts/create-skill.prompt.md` | `skills/create-skill/` | `prompts/create-skill.prompt.md` | `planned` | `Medium: generation rules + checklist still prompt-only` |
| `validate-skill` | `skills/validate-skill/` | `prompts/validate-skill.prompt.md` | `skills/validate-skill/` | `prompts/validate-skill.prompt.md` | `planned` | `Medium: validator phases/report schema/scoring still prompt-only` |
| `plan-lifecycle-management` | `skills/plan-lifecycle-management/` | `skills/plan-lifecycle-management/` | `skills/plan-lifecycle-management/` | `n/a` | `planned` | `Low: governance skill exists; verify no prompt-level duplication creeps in` |
| `repository-drift-control` | `skills/repository-drift-control/` | `skills/repository-drift-control/` | `skills/repository-drift-control/` | `n/a` | `planned` | `Low: governance skill exists; ensure precedence flip is reflected consistently` |

## Commit 1 Validation Checklist
- [ ] Every prompt workflow has one canonical skill mapping.
- [ ] No prompt workflow is missing `target_authority`.
- [ ] Prompt wrapper path is defined for all prompt-backed workflows.
- [ ] `migration_status` initialized for all rows.

