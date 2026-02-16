# Skill-First Parity Report

## Purpose
Record dual-path parity outcomes between prompt-authoritative behavior and skill-authoritative behavior for migrated workflows.

## Execution Metadata
- Run date:
- Run owner:
- Branch/ref:
- Scope:

## Golden Fixtures
- `projects/ai_context_kit_project.instructions.md`
- `usercontexts/sample_usercontext.instructions.md`
- `AGENTS.md`

## Parity Criteria
- Overall status parity (`PASS`, `PASS WITH WARNINGS`, `FAIL`)
- Required section/field detection parity
- Critical issue parity
- Score delta `<= 2`
- Validation report schema parity

## Workflow Parity Matrix
| workflow_id | fixture_path | prompt_status | skill_status | status_parity | prompt_score | skill_score | score_delta | section_field_parity | critical_issue_parity | report_schema_parity | result | notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `validate-project-instructions` | `projects/ai_context_kit_project.instructions.md` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `pending` | `-` |
| `validate-usercontext-instructions` | `usercontexts/sample_usercontext.instructions.md` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `pending` | `-` |
| `validate-agents-md` | `AGENTS.md` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `pending` | `-` |

## Discrepancy Log
| id | workflow_id | fixture_path | discrepancy_type | severity | description | expected | actual | remediation | owner | status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `D-001` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `-` | `open` |

## Summary
- Total workflows checked:
- Total fixture runs:
- Parity pass count:
- Parity fail count:
- Blockers:

## Merge Readiness Checklist
- [ ] All migrated workflows pass parity checks on required fixtures.
- [ ] No missing critical issue in skill path vs prompt baseline.
- [ ] Score delta is `<= 2` for all parity runs.
- [ ] Report schema parity is confirmed for all validator workflows.
- [ ] Open discrepancies are resolved or explicitly accepted.

## Sign-Off
- Migration owner:
- Quality reviewer:
- Approval date:

