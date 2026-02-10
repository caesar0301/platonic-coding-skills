# Phase 3: Code Implementation

## Current Phase

**[Phase 3] Code Implementation**

## Objective

**Write code** that realizes the feature described in the RFC spec and the implementation guide, integrated into the existing codebase. No speculative design or undocumented behavior.

## Inputs

- **Implementation guide**: From Phase 2 (default `docs/impl/`, e.g. `rfc-NNN-<feature>-impl.md`).
- **RFC spec**: From Phase 1 (default `specs/`) for reference.
- **Existing codebase**: Target repo and structure.

## Process

### Step 1: Use Guides as Law

- Read the implementation guide and the relevant RFC.
- Treat them as the source of truth: code is a **realization**, not a source of new requirements.

### Step 2: Run Coding Agents

- Execute coding agents (or equivalent) to:
  - Implement modules, types, and interfaces as specified in the impl guide.
  - Follow language and framework conventions referenced in the guide.
  - Integrate with existing code (imports, wiring, configuration) as described in the guide.
- Do not add behavior or interfaces that are not in the RFC or the impl guide; if something is missing, document it and optionally suggest a spec/guide update instead of inventing it in code.

### Step 3: Verify Integration

- Ensure new code is integrated into the project (build, tests, config) as specified in the implementation guide.

## Output

- **Source code** in the repository implementing the feature.
- Code is traceable to the implementation guide and RFC.

## Handoff to Phase 4

- Confirm which code paths and which RFC(s) / impl guide(s) should be reviewed.
- Proceed to Phase 4: **platonic-code-review** for code vs specs and impl RFCs.
