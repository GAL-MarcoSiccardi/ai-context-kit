# Skill-First Quality Gate Map

## Purpose
Track 1:1 parity between prompt-era quality rules and their canonical skill-era enforcement points.

## Status Values
- `unmapped`: Rule exists in prompt workflow but no canonical skill mapping is defined.
- `mapped`: Canonical skill mapping exists but parity not yet verified.
- `verified`: Mapping exists and parity has been verified through dual-path checks.

## Gate Classes
- `schema`
- `workflow`
- `report`
- `scoring`
- `severity`
- `safety`
- `portability`
- `wrapper-thinness`

## Rule Mapping Table
| workflow_id | prompt_rule_id | gate_class | requirement_summary | prompt_source_path | prompt_source_anchor | skill_target_path | verification_method | status | verified_by | verified_at | notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `validate-project-instructions` | `vp-001` | `schema` | `YAML frontmatter checks are complete and deterministic` | `prompts/validate-project-instructions.prompt.md` | `### Phase 1: YAML Frontmatter Validation` | `skills/validate-project-instructions/references/...` | `dual-path fixture comparison` | `unmapped` | `-` | `-` | `-` |
| `validate-usercontext-instructions` | `vu-001` | `schema` | `Required sections coverage is enforced` | `prompts/validate-usercontext-instructions.prompt.md` | `### Phase 2: Required Sections Validation` | `skills/validate-usercontext-instructions/references/...` | `dual-path fixture comparison` | `unmapped` | `-` | `-` | `-` |
| `validate-agents-md` | `va-001` | `report` | `Validation report schema is complete` | `prompts/validate-agents-md.prompt.md` | `## Validation Report Format` | `skills/validate-agents-md/references/...` | `report schema parity check` | `unmapped` | `-` | `-` | `-` |

## Blocking Checklist
- [ ] No required rule remains `unmapped`.
- [ ] All migrated workflow rules are at least `mapped`.
- [ ] Wrapper-thinness rules exist for every prompt wrapper.
- [ ] All required rules are `verified` before marking migration complete.

## Reviewer Sign-Off
- Owner:
- Reviewer:
- Last updated:

