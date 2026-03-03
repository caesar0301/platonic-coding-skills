# Platonic Coding Workflow — Reference

This folder contains the reference instructions for each phase of the **platonic-workflow** workflow. Always show the **current phase** when executing a step.

## Workflow Overview

Read [workflow-overview.md](workflow-overview.md) for phase order, default paths, and when to invoke other skills.

## Phase Reference Files

| Phase | File | Purpose |
|-------|------|---------|
| — | `workflow-overview.md` | End-to-end workflow and phase visibility |
| 0 | `phase-0-design-draft.md` | Conceptual design and design draft (interactive chat, optional items) |
| 1 | `phase-1-rfc-spec.md` | Generate RFC from draft, then **platonic-specs** refine |
| 2 | `phase-2-implementation.md` | **platonic-impl** — full implementation (guide + code with tests) |
| 3 | `phase-3-review.md` | **platonic-code-review** — review code vs specs and impl guides |

## Execution Order

1. **Phase 0**: Follow `phase-0-design-draft.md`. Output: design draft (default `docs/drafts/`).
2. **Phase 1**: Follow `phase-1-rfc-spec.md`. Optionally ask for RFC index. Generate RFC, then call **platonic-specs** (refine). Output: RFC in `docs/specs/`.
3. **Phase 2**: Follow `phase-2-implementation.md`. Optionally ask for RFC index. Call **platonic-impl** (full-impl operation: guide → coding plan → code with tests). Output: impl guide in `docs/impl/` + source code with tests.
4. **Phase 3**: Follow `phase-3-review.md`. Call **platonic-code-review** (code + targeted RFC spec + impl guide). Output: review/compliance report.
5. **FINISHED**: Summarize and recommend follow-ups.

## Default Paths

- Design drafts: `docs/drafts/`
- RFC specs: `docs/specs/`
- Implementation guides: `docs/impl/`

## Skill Dependencies

- **Phase 1**: `platonic-specs` — refine operation (see `skills/platonic-specs/references/refine-specs.md`).
- **Phase 2**: `platonic-impl` — full-impl operation (see `skills/platonic-impl/references/full-impl.md`).
- **Phase 3**: `platonic-code-review` — review procedure (see `skills/platonic-code-review/references/REFERENCE.md`).

Read the corresponding reference file before executing each phase.
