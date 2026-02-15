# AI Context Kit Agent Guide

## Purpose
AI Context Kit is a cross-provider instruction-layer repository for context-aware AI collaboration.  
It defines persistent instruction structures, generation/validation workflows, and reference examples.

This repository distinguishes:
- **Instructions**: persistent context files (`*.instructions.md`) that define who the user is, what the project is, and how collaboration should run.
- **Prompts/queries**: day-to-day requests made inside that instructed environment.

## Source Of Truth And Precedence
Use this order when files differ:
1. **Specification (authoritative):** `specs/context_aware_ai_session_spec.md`
2. **Templates (canonical structures):** `templates/*.instructions.md`
3. **Prompts (operational workflows):** `prompts/*.prompt.md`
4. **Samples (illustrative examples):** `projects/*.instructions.md`, `usercontexts/*.instructions.md`, and related `*.validation.md`

## Repository Map
| Path | Purpose |
| --- | --- |
| `specs/` | Normative session-model specification and terminology |
| `templates/` | Canonical instruction templates aligned to the spec |
| `prompts/` | Create/validate prompt workflows for instruction files |
| `projects/` | Project-level instruction examples and validation reports |
| `usercontexts/` | User-context instruction examples and validation reports |
| `plans/` | Planning prompts used to execute repository refactors |

## Key References
- Specification: [`specs/context_aware_ai_session_spec.md`](specs/context_aware_ai_session_spec.md)
- User context template: [`templates/usercontext_template.instructions.md`](templates/usercontext_template.instructions.md)
- Project template: [`templates/project_template.instructions.md`](templates/project_template.instructions.md)
- Create prompts:
  - [`prompts/create-usercontext-instructions.prompt.md`](prompts/create-usercontext-instructions.prompt.md)
  - [`prompts/create-project-instructions.prompt.md`](prompts/create-project-instructions.prompt.md)
- Validate prompts:
  - [`prompts/validate-usercontext-instructions.prompt.md`](prompts/validate-usercontext-instructions.prompt.md)
  - [`prompts/validate-project-instructions.prompt.md`](prompts/validate-project-instructions.prompt.md)
- Sample project instructions: [`projects/ai_context_kit_project.instructions.md`](projects/ai_context_kit_project.instructions.md)
- Sample user context instructions: [`usercontexts/sample_usercontext.instructions.md`](usercontexts/sample_usercontext.instructions.md)
