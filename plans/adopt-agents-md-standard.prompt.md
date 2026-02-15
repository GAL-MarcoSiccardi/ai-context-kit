---
description: "Step-by-step (committable) plan to refactor AI Context Kit to use AGENTS.md as the primary standard entrypoint without losing any existing features (spec v1.2 instruction system stays)."
status: open
---

# Refactor Plan (Committable): Adopt `AGENTS.md` Standard (No Feature Loss)

You are working in the `ai-context-kit` repository.

## Goal
Refactor this repository so it **follows the `AGENTS.md` standard going forward**, using root `AGENTS.md` as the **primary, embedded agent entrypoint for this repo**, while **preserving all existing capabilities**:
- Spec-driven session-state model (`specs/context_aware_ai_session_spec.md`)
- Layered instruction files (`usercontexts/*.instructions.md` + `projects/*.instructions.md`)
- Canonical templates (`templates/*.instructions.md`)
- Generator + validator prompts (`prompts/*.prompt.md`)
- Existing file paths and conventions

## Non-Goals
- Do not delete or rename existing folders/files.
- Do not replace the spec with `AGENTS.md`; `AGENTS.md` should embed operational essentials and link to deeper references.
- Root `AGENTS.md` is **repo-only** (not a general template).
- Do not introduce provider-specific syntax that harms portability (unless clearly marked optional).

## Branch Strategy
- Perform the entire migration on a dedicated feature branch.
- Merge to `main` only after the full plan is complete and reviewed.


## Delivery Strategy: Small, Reviewable Commits
Implement this refactor in discrete commits. Each commit must:
- Touch only the files necessary for that slice.
- Be shippable by itself (docs consistent, links valid).
- Avoid cascading rewrites.

## Human Review Gate (Before Each Commit)
After completing the work for a commit:
- Stop and ask the user to review the changes.
- Do not run `git commit` (the user will commit manually).
- When the user explicitly asks for a commit message, propose one that describes **only the changes since the last commit**.

## Validation Report Write Access (Fallback Policy)
When a validation prompt instructs writing a `*.validation.md` file:
- **If you have write access**, create/overwrite the file at the specified path.
- **If you do not have write access (or are unsure)**, output the complete report as a single Markdown block and clearly state the recommended filename/path so a human can save it.


## Formatting & Style Consistency
Apply these rules to all new/updated files created by this plan (`AGENTS.md`, `templates/AGENTS_template.md`, `prompts/*.prompt.md`, and any updated docs):
- **No decorative icons/emojis** in headers (per spec guidance).
- **Consistent Markdown structure**: clear headings, clean lists, tables where appropriate.
- **Use relative paths** when referencing repo files.
- **Keep language provider-agnostic** (no tool- or vendor-specific assumptions).
- **Do not introduce new naming conventions**; follow existing repo conventions.
- **Prompt file style parity**: new prompts should match the tone/structure of existing prompts in `prompts/`.


### Commit 0 — Full repo analysis (no changes)
- Inventory repo files (exclude `.git/` and non-text binaries like `.DS_Store`).
- Read **all** repo text files completely to build a big-picture map:
  - `README.md`, `LICENSE`, `.gitignore`
  - `specs/*.md`
  - `templates/*`
  - `prompts/*`
  - `projects/*`, `usercontexts/*`
  - `plans/*` (planning prompts)
- Identify and write down (not committed) the current “sources of truth” and their precedence (spec vs templates vs prompts vs samples).
- Confirm the `/ack.*` command surface + default session state currently used by this repo.
- Confirm formatting rules (e.g., no decorative icons in headers) and canonical path stability expectations.



---

### Commit 1a — Add root `AGENTS.md` skeleton + repo map
**Files:**
- NEW: `AGENTS.md`

**Scope:**
- Create a concise first draft that an agent can open first and immediately understand what this repo is and where the “truth” lives.

**Include:**
- What this repo is (instruction layer kit; instructions vs prompts; cross-provider).
- Source-of-truth hierarchy (spec is authoritative; templates are canonical; prompts generate/validate; samples demonstrate).
- Repo map (purpose of `specs/`, `templates/`, `prompts/`, `projects/`, `usercontexts/`).
- Links to deeper references (relative paths) for: spec, templates, prompts, sample files.

**Defer to next commit:**
- The full `/ack.*` command surface details
- Default session state table
- Detailed formatting/path stability rules

**Acceptance check:**
- `AGENTS.md` is scannable and accurate.
- All links are relative and valid.

---

### Commit 1b — Expand `AGENTS.md` with the operational contract
**Files:**
- UPDATE: `AGENTS.md`

**Add:**
- Session-state model summary + “no silent transitions”.
- Commands: `/ack.context`, `/ack.mode`, `/ack.phase`, `/ack.style`, `/ack.tone`, `/ack.interact`, `/ack.reset`.
- Default state aligned to `projects/ai_context_kit_project.instructions.md`.
- Formatting/path stability rules (no decorative icons; keep canonical paths stable).
- Contribution/update rule: if spec changes, update templates + prompts + samples + README + `AGENTS.md`.

**Acceptance check:**
- Meets **Definition of Done (Root `AGENTS.md`)** below.

