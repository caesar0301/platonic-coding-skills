# Phase 2: Implementation Guide

## Current Phase

**[Phase 2] Implementation Guide**

## Objective

Produce a **concrete implementation guide** from the Phase 1 RFC spec, integrated into the project and ready to drive implementation (Phase 3). Use **platonic-impl-guide** as specified in the README.

## Inputs

- **RFC spec**: From Phase 1 (default `specs/`, e.g. `rfc-NNN-<title>.md`).
- **RFC number/index** (optional): If the user has not specified for which RFC to create the impl guide, ask (e.g., "For which RFC should I create the implementation guide?").
- **Target module/language/framework**: From user or inferred from codebase.

## Process

### Step 1: Identify RFC and Scope

- If not specified, ask the user which RFC (by number/index) should get an implementation guide.
- Determine target module/crate/package and language/framework (from user or existing codebase).

### Step 2: Create Implementation Guide via platonic-impl-guide

- **Use the platonic-impl-guide skill** to create the implementation guide.
- Read `skills/platonic-impl-guide/references/create-guide.md` and follow it.
- Inputs:
  - RFC document path (e.g., `specs/rfc-001-authentication.md`)
  - Target module name
  - Language and optional framework
  - Output path: default `docs/impl/` (e.g., `docs/impl/rfc-001-auth-impl.md`)

### Step 3: Integrate into Project

- Save the guide under the default location `docs/impl/` so it is part of the project’s documentation and can be followed in Phase 3.

## Output

- Implementation guide document in `docs/impl/` (e.g., `rfc-NNN-<feature>-impl.md`).
- Guide is concrete, language- and framework-aware, and does not contradict the RFC.

## Default Location

- `docs/impl/`

## Handoff to Phase 3

- Confirm the path to the implementation guide.
- Proceed to Phase 3: coding agents will implement following this guide and the RFC.
