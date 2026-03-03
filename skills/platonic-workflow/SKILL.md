---
name: platonic-workflow
description: Orchestrate the full Platonic Coding workflow from conceptual design to RFC specs, implementation (guide + code with tests), and spec-compliance review. Always shows current phase; uses interactive chat in Phase 0, invokes platonic-specs in Phase 1, platonic-impl in Phase 2 (impl guide + coding), and platonic-code-review in Phase 3.
license: MIT
metadata:
  version: "1.0.3"
  author: "Xiaming Chen"
  category: "workflow"
---

# Platonic Coding Workflow

Orchestrate the complete **four-phase Platonic Coding workflow** from conceptual design through specification, implementation (guide + code), and review.

## When to Use This Skill

Use this skill when you need to:

- **Run the full workflow** from design idea to reviewed implementation
- **Progress through phases** with clear phase visibility and handoffs
- **Ensure traceability** from design draft → RFC → impl guide → code → review
- **Coordinate other skills** (platonic-specs, platonic-impl, platonic-code-review) in the correct order

Keywords: workflow, platonic coding, design draft, RFC, implementation guide, code review, phase

## Phase Visibility

**Always show the current Phase of the workflow** at the start of each step and in summaries:

- **Phase 0**: Conceptual Design & Design Draft
- **Phase 1**: RFC Specification (Draft)
- **Phase 2**: Implementation (Guide + Code)
- **Phase 3**: Spec Compliance Review
- **FINISHED**: Workflow complete

## Workflow Summary

| Phase | Focus | Output Location | Skills / Actions |
|-------|--------|------------------|------------------|
| **0** | Conceptual design, requirements | `docs/drafts/` | Interactive chat, optional items |
| **1** | Formal RFC from design draft | `docs/specs/` | Generate RFC, then **platonic-specs** (refine) |
| **2** | Impl guide + code with tests | `docs/impl/` + Codebase | **platonic-impl** (full impl sub-workflow) |
| **3** | Review code vs specs & impl guides | Report | **platonic-code-review** |
| **FINISHED** | — | — | — |

## Phase Details

### Phase 0: Conceptual Design & Design Draft

- **Goal**: Obtain a shared conceptual design (principles, constraints, conceptual interfaces, design art, etc.).
- **Method**: Interactive chat; use optional items to communicate with the user.
- **Output**: A **design draft**.
- **Location**: Default `docs/drafts/`. The user may provide a draft from elsewhere.
- **Reference**: See `references/phase-0-design-draft.md`.

### Phase 1: RFC Specification (Draft)

- **Goal**: Turn the design draft into a formal RFC spec (Status: Draft).
- **Optional**: Ask the user for RFC number/index if not specified.
- **Actions**:
  1. Generate RFC from the Phase 0 design draft.
  2. **Call platonic-specs** to refine the generated RFC (and related specs).
- **Output**: RFC(s) in the specs directory.
- **Location**: Default `docs/specs/`.
- **Reference**: See `references/phase-1-rfc-spec.md`.

### Phase 2: Implementation (Guide + Code)

- **Goal**: Produce a concrete implementation guide from the RFC spec, then implement the code with tests.
- **Optional**: Ask the user for RFC number/index if not specified.
- **Actions**: Use **platonic-impl** (full-impl operation) which runs a four-step sub-workflow:
  1. Spec analysis — extract requirements from RFC
  2. Impl guide design — create architecture doc (user confirmation gate)
  3. Coding plan — task breakdown with file-level changes (user confirmation gate)
  4. Coding — implement code with unit and integration tests
- **Output**: Implementation guide in `docs/impl/` + source code with tests in codebase.
- **Reference**: See `references/phase-2-implementation.md`.

### Phase 3: Spec Compliance Review

- **Goal**: Review implementation against both RFC specs and implementation guides.
- **Actions**: Call **platonic-code-review** to review the code implementation and the targeted RFC (specs and impl guides).
- **Output**: Review and compliance report.
- **Reference**: See `references/phase-3-review.md`.

### FINISHED

- Workflow complete. Summarize outcomes and any follow-up recommendations.

## Default Paths

| Artifact | Default Path |
|----------|--------------|
| Design drafts | `docs/drafts/` |
| RFC specs | `docs/specs/` |
| Implementation guides | `docs/impl/` |

Paths may be overridden by the user.

## Available References

| Phase | Reference File | Purpose |
|-------|----------------|---------|
| Overview | `workflow-overview.md` | End-to-end workflow and phase transitions |
| Phase 0 | `phase-0-design-draft.md` | Conceptual design and design draft |
| Phase 1 | `phase-1-rfc-spec.md` | RFC generation and platonic-specs refine |
| Phase 2 | `phase-2-implementation.md` | platonic-impl full sub-workflow (guide + code) |
| Phase 3 | `phase-3-review.md` | platonic-code-review usage |

See [references/REFERENCE.md](references/REFERENCE.md) for detailed phase procedures.

## Best Practices

1. **Always show current phase** at the start of each step and in status summaries.
2. **Confirm handoffs**: Before leaving a phase, confirm outputs and paths with the user if ambiguous.
3. **Ask for indices when useful**: In Phase 1 (RFC number) and Phase 2 (RFC for implementation), ask for index if not provided.
4. **Call skills explicitly**: Phase 1 → platonic-specs (refine); Phase 2 → platonic-impl (full-impl); Phase 3 → platonic-code-review.
5. **Preserve traceability**: Keep links between design draft → RFC → impl guide → code in summaries and docs.

## Dependencies

- **platonic-specs**: Phase 1 (refine RFCs).
- **platonic-impl**: Phase 2 (full implementation: guide + code with tests).
- **platonic-code-review**: Phase 3 (review code vs specs and impl guides).
- Read/write access to `docs/drafts/`, `docs/specs/`, `docs/impl/` and codebase as needed.
