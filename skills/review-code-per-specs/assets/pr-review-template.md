# Spec-to-Code Review Report

**PR/Branch**: [Title/Name]  
**Author**: [Name] | **Reviewer**: [Name] | **Date**: [YYYY-MM-DD]  
**Files Changed**: X | **Lines**: +A / -B

**Review Level**: [ ] Basic | [ ] Detailed | [ ] Comprehensive

---

## Executive Summary

**What This PR Does**: [Brief description]

**Spec Compliance**: [Overall assessment of spec alignment]

**Status Summary**:
- ✅ Fully Compliant: X items
- ⚠️ Partial/Minor Issues: Y items  
- ❌ Non-Compliant/Missing: Z items

**Recommendation**: [ ] Approve | [ ] Approve with changes | [ ] Request changes | [ ] Reject

---

## Critical Issues 🔴

**[Must fix before merge]**

**1. [Issue Title]**
- **Spec**: [Document, Section]
- **Code**: `path/file:line`
- **Issue**: [Description]
- **Impact**: [Security/Data loss/Breaking bug]
- **Fix**: [Specific recommendation or code snippet]

---

## High Priority Issues 🟠

**[Should fix before merge]**

**1. [Issue Title]**
- **Spec**: [Document, Section]
- **Code**: `path/file:line`
- **Issue**: [Description]
- **Fix**: [Recommendation]

---

## Medium Priority 🟡

**[Fix during sprint/next refactor]**

- **[Component]**: [Issue] - `path/file:line`
- **[Component]**: [Issue] - `path/file:line`

---

## Low Priority 🟢

**[Nice to have]**

- [Suggestion 1]
- [Suggestion 2]

---

## Spec Compliance Checklist

| Spec Item | Status | Code Location | Notes |
|-----------|--------|---------------|-------|
| [Feature 1] | ✅ / ⚠️ / ❌ | `path/file` | [Note] |
| [Feature 2] | ✅ / ⚠️ / ❌ | `path/file` | [Note] |
| [Feature 3] | ✅ / ⚠️ / ❌ | `path/file` | [Note] |

**Legend**: ✅ Fully compliant | ⚠️ Partial/Issues | ❌ Missing/Non-compliant

---

## Detailed Analysis

### Functional Consistency
- **Matches Spec**: [What works correctly]
- **Issues**: [What doesn't match]

### Data/API Consistency  
- **Matches Spec**: [Correct implementations]
- **Issues**: [Mismatches with spec]

### Missing Implementations
- [Specified feature not implemented]
- [Another missing feature]

### Undocumented Features
- [Code feature without spec]
- [Another undocumented feature]

### Test Coverage
- **Coverage**: X% | **Spec Requirements Tested**: Y/Z
- **Missing Tests**: [List]
- **Edge Cases**: [List untested scenarios from spec]

---

## Quality Metrics

| Category | Rating | Key Points |
|----------|--------|-----------|
| **Spec Compliance** | ⭐⭐⭐☆☆ | [Notes] |
| **Completeness** | ⭐⭐⭐⭐☆ | [Notes] |
| **Correctness** | ⭐⭐⭐⭐⭐ | [Notes] |
| **Test Alignment** | ⭐⭐⭐☆☆ | [Notes] |

---

## Positive Observations ✅

- ✓ [What's implemented well per spec]
- ✓ [Good practice noted]
- ✓ [Correct implementation highlighted]

---

## Recommendations by Priority

### Immediate (Before Merge)
1. **[Action]** - [Reason based on spec]
2. **[Action]** - [Reason based on spec]

### Short-term (Current Sprint)
1. **[Action]** - [Spec reference]
2. **[Action]** - [Spec reference]

### Long-term (Backlog)
1. **[Action]** - [Rationale]
2. **[Action]** - [Rationale]

---

## Specifications Reviewed

- [RFC-001: Title](path) - v1.2, Section X.Y
- [requirements.md](path) - Updated YYYY-MM-DD
- [API-spec.yaml](path) - v2.0

---

## Decision

**Final Recommendation**: [Choose one]
- [ ] ✅ **Approve** - Fully compliant with specs
- [ ] ⚠️ **Approve with Minor Changes** - Small fixes acceptable after merge
- [ ] 🔄 **Request Changes** - Issues must be fixed before merge
- [ ] ❌ **Reject** - Significant spec violations or missing requirements

**Next Steps**: [What needs to happen]

**Note**: This review validates spec compliance. No code was modified (report-only mode).

---

**Review Completed**: [YYYY-MM-DD HH:MM]  
**Tool**: review-code-per-specs skill

## Additional Context

[Any questions, clarifications, or additional notes]
