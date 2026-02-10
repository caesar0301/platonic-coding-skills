# {{FEATURE_NAME}} Implementation Architecture

> Implementation guide for {{FEATURE_DESCRIPTION}} in {{PROJECT_NAME}}.
>
> **Module**: `{{MODULE_NAME}}`
> **Source**: Derived from {{SOURCE_RFCS}}
> **Related RFCs**: {{RELATED_RFCS}}
> **Language**: {{LANGUAGE}}
> **Framework**: {{FRAMEWORK}}

---

## 1. Overview

{{OVERVIEW_DESCRIPTION}}

### 1.1 Purpose

This document specifies the **implementation architecture** for {{FEATURE_NAME}} as defined in {{PRIMARY_RFC}}. It provides:

- Concrete module structure
- Type definitions with full field specifications
- Interface definitions
- Implementation details and algorithms
- Error handling strategy
- Testing approach

### 1.2 Scope

**In Scope**:
- {{IN_SCOPE_ITEM_1}}
- {{IN_SCOPE_ITEM_2}}

**Out of Scope**:
- {{OUT_OF_SCOPE_ITEM_1}}
- {{OUT_OF_SCOPE_ITEM_2}}

### 1.3 Spec Compliance

This implementation guide **supersedes** RFC specifications with concrete details but **MUST NOT contradict** them. All invariants and requirements from source RFCs are preserved.

---

## 2. Architectural Position

### 2.1 System Context

{{SYSTEM_CONTEXT_DESCRIPTION}}

### 2.2 Dependency Graph

```
{{DEPENDENCY_GRAPH}}
```

### 2.3 Module Responsibilities

| Module | Responsibility | Dependencies |
|--------|----------------|--------------|
| `{{MODULE_1}}` | {{RESPONSIBILITY_1}} | {{DEPS_1}} |

---

## 3. Module Structure

```
{{MODULE_NAME}}/
├── {{FILE_1}}              # {{FILE_1_DESCRIPTION}}
├── {{FILE_2}}              # {{FILE_2_DESCRIPTION}}
└── {{SUBMODULE_1}}/
    ├── {{SUB_FILE_1}}
    └── {{SUB_FILE_2}}
```

---

## 4. Core Types

### 4.1 {{TYPE_1_NAME}}

{{TYPE_1_DESCRIPTION}}

```{{LANGUAGE}}
{{TYPE_1_DEFINITION}}
```

| Field | Type | Description |
|-------|------|-------------|
| `{{FIELD_1}}` | `{{FIELD_1_TYPE}}` | {{FIELD_1_DESC}} |

---

## 5. Key Interfaces

### 5.1 {{INTERFACE_1_NAME}}

{{INTERFACE_1_DESCRIPTION}}

```{{LANGUAGE}}
{{INTERFACE_1_DEFINITION}}
```

| Method | Description |
|--------|-------------|
| `{{METHOD_1}}` | {{METHOD_1_DESC}} |

---

## 6. Implementation Details

### 6.1 {{DETAIL_1_NAME}}

{{DETAIL_1_DESCRIPTION}}

---

## 7. Error Handling

### 7.1 Error Types

```{{LANGUAGE}}
{{ERROR_TYPE_DEFINITION}}
```

### 7.2 Error Handling Strategy

| Error Category | Handling Approach |
|----------------|-------------------|
| {{ERROR_CAT_1}} | {{HANDLING_1}} |

---

## 8. Configuration

### 8.1 Configuration Options

```{{LANGUAGE}}
{{CONFIG_TYPE_DEFINITION}}
```

| Option | Default | Description |
|--------|---------|-------------|
| `{{OPTION_1}}` | `{{DEFAULT_1}}` | {{OPTION_1_DESC}} |

---

## 9. Testing Strategy

### 9.1 Unit Tests

| Component | Test Focus |
|-----------|------------|
| `{{COMPONENT_1}}` | {{TEST_FOCUS_1}} |

### 9.2 Integration Tests

{{INTEGRATION_TEST_DESCRIPTION}}

---

## 10. Migration / Compatibility

{{MIGRATION_DESCRIPTION}}

---

## Appendix A: RFC Requirement Mapping

| RFC Requirement | Guide Section | Implementation |
|-----------------|---------------|----------------|
| {{REQ_1}} | Section {{SEC_1}} | {{IMPL_1}} |

---

## Appendix B: Revision History

| Date | RFC Version | Changes |
|------|-------------|---------|
| {{DATE}} | {{RFC_VERSION}} | Initial guide |
