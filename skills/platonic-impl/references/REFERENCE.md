# Platonic Implementation — Reference

This document provides detailed guidance for all implementation operations.

## Operations Overview

| Operation | Purpose | Input | Output |
|-----------|---------|-------|--------|
| Full Impl | End-to-end implementation | RFC, target module | Impl guide + code + tests |
| Create Guide | Generate impl guide from RFC | RFC document, target module | Implementation guide |
| Implement Code | Write code from existing guide | Impl guide, RFC | Source code + tests |
| Validate Guide | Check guide against RFC | Impl guide, RFC document | Validation report |
| Update Guide | Sync guide with RFC changes | Impl guide, updated RFC | Updated guide |

---

## Operation: Full Impl (Default Workflow)

**Reference**: `full-impl.md`

Runs the complete implementation sub-workflow: spec analysis, impl guide design, coding plan, and coding with tests. This is the default operation when the user asks to "implement" an RFC.

### Sub-Workflow

1. **Spec Analysis** → Requirements checklist
2. **Impl Guide** → Architecture document (confirmation gate)
3. **Coding Plan** → Task breakdown (confirmation gate)
4. **Coding** → Source code + unit and integration tests

### When to Use

- User asks to "implement RFC-NNNN"
- User invokes platonic-workflow Phase 2
- User wants end-to-end from spec to code

---

## Operation: Create Guide

**Reference**: `create-guide.md`

Creates a new implementation guide from an RFC specification without proceeding to code.

### Prerequisites

1. RFC document must exist and be readable
2. Target module/crate name must be specified
3. Target language and framework must be known

### Process

1. Read and analyze the RFC specification
2. Identify all requirements, constraints, and invariants
3. Design concrete implementation architecture
4. Map RFC concepts to language-specific constructs
5. Generate implementation guide using template

---

## Operation: Implement Code

**Reference**: `implement-code.md`

Writes code from an existing implementation guide, including tests.

### Prerequisites

1. Implementation guide must exist
2. Source RFC must be available for reference
3. Target codebase and conventions must be understood

### Process

1. Read implementation guide and source RFC
2. Generate coding plan (task breakdown)
3. Confirm plan with user (unless auto-mode)
4. Implement code following the guide
5. Write unit and integration tests

---

## Operation: Validate Guide

**Reference**: `validate-guide.md`

Validates that an implementation guide does not contradict its source RFC.

### Validation Checks

1. **Invariant Preservation**: All RFC invariants are respected
2. **Requirement Coverage**: All RFC requirements are addressed
3. **Constraint Compliance**: All RFC constraints are followed
4. **Terminology Consistency**: Uses RFC-defined terms correctly
5. **No Contradictions**: No statements that conflict with RFC

### Output

Validation report with:
- Compliance status (PASS/FAIL)
- List of verified requirements
- Any contradictions found
- Recommendations for fixes

---

## Operation: Update Guide

**Reference**: `update-guide.md`

Updates an implementation guide when its source RFC changes.

### Process

1. Identify RFC changes (diff or changelog)
2. Analyze impact on implementation guide
3. Update affected sections
4. Re-validate against updated RFC
5. Document changes in guide revision history

---

## Best Practices for All Operations

### Traceability

Always maintain clear links between:
- RFC sections → Guide sections
- RFC requirements → Implementation components
- RFC invariants → Code constraints
- Guide sections → Source code files

### Consistency

- Use terminology from `docs/specs/rfc-namings.md`
- Follow project coding standards
- Match existing implementation patterns

### Completeness

- Address all RFC requirements
- Include error handling
- Document edge cases
- Specify testing approach

### Test Requirements

All coding operations MUST produce:
- **Unit tests**: Test individual components in isolation
- **Integration tests**: Test cross-component behavior and data flow
- Tests MUST verify spec requirements, not just code correctness
