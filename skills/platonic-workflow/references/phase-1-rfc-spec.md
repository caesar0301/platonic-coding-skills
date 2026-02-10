# Phase 1: RFC Specification (Draft)

## Current Phase

**[Phase 1] RFC Specification (Draft)**

## Objective

Convert the Phase 0 **design draft** into a formal **RFC specification** (Status: Draft) and refine it using **platonic-specs**.

## Inputs

- **Design draft**: From Phase 0 (default path `docs/drafts/` or user-provided).
- **RFC number/index** (optional): If the user has not specified which RFC number to use, ask for it (e.g., next index in `specs/` or a specific number).

## Process

### Step 1: Determine RFC Index

- If the user has not specified an RFC number/index, ask: e.g., "Which RFC number should this be (e.g., RFC-001)?" or suggest the next available index based on existing files in `specs/`.

### Step 2: Generate RFC from Design Draft

- Read the design draft.
- Produce a formal RFC document that:
  - Follows the project’s RFC format (see `specs/rfc-standard.md` if present).
  - Includes: title, status (Draft), summary, motivation, detailed specification (entities, relations, invariants, constraints), terminology, and references.
  - Preserves all material from the design draft in a structured, formal form.
- Write the RFC to the specs directory (default: `specs/`), e.g. `specs/rfc-NNN-<short-title>.md`.

### Step 3: Refine with platonic-specs

- **Call the platonic-specs skill** to refine the specifications.
- Use the **refine** operation: read `skills/platonic-specs/references/refine-specs.md` and apply it to the specs directory (`specs/` by default).
- This updates history, index, namings, and validates consistency and compliance.

## Output

- RFC document(s) in `specs/` with Status **Draft**.
- Updated supporting files (history, index, namings) from refine.

## Default Location

- `specs/`

## Handoff to Phase 2

- Confirm the RFC path and identifier (e.g., RFC-001).
- Proceed to Phase 2 to create the implementation guide for this RFC (or ask which RFC to use if multiple exist).
