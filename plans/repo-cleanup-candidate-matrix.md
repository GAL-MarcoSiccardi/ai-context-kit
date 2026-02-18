# Repo Cleanup Candidate Matrix

## Purpose
Track post-migration cleanup candidates and approved actions so deletions/retentions are explicit and reviewable.

## Action Keys
- `delete`: remove file/artifact as no longer needed.
- `retain`: keep file/artifact in place.
- `archive`: move to archival location under `plans/` while preserving traceability.

## Candidate Table
| path | artifact_type | owner_area | current_role | duplication_or_staleness_reason | approved_action | replacement_or_retention_note |
| --- | --- | --- | --- | --- | --- | --- |
| `plans/skill-first-migration-matrix.md` | migration tracking | `plans` | Historical evidence of authority migration | Transitional but still linked from executed migration plan | `retain` | Keep as execution evidence for `plans/adopt-skill-first-workflow-authority.prompt.md` |
| `plans/skill-first-parity-report.md` | parity evidence | `plans` | Dual-path verification record | Transitional but required for auditability of quality gates | `retain` | Keep as immutable parity artifact for completed migration |
| `plans/skill-first-quality-gate-map.md` | quality gate inventory | `plans` | Rule-level parity and verification ledger | Transitional format but still authoritative migration evidence | `retain` | Keep; continue consistency updates when stale wording appears |
| `plans/skill-extraction-matrix.md` | extraction tracking | `plans` | Coverage/status ledger for extracted skills | Primarily historical, but referenced by executed extraction plan | `retain` | Keep as extraction audit trail |
| `plans/adopt-agent-skills-foundation.prompt.md` | executed plan | `plans` | Execution history | Not temporary; lifecycle record | `retain` | Required by plan lifecycle policy |
| `plans/adopt-agents-md-standard-codex.prompt.md` | executed plan | `plans` | Execution history | Not temporary; lifecycle record | `retain` | Required by plan lifecycle policy |
| `plans/extract-agent-skills-from-existing-artifacts.prompt.md` | executed plan | `plans` | Execution history | Not temporary; lifecycle record | `retain` | Required by plan lifecycle policy |
| `plans/adopt-skill-first-workflow-authority.prompt.md` | executed plan | `plans` | Execution history | Not temporary; lifecycle record | `retain` | Required by plan lifecycle policy |
| `plans/README.md` | governance doc | `plans` | Plan lifecycle policy | Canonical policy file; not redundant | `retain` | Required by `AGENTS.md` plan policy |
| `plans/plan-status.sh` | utility script | `plans` | Open/executed plan status checker | Canonical utility; no duplicate | `retain` | Keep as required lifecycle tool |
| `prompts/create-*.prompt.md` | compatibility wrapper set | `prompts` | User-facing compatibility entrypoints | Not stale; wrappers intentionally retained | `retain` | Skill-first model requires wrappers remain thin but available |
| `prompts/validate-*.prompt.md` | compatibility wrapper set | `prompts` | User-facing compatibility entrypoints | Not stale; wrappers intentionally retained | `retain` | Skill-first model requires wrappers remain thin but available |
| `skills/create-usercontext-instructions/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |
| `skills/create-project-instructions/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |
| `skills/create-agents-md/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |
| `skills/validate-usercontext-instructions/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |
| `skills/validate-project-instructions/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |
| `skills/validate-agents-md/references/source-mapping.md` | traceability map | `skills` | Source provenance for extracted rules | Some mappings may still reference prompt-era anchors post-wrapper conversion | `retain` | Commit 2: normalize mappings to canonical skill refs + historical prompt revision |

## Commit 1 Validation Checklist
- [x] Candidate rows include explicit rationale.
- [x] Every candidate row has an `approved_action`.
- [x] No canonical artifact is marked `delete` without replacement rationale.
- [x] Cleanup actions preserve plan lifecycle records.
