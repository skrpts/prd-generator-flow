# Release Notes

## v1.1.30
GH#863 Wave 1 (#858-A1 class) — fix K-045 intent/output mismatch: the workflow shipped the prd-assembler, problem-statement-writer, and success-metrics-definer prompts but never invoked them, so it emitted polished intermediate analysis rather than the promised PRD. Wired all three as execution steps in dependency order (Problem Statement → Requirements → Personas → Technical Scoping → Success Metrics → Executive Summary → **PRD Assembler** → language-polish), each backed by a new skill (`problem-statement`, `success-metrics`, `prd-assembly`) so its title is `from_step`-addressable. Cross-step inputs are now explicit `from_step` bindings via named `context_params`. Repinned polish-language 1.0.1→1.0.6 (adds the bindable `source` slot) and bound language-polish `source` ← the assembled PRD, so the final output is the polished PRD rather than the last intermediate step. Skills 1→4, total 13→16.

## v1.1.29
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.28
GH#745 — declare per-step `output: {name, type}` on every execution step (requirements/text, personas/text, technical_scope/text, summary/text, polished_prd/text, consistency_verdict/decision, input_gaps/decision, compliance_verdict/decision). Lights up the #744 rich flow-map with named, typed outputs. **Also corrects the input-gap-check step to its intended `validation` type** — its `step_type` was mis-indented (outside the parallel item) and dropped at parse time, so the step previously ran untyped; it is now a validation gate. Content + structural fix (GH#748); no bindings changes.

## v1.1.27
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 14 inline shared-content files and declare 14 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.26
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.25
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.24
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.23
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.22
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
