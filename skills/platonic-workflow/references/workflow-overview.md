# Platonic Coding Workflow Overview

## Objective

Execute the full five-phase Platonic Coding workflow with clear phase visibility and correct handoffs between design draft, RFC spec, implementation guide, code, and review.

## Phase Visibility Rule

**Always show the current Phase** at the start of each step and in any status summary, e.g.:

- `[Phase 0] Conceptual Design & Design Draft`
- `[Phase 1] RFC Specification (Draft)`
- `[Phase 2] Implementation Guide`
- `[Phase 3] Code Implementation`
- `[Phase 4] Spec Compliance Review`
- `[FINISHED]`

## Phase Flow

```
Phase 0: Conceptual Design
    → design draft (docs/drafts/ or user-provided)
Phase 1: RFC from draft + platonic-specs refine
    → RFC in specs/
Phase 2: platonic-impl-guide from RFC
    → impl guide in docs/impl/
Phase 3: Coding agents write code
    → source code
Phase 4: platonic-code-review (code + specs + impl RFCs)
    → review/compliance report
FINISHED
```

## Default Paths

- Design drafts: `docs/drafts/`
- RFC specs: `specs/`
- Implementation guides: `docs/impl/`

User may override any path.

## When to Ask the User

- **Phase 1**: RFC number/index for the new or updated RFC, if not specified.
- **Phase 2**: RFC number/index for which to create the implementation guide, if not specified.
- **Phase 0**: Clarify scope, constraints, and where to save the design draft if not using default.

## Skill Invocations

| Phase | Skill / Action |
|-------|----------------|
| 1 | **platonic-specs** — refine generated RFC (and related specs) |
| 2 | **platonic-impl-guide** — create implementation guide from RFC |
| 4 | **platonic-code-review** — review code against RFC specs and impl guides |

Read the phase-specific reference file before executing each phase.