## Definition of Done (Root `AGENTS.md`)
The root `AGENTS.md` is done when it is **repo-only**, **scannable**, and contains (at minimum):
- **Purpose + model**: what AI Context Kit is; the distinction between **instructions** vs **prompts/queries**.
- **Truth sources + precedence**: what is authoritative (spec), canonical (templates), operational (prompts), and illustrative (samples).
- **Repo map**: one-line purpose for `specs/`, `templates/`, `prompts/`, `projects/`, `usercontexts/`, `plans/`.
- **Scoping & precedence policy**: if nested `AGENTS.md` files exist later, define scope (directory subtree) and precedence (closest wins), and state how conflicts are handled.
- **Session-state summary**: Role/Mode, Phase, Output Style, Tone, Interaction Mode; state persists; **no silent transitions**.
- **Ambiguity rule**: when unclear, ask before changing project/role/phase/assumptions.
- **Command surface**: `/ack.context`, `/ack.mode`, `/ack.phase`, `/ack.style`, `/ack.tone`, `/ack.interact`, `/ack.reset` with short descriptions.
- **Namespace policy**: commands are namespaced (`/ack.*`); if aliases are allowed, state when they are acceptable.
- **Default state (explicit values)** aligned to `projects/ai_context_kit_project.instructions.md`.
- **Formatting + stability rules**: no decorative icons/emojis in headers; keep canonical paths stable; use relative paths.
- **Contribution/update rule**: if the spec changes, audit/update (as applicable) `templates/`, `prompts/`, samples, `README.md`, and `AGENTS.md`.
- **Links**: relative links to the spec and the canonical templates/prompts (so an agent can dive deeper).

Also:
- **No full spec duplication**: embed essentials, link the rest.
- **Provider-agnostic language**: avoid provider-specific tooling assumptions.

## AGENTS.md Scoping & Precedence Policy (for future nested files)
Document this policy in root `AGENTS.md` so it’s clear even if you don’t add nested `AGENTS.md` files today:
- **Scope:** An `AGENTS.md` applies to the directory it is in and all subdirectories.
- **Precedence:** If multiple `AGENTS.md` files apply, the **closest (deepest) one wins** for files in its subtree.
- **Conflict handling:** If two instructions conflict, follow the more specific file; if still ambiguous, ask.
- **No duplication:** Keep root `AGENTS.md` global; keep nested `AGENTS.md` narrowly focused on that folder.
- **Path stability:** If nested `AGENTS.md` introduces path assumptions, document them and keep paths stable.

---

### Commit 2 — Add general-purpose template `templates/AGENTS_template.md`
**Files:**
- NEW: `templates/AGENTS_template.md`

**Template requirements:**
- Placeholders for project name, tech stack, repo layout.
- Minimal session-state model summary.
- Command namespace section (e.g., `/xyz.*`).
- “Ask when ambiguous” + “no silent transitions”.
- Formatting/path stability guidance.

**Acceptance check:**
- A user could copy it into another repo as `AGENTS.md` and fill blanks.

---

### Commit 3a — Add generator prompt skeleton `prompts/create-agents-md.prompt.md`
**Files:**
- NEW: `prompts/create-agents-md.prompt.md`

**Scope:**
- Create the prompt’s overall structure and discovery phases, consistent with existing create prompts.

**Include:**
- Frontmatter `description`.
- Mission, scope & preconditions, inputs.
- Multi-phase discovery outline (project identity, repo layout, roles/phases/commands, standards, tools/tests, contribution workflow).

**Defer to next commit:**
- The final “generation rules” section
- Output format block
- Validation checklist

**Acceptance check:**
- Prompt structure matches the style of `prompts/create-usercontext-instructions.prompt.md` and `prompts/create-project-instructions.prompt.md`.

---

### Commit 3b — Complete generator prompt output rules + checklist
**Files:**
- UPDATE: `prompts/create-agents-md.prompt.md`

**Add:**
- Generation rules: embed essentials, link deeper docs, keep `AGENTS.md` short/scannable.
- Output format: a complete `AGENTS.md` as a single Markdown block.
- Validation checklist: links valid, essentials present, no overstuffing, provider-agnostic language.
- Example reference: point to this repo’s `AGENTS.md` as a sample and to `templates/AGENTS_template.md` as the canonical starting point.

**Acceptance check:**
- Prompt can be pasted into any assistant and still makes sense.

---

### Commit 4 — Add validator prompt `prompts/validate-agents-md.prompt.md` (recommended)
**Files:**
- NEW: `prompts/validate-agents-md.prompt.md`

**Prompt requirements:**
- Mirror structure of existing validators (5 phases, score /100, clear pass/fail criteria).
- Validate: clarity/actionability, required operational content, portability, scoping/precedence guidance (if used), and “do not overstuff”.
- Output: `.validation.md` report format.
- Include an **Example Fixes** section with short snippets (like existing validators) for common failures.

**Acceptance check:**
- Validator is specific enough to catch drift and missing essentials.

---

### Commit 5 — Update `README.md` (minimal)
**Files:**
- UPDATE: `README.md`

**Changes:**
- Declare `AGENTS.md` as primary agent entrypoint for this repo.
- Explain relationship to the existing spec/templates/prompts (spec remains authoritative).
- Mention `plans/` contains planning prompts, and they are plain Markdown usable anywhere.

**Acceptance check:**
- README remains correct and does not break existing onboarding.

---

### Commit 6 — Optional: small spec note
**Files:**
- OPTIONAL UPDATE: `specs/context_aware_ai_session_spec.md`

**Changes:**
- Add a brief note that `AGENTS.md` can serve as a bootstrap entrypoint (embed essentials), while the spec remains normative.

**Acceptance check:**
- No scope expansion; just an acknowledgement.

---

## Final Sanity Checks (after each commit)
- Drift control: if `specs/context_aware_ai_session_spec.md` changes, audit/update (as applicable): `templates/`, `prompts/`, sample files in `projects/` + `usercontexts/`, `README.md`, and `AGENTS.md`.
- Paths referenced exist.
- No circular dependency (“read X” with no embedded guidance).
- No provider-specific instructions introduced.
- Existing samples and validation reports remain untouched.
