# Implementation Guide Operations Reference

This document provides detailed guidance for all implementation guide operations.

## Operations Overview

| Operation | Purpose | Input | Output |
|-----------|---------|-------|--------|
| Create Guide | Generate new impl guide from RFC | RFC document, target module | Implementation guide |
| Validate Guide | Check guide against RFC | Impl guide, RFC document | Validation report |
| Update Guide | Sync guide with RFC changes | Impl guide, updated RFC | Updated guide |

---

## Operation: Create Guide

**Reference**: `create-guide.md`

Creates a new implementation guide from an RFC specification.

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

### Consistency

- Use terminology from `specs/rfc-namings.md`
- Follow project coding standards
- Match existing implementation patterns

### Completeness

- Address all RFC requirements
- Include error handling
- Document edge cases
- Specify testing approach
