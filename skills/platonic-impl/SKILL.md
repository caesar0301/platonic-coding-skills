---
name: platonic-impl
description: Translate RFC specifications into concrete implementation guides and then implement them as code. Manages the full implementation lifecycle from spec analysis through architecture design, coding plan, and code with tests. Use when creating implementation guides, implementing features from specs, or running the full spec-to-code pipeline.
license: MIT
metadata:
  version: "1.1.0"
  author: "Xiaming Chen"
  category: "implementation"
---

# Platonic Implementation

Translate RFC specifications into concrete implementation guides and realize them as working code with tests.

## When to Use This Skill

Use this skill when you need to:

- **Translate** RFC specifications into implementation-ready architecture guides
- **Implement** features end-to-end from spec through code with tests
- **Create** detailed technical architecture for a feature
- **Execute** the full implementation sub-workflow: spec analysis, impl guide, coding plan, coding
- **Validate** an implementation guide against its source RFC
- **Update** an implementation guide when its source RFC changes

Keywords: implementation guide, technical design, architecture, RFC implementation, module design, coding, code generation, unit tests, integration tests, coding plan

## What This Skill Does

This skill manages the **full implementation lifecycle**:

```
RFC Specification (abstract, what)
        |
        v
Implementation Guide (concrete, how)     Step 1: Design
        |
        v
Coding Plan (task breakdown)              Step 2: Plan
        |
        v
Code + Tests (executable, verified)       Step 3: Build
```

### Implementation Sub-Workflow (Default)

When invoked for full implementation, the skill follows this sub-workflow:

| Step | Activity | Confirmation Gate | Output |
|------|----------|-------------------|--------|
| **1. Spec Analysis** | Read RFC, extract requirements, constraints, invariants | None | Requirements checklist |
| **2. Impl Guide** | Design concrete architecture, types, interfaces | **User confirms** (default) | `docs/impl/<guide>.md` |
| **3. Coding Plan** | Break down into ordered tasks with file-level changes | **User confirms** (default) | Coding plan |
| **4. Coding** | Write code following guide, include unit and integration tests | None | Source code + tests |

### Confirmation Gates

By default, the skill pauses for user confirmation after the impl guide and coding plan steps. This behavior can be adjusted:

- **Default (recommended)**: Confirm after impl guide AND coding plan
- **Auto mode**: User explicitly requests no confirmations (e.g., "implement without stopping")
- **Smart skip**: For trivially small changes (single-file, < ~50 lines of implementation), the skill MAY skip the coding plan confirmation and proceed directly

The skill determines whether to request confirmation based on:

1. **Explicit user instruction**: If the user says "just do it" or "no confirmations", skip gates
2. **Scope assessment**: Larger scope (multi-file, new modules) always confirms; trivial scope may skip coding plan
3. **Ambiguity**: When RFC requirements are ambiguous or have multiple valid interpretations, always confirm

## Core Principles

### 1. Spec Compliance (Non-Negotiable)

Implementation guides **MUST NOT** contradict RFC specifications:

- All invariants from specs must be preserved
- All required behaviors must be implemented
- All constraints must be respected
- If a spec is unclear, document the interpretation

### 2. Concrete Over Abstract

Unlike RFCs which define "what", implementation guides define "how":

- Specific module/crate/package structure
- Concrete type definitions with fields
- Actual function signatures
- Real dependency relationships
- Specific storage formats and schemas

### 3. Language and Framework Awareness

Implementation guides and code are technology-specific:

- Use idiomatic patterns for the target language
- Leverage framework conventions and capabilities
- Follow project-established coding standards
- Reference actual libraries and dependencies

### 4. Traceability

Every implementation decision traces back to specs:

- Reference source RFCs explicitly
- Document which spec requirements each component satisfies
- Explain deviations or interpretations

### 5. Test Coverage

All implementations include tests:

- **Unit tests** for individual components, types, and functions
- **Integration tests** for cross-component behavior and data flow
- Tests verify spec requirements, not just code correctness

## Implementation Guide Structure

An implementation guide follows this structure:

```markdown
# [Feature] Implementation Architecture

> Implementation guide for [feature] in [project].
> 
> **Crate/Module**: `module-name`
> **Source**: Derived from RFC-NNNN (Title)
> **Related RFCs**: RFC-XXXX, RFC-YYYY

---

## 1. Overview
## 2. Architectural Position
## 3. Module Structure
## 4. Core Types
## 5. Key Interfaces/Traits
## 6. Implementation Details
## 7. Error Handling
## 8. Configuration
## 9. Testing Strategy
## 10. Migration/Compatibility
```

## Available Operations

| Operation | Reference File | Purpose |
|-----------|----------------|---------|
| **Full Impl** | `full-impl.md` | End-to-end: spec → guide → plan → code + tests |
| **Create Guide** | `create-guide.md` | Create implementation guide from RFC (guide only) |
| **Implement Code** | `implement-code.md` | Implement code from existing guide (code only) |
| **Validate Guide** | `validate-guide.md` | Check guide against RFC for contradictions |
| **Update Guide** | `update-guide.md` | Update guide when RFC changes |

See [references/REFERENCE.md](references/REFERENCE.md) for detailed operation guides.

## Templates

Templates are provided in `assets/`:

- `impl-guide-template.md` - Full implementation guide template
- `coding-plan-template.md` - Coding plan template

## Usage Examples

### Example 1: Full Implementation (Default Workflow)

```
Use platonic-impl to implement RFC-0042 (Message Queue Protocol) 
targeting the acme-queue module. Use Rust with Tokio.
```

**Result**: Agent analyzes spec, creates impl guide (waits for confirmation), generates coding plan (waits for confirmation), then implements code with tests.

### Example 2: Create Implementation Guide Only

```
Use platonic-impl to create an implementation guide for
RFC-001 (Authentication) targeting the auth module. Use TypeScript
and the existing Express patterns in this repo.
```

**Result**: Implementation guide with module structure, types, interfaces, and implementation details aligned with the RFC.

### Example 3: Implement from Existing Guide

```
Use platonic-impl to implement code from docs/impl/RFC-0001-impl.md
following docs/specs/RFC-0001.md. Include unit and integration tests.
```

**Result**: Code + tests that match the implementation guide and the RFC.

### Example 4: Full Implementation, No Confirmations

```
Use platonic-impl to implement RFC-003 end-to-end without stopping 
for confirmation. Include tests.
```

**Result**: Agent runs the full sub-workflow automatically without pausing.

### Example 5: Validate Existing Guide

```
Use platonic-impl to validate that docs/impl/queue_impl.md
does not contradict RFC-0042 specifications.
```

**Result**: Validation report confirming the guide is spec-compliant or listing contradictions to fix.

### Example 6: Update Guide After RFC Change

```
Use platonic-impl to update the implementation guide
after RFC-0042 was revised to add new message priority levels.
```

**Result**: Updated guide synchronized with the new RFC, re-validated for compliance.

## Best Practices

1. **Read the RFC first**: Understand the specification completely before designing implementation
2. **Check existing patterns**: Look at how similar features are implemented in the project
3. **Document decisions**: Explain why specific implementation choices were made
4. **Keep it current**: Update guides when RFCs or implementations change
5. **Be specific**: Vague guides are not useful; include actual types and signatures
6. **Test coverage**: Always include both unit and integration tests
7. **Respect confirmation gates**: Unless told otherwise, always pause for user review

## Dependencies

- Read access to RFC specifications
- Understanding of target language and framework
- Knowledge of project architecture and conventions
- Write access to `docs/impl/` or designated impl-guide directory
- Write access to source code directories for coding operations
