# Phase 4: Spec Compliance Review

## Current Phase

**[Phase 4] Spec Compliance Review**

## Objective

**Review the implementation** against the targeted RFC (both the formal spec and the implementation guide) using **platonic-code-review**, and produce a compliance report.

## Inputs

- **Code**: Implemented in Phase 3 (relevant directories/modules).
- **RFC spec(s)**: From Phase 1 (e.g., `docs/specs/rfc-NNN-<title>.md`).
- **Implementation guide(s)**: From Phase 2 (e.g., `docs/impl/rfc-NNN-<feature>-impl.md`).

## Process

### Step 1: Call platonic-code-review

- **Use the platonic-code-review skill** to review:
  - The **code implementation** from Phase 3.
  - The **targeted RFC spec** (docs/specs).
  - The **targeted impl RFC/implementation guide** (docs/impl).
- Read `skills/platonic-code-review/references/REFERENCE.md` (or the skill’s review procedure) and invoke the skill accordingly.
- Scope the review to the RFC and impl guide used in this workflow so the report is focused.

### Step 2: Produce Report

- platonic-code-review produces a review/compliance report (default: report-only, no code modification).
- Summarize for the user: what matches, what is missing, what is inconsistent.

## Output

- **Review and compliance report** (from platonic-code-review).
- Clear list of findings and recommended actions; ask the user before making any code changes.

## Handoff to FINISHED

- Once the review is complete, mark the workflow as **FINISHED** and provide a short summary and any follow-up recommendations.
