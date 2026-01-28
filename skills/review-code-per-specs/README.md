# Review Code Per Specs

An Agent Skill for validating code implementation against specifications to ensure consistency and completeness.

## What This Skill Does

This skill validates that your code correctly implements your specifications:

- **Validates** code matches RFC specifications
- **Checks** feature completeness against requirements
- **Identifies** gaps where specs exist but code doesn't
- **Finds** discrepancies where implementation differs from specs
- **Generates** detailed review reports **without modifying code**

## Not a General Code Reviewer

This is NOT a general code quality or security reviewer. It specifically focuses on:

✅ **Spec-to-Code Consistency** - Does code implement what specs describe?  
✅ **Completeness** - Are all specified features implemented?  
✅ **Correctness** - Does implementation match spec requirements?  
❌ NOT code quality, performance, or security review (use other tools for that)

## Quick Start

### Review Implementation Against Specs

```
Use review-code-per-specs to verify that src/auth/ correctly 
implements all requirements from specs/rfc-001-authentication.md
```

### Check Feature Completeness

```
Use review-code-per-specs to check if all features specified 
in specs/rfc-005-payment-system.md are implemented in src/payments/
```

### Gap Analysis

```
Use review-code-per-specs to identify gaps between all RFCs 
in ./specs/ and the implementation in ./src/
```

## Review Procedure

The skill follows a systematic 6-step process:

### 1. Understand Specifications

Read and analyze relevant spec documents:
- RFC documents
- Requirements documents
- Design specifications
- API contracts

### 2. Generate Functionality Checklist

Extract testable requirements from specs:
- List all specified features
- List all specified behaviors
- List all APIs and interfaces
- List all data structures
- List all business rules

### 3. Map Specs to Code

Identify implementation locations:
- Find relevant source files
- Map features to modules
- Identify entry points
- Understand code structure

### 4. Review Implementation

For each checklist item, verify:
- ✅ **Implemented** - Correctly and completely
- ⚠️ **Partial** - Implemented but incomplete
- ❌ **Missing** - Specified but not found
- 🔍 **Unclear** - Needs investigation

### 5. Identify Discrepancies

Document inconsistencies:
- Implementation differs from spec
- Missing features
- Extra undocumented features
- Incorrect behaviors
- Incomplete implementations

### 6. Generate Report

Create structured report with:
- Executive summary
- Checklist with status
- Detailed findings
- Code references
- Recommendations

## Default Behavior

### Report Generation (Default)

**By default, this skill generates reports WITHOUT modifying code:**

- Documents all findings
- Provides specific code references
- Lists inconsistencies and gaps
- Recommends actions
- Asks for user approval before any changes

### Code Modification (Explicit Only)

Code is only modified when user explicitly requests:
- "Fix the inconsistencies"
- "Implement the missing features"
- "Update code to match specs"

Otherwise, report-only mode is used.

## Review Levels

### Level 1: Basic Compliance

Quick check for major features:
- Core functionality exists
- Main APIs are implemented
- Basic requirements met

**Time**: 5-10 minutes

### Level 2: Detailed Verification

Thorough feature-by-feature review:
- All specified behaviors
- Edge cases and error handling
- Data structures and interfaces
- Business rule implementation

**Time**: 30-60 minutes

### Level 3: Comprehensive Audit

Deep analysis with full validation:
- Implementation details
- Algorithm correctness
- Performance requirements
- All constraints and validations
- Test coverage alignment

**Time**: 2+ hours

## Report Format

Generated reports follow this structure:

```markdown
# Spec-to-Code Review Report
Date: YYYY-MM-DD
Reviewer: AI Agent

## Summary
- Specifications: X reviewed
- Code Modules: Y reviewed
- Consistency Rate: Z%

## Functionality Checklist

### Feature Category A
- ✅ Feature A1 - Fully implemented
  - Spec: rfc-001.md, Section 3.1
  - Code: src/module/feature-a1.ts
  - Status: Matches specification exactly

- ⚠️ Feature A2 - Partially implemented
  - Spec: rfc-001.md, Section 3.2
  - Code: src/module/feature-a2.ts
  - Issue: Error handling incomplete
  - Missing: Input validation for edge case X

- ❌ Feature A3 - Not implemented
  - Spec: rfc-001.md, Section 3.3
  - Status: No implementation found
  - Impact: Critical feature missing

### Feature Category B
...

## Critical Inconsistencies

### 1. Authentication Flow Mismatch
**Severity**: Critical  
**Spec**: rfc-001-auth.md, Section 4.2  
**Code**: src/auth/login.ts:45-78  
**Issue**: Code uses Basic Auth, spec requires OAuth2  
**Impact**: Security and compliance violation

## Missing Implementations

### 1. Password Reset Feature
**Spec**: rfc-001-auth.md, Section 5.3  
**Status**: Not found in codebase  
**Impact**: High - User-facing feature missing

## Extra Implementations

### 1. Social Login
**Code**: src/auth/social-login.ts  
**Status**: No corresponding specification  
**Note**: Feature not documented in specs

## Recommendations

### Priority 1: Critical (Fix Immediately)
1. Update authentication to OAuth2 per rfc-001-auth.md Section 4.2
2. Implement missing password reset per rfc-001-auth.md Section 5.3

### Priority 2: High (Fix This Sprint)
1. Complete error handling for Feature A2
2. Add input validation for edge cases

### Priority 3: Medium (Address Soon)
1. Document social login feature in specs or remove if not needed
2. Add missing test cases for Feature X

### Priority 4: Low (Nice to Have)
1. Refactor Feature Y for better alignment with spec
2. Update inline documentation

## Next Steps

**IMPORTANT**: This is a report only. No code has been modified.

To proceed:
1. Review findings above
2. Prioritize which issues to address
3. If you want code modifications, explicitly request them
4. Otherwise, use this report to guide manual updates
```

