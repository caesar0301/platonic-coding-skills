# Platonic Coding Workflow Overview

## Objective

Execute the full four-phase Platonic Coding workflow with clear phase visibility and correct handoffs between design draft, RFC spec, implementation (guide + code), and review.

## Phase Visibility Rule

**Always show the current Phase** at the start of each step and in any status summary, e.g.:

- `[Phase 0] Conceptual Design & Design Draft`
- `[Phase 1] RFC Specification (Draft)`
- `[Phase 2] Implementation (Guide + Code)`
- `[Phase 3] Spec Compliance Review`
- `[FINISHED]`

## Phase Flow

```
Phase 0: Conceptual Design
    → design draft (docs/drafts/ or user-provided)
Phase 1: RFC from draft + platonic-specs refine
    → RFC in docs/specs/
Phase 2: platonic-impl full sub-workflow
    → impl guide in docs/impl/ + source code with tests
Phase 3: platonic-code-review (code + specs + impl guides)
    → review/compliance report
FINISHED
```

## Default Paths

- Design drafts: `docs/drafts/`
- RFC specs: `docs/specs/`
- Implementation guides: `docs/impl/`

User may override any path.

## When to Ask the User

- **Phase 0**: Clarify scope, constraints, and where to save the design draft if not using default.
- **Phase 1**: RFC number/index for the new or updated RFC, if not specified.
- **Phase 2**: RFC number/index for which to implement, if not specified. The platonic-impl skill handles its own confirmation gates for impl guide and coding plan.

## Skill Invocations

| Phase | Skill / Action |
|-------|----------------|
| 1 | **platonic-specs** — refine generated RFC (and related specs) |
| 2 | **platonic-impl** — full-impl: spec analysis → impl guide → coding plan → code with tests |
| 3 | **platonic-code-review** — review code against RFC specs and impl guides |

Read the phase-specific reference file before executing each phase.