## Examples

### Example 1: Single RFC Review

**User Request:**
```
Use review-code-per-specs to review src/auth/ against 
specs/rfc-001-authentication.md
```

**Output:**
- Checklist of all authentication features from RFC
- Status of each feature (implemented/partial/missing)
- Detailed report with code references
- No code modifications

### Example 2: Module Completeness Check

**User Request:**
```
Use review-code-per-specs to verify that src/api/payments/ 
fully implements all requirements in specs/rfc-005-payments.md
```

**Output:**
- Complete feature checklist
- Gap analysis (what's missing)
- Discrepancy report (what's different)
- Recommendations for fixes

### Example 3: Comprehensive Codebase Audit

**User Request:**
```
Use review-code-per-specs to audit the entire codebase against 
all RFCs in ./specs/. Generate a comprehensive report.
```

**Output:**
- Multi-RFC analysis
- Cross-module consistency check
- Overall compliance metrics
- Prioritized action plan

### Example 4: Bi-Directional Check

**User Request:**
```
Use review-code-per-specs to perform bi-directional analysis:
1. Check what specs are not implemented
2. Check what code is not specified
```

**Output:**
- Missing implementations list
- Undocumented features list
- Gap analysis report
- Recommendations for specs or code updates

## Advanced Features

### Cross-Reference Analysis

- **Spec → Code**: Find unimplemented specifications
- **Code → Spec**: Find undocumented implementations
- **Dependency Check**: Verify integration point consistency

### Test Coverage Integration

- Compare test cases with spec requirements
- Identify untested specified behaviors
- Suggest test scenarios based on specs

### Version Tracking

- Track which code version implements which spec version
- Identify outdated implementations
- Suggest updates for spec changes

## Integration with Other Skills

### Works Great With

**platonic-coding-specs**:
```
1. Use platonic-coding-specs to maintain RFC specifications
2. Use review-code-per-specs to validate code against those RFCs
3. Use platonic-coding-specs to update history with review findings
```

**Testing Skills**:
```
1. Use review-code-per-specs to identify untested requirements
2. Generate test cases for missing coverage
3. Validate test suite completeness
```

## Best Practices

### Before Review

1. Ensure specs are up-to-date
2. Identify scope (which specs, which code)
3. Choose appropriate review level
4. Clarify if code modifications are allowed

### During Review

1. Read specs thoroughly first
2. Create comprehensive checklist
3. Document all findings with code references
4. Be systematic and objective
5. Don't make assumptions

### After Review

1. Review generated report
2. Prioritize findings
3. Decide which issues to address
4. Request code modifications explicitly if needed
5. Update specs if code is correct but undocumented

## File Structure

```
review-code-per-specs/
├── SKILL.md              # Agent Skills format definition
├── README.md             # This file
├── references/           # Detailed procedures
│   └── REFERENCE.md      # Complete review guide
└── assets/               # Templates and checklists
    ├── review-checklist.md
    └── report-template.md
```

## Troubleshooting

**Q: Why didn't it modify my code?**  
A: By default, this skill only generates reports. Request modifications explicitly.

**Q: How do I get more detailed analysis?**  
A: Request Level 3 comprehensive audit or specify areas to deep dive.

**Q: What if specs are outdated?**  
A: The skill will report discrepancies. You can then decide whether to update specs or code.

**Q: Can it review without specs?**  
A: No, this skill requires specifications to validate against.

## Documentation

- **[SKILL.md](SKILL.md)** - Agent Skills format definition
- **[references/REFERENCE.md](references/REFERENCE.md)** - Detailed procedures and examples

## License

MIT - See [LICENSE](../../LICENSE) for details
