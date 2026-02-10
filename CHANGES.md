# Project Restructuring Summary

This document summarizes the changes made to align the platonic-coding-skills project with the [Agent Skills](https://agentskills.io) standard.

## Date
2026-02-10

## Version 1.0.2 — New Skill: platonic-init & Scope Refinements (2026-02-10)

### New Skill: platonic-init

**Added:** `platonic-init` skill for initializing the Platonic Coding system on any project.

**Purpose:**
- Bootstrap new (greenfield) projects with `.platonic.yml`, specs directory, templates, and impl guide scaffolding
- Adopt Platonic Coding for existing codebases by scanning code and recovering design specs as Draft RFCs
- Propose modular RFC dependency graphs (Conceptual, Architecture, and optionally Impl Interface Design)
- Populate rfc-index.md, rfc-namings.md, and rfc-history.md from recovered specs

**Operations:**
1. **Scaffold Project** – Create directories, config, and templates
2. **Scan Project** – Systematically analyze existing codebase
3. **Plan Modular Specs** – Propose RFC dependency graph from scan results
4. **Recover Conceptual** – Generate conceptual design spec from code
5. **Recover Architecture** – Generate architecture design spec from code
6. **Recover Impl Interface** – Generate impl interface design spec from code (optional)

**File Structure:**
```
platonic-init/
├── SKILL.md              # Agent Skills definition
├── assets/               # Templates (12 files)
│   ├── platonic.yml.template
│   ├── rfc-standard.md.template
│   ├── rfc-history.md.template
│   ├── rfc-index.md.template
│   ├── rfc-namings.md.template
│   ├── rfc-template.md
│   ├── conceptual-design.md.template
│   ├── architecture-design.md.template
│   ├── impl-interface-design.md.template
│   ├── impl-guide-template.md
│   ├── impl-readme.md.template
│   └── drafts-readme.md.template
└── references/           # Operation guides (7 files)
    ├── REFERENCE.md
    ├── scaffold-project.md
    ├── scan-project.md
    ├── plan-modular-specs.md
    ├── recover-conceptual.md
    ├── recover-architecture.md
    └── recover-impl-interface.md
```

**Key Features:**
- Two modes: Greenfield Init (new projects) and Recovery Init (existing codebases)
- Three spec kinds: Conceptual Design, Architecture Design, Impl Interface Design
- User confirmation required before generating RFCs
- Bounded RFC count (default max: 5) to keep specs focused and manageable

### Scope Change: platonic-specs

**Changed:** `platonic-specs` no longer handles project initialization.

- Initialization (scaffolding directories, config, templates) has been extracted into `platonic-init`
- `platonic-specs` now focuses exclusively on **validation and management** of existing specs:
  - Refine specifications
  - Generate history, index, and terminology files
  - Validate consistency and cross-references
  - Check taxonomy and standard compliance

### Version Bumps

All skills updated to **version 1.0.2**:
- `platonic-init` — 1.0.2 (new)
- `platonic-specs` — 1.0.1 → 1.0.2
- `platonic-impl-guide` — 1.0.1 → 1.0.2
- `platonic-code-review` — 1.0.1 → 1.0.2
- `platonic-workflow` — 1.0.1 → 1.0.2

### Manifesto Renamed

- `PLATONIC_CODING_MANIFESTO.md` → `MANIFESTO.md`
- `platonic-coding-manifesto.png` → `manifesto.png`

### Also Updated

- Root `README.md` – Added platonic-init to Available Skills, updated platonic-specs description, added init examples, updated workflow diagram
- `.claude-plugin/marketplace.json` – Registered platonic-init skill, updated versions and descriptions

---

## Date
2026-02-01

## New Skill: platonic-impl-guide (2026-02-01)

**Added:** `platonic-impl-guide` skill for creating implementation guides from RFC specifications.

**Purpose:**
- Translate RFC specifications into concrete, implementation-ready designs
- Create detailed technical architecture for features
- Document language-specific and framework-specific implementation decisions
- Bridge the gap between abstract specs and concrete code

**Operations:**
1. **Create Guide** – Create new implementation guide from RFC
2. **Validate Guide** – Check guide against RFC for contradictions
3. **Update Guide** – Update guide when RFC changes

**File Structure:**
```
platonic-impl-guide/
├── SKILL.md              # Agent Skills definition
├── references/           # Operation guides
│   ├── REFERENCE.md
│   ├── create-guide.md
│   ├── update-guide.md
│   └── validate-guide.md
└── assets/
    └── impl-guide-template.md
```

**Key Features:**
- Spec-compliant: guides MUST NOT contradict RFCs
- Language-aware and framework-aware
- Project-specific alignment with existing architecture
- Traceability from implementation decisions back to specs

**Also updated:**
- Root `README.md` – Added platonic-impl-guide to Available Skills, examples, and workflows; all skill links point to SKILL.md
- `.claude-plugin/marketplace.json` – Registered platonic-impl-guide skill

---

## Date
2026-01-28

## Changes Overview

### 1. Restructured platonic-specs Skill

**Directory Changes:**
- ✅ Renamed `prompts/` → `references/` (Agent Skills standard)
- ✅ Renamed `templates/` → `assets/` (Agent Skills standard)

**Files Updated:**
- ✅ `SKILL.md` - Added metadata (version, author, category, license), improved structure and docs
- ✅ `references/REFERENCE.md` - NEW: Comprehensive operation guide (418 lines)
- ✅ `references/init-specs.md` - Updated paths (templates → assets)

**Key Improvements:**
- Follows Agent Skills specification format
- Better organized with progressive disclosure
- Comprehensive reference documentation
- Clear metadata in frontmatter

---

### 2. Renamed and Refocused review-code Skill

**Renamed:** `review-code` → `platonic-code-review`

**Focus Changed:**
- ❌ WAS: General code quality, security, performance reviewer
- ✅ NOW: Spec-to-code consistency validator

**New Purpose:**
- Validate code implements specifications correctly
- Check feature completeness against requirements
- Identify gaps (specs without code, code without specs)
- Find discrepancies where implementation differs from specs
- **Default behavior: Generate report WITHOUT modifying code**

**Files Created:**
- ✅ `SKILL.md` - Complete rewrite focusing on spec validation and docs (197 lines)
- ✅ `references/REFERENCE.md` - Detailed review procedures (1000+ lines)
- ✅ `assets/review-checklist.md` - Review checklist template
- ✅ `assets/pr-review-template.md` - PR review template

**Key Features:**
- 6-step review process (Understand → Checklist → Map → Review → Discrepancies → Report)
- Three review levels (Basic, Detailed, Comprehensive)
- Bi-directional analysis (spec→code and code→spec)
- Report generation by default (no code modification unless requested)
- Structured report format with prioritized findings

---

### 3. Updated Configuration Files

**marketplace.json:**
- ✅ Updated to include both skills with proper metadata
- ✅ Added repository information
- ✅ Changed review-code → platonic-code-review
- ✅ Updated skill categories and tags
- ✅ Added compatibility section

**Main README.md:**
- ✅ Complete rewrite following Agent Skills format
- ✅ Professional structure with badges
- ✅ Clear skill descriptions
- ✅ Updated examples
- ✅ Added integration guidance
- ✅ Better documentation links

---

## Skills Summary

### Skill 1: platonic-specs

**Category:** Documentation  
**Version:** 1.0.1  
**Purpose:** Manage RFC-style specifications

**Operations:**
1. Initialize specs folder
2. Refine specifications (comprehensive)
3. Generate history
4. Generate index
5. Generate namings
6. Validate consistency
7. Check taxonomy
8. Check standard compliance

**File Structure:**
```
platonic-specs/
├── SKILL.md              # Agent Skills definition and docs
├── references/            # Reference documentation
│   ├── REFERENCE.md      # Complete guide
│   └── *.md              # 8 operation references
└── assets/               # Templates
    └── *.template        # 5 RFC templates
```

---

### Skill 2: platonic-code-review

**Category:** Validation  
**Version:** 1.0.1  
**Purpose:** Validate code against specifications

**Review Process:**
1. **Understand Specifications** - Read and analyze specs
2. **Generate Functionality Checklist** - Extract testable requirements
3. **Map Specs to Code** - Identify implementation locations
4. **Review Implementation** - Verify each requirement
5. **Identify Discrepancies** - Document inconsistencies
6. **Generate Report** - Create actionable report (no code changes by default)

**Review Levels:**
- **Level 1: Basic Compliance** (5-10 min) - Major features only
- **Level 2: Detailed Verification** (30-60 min) - All specified features
- **Level 3: Comprehensive Audit** (2+ hours) - Deep analysis

**File Structure:**
```
platonic-code-review/
├── SKILL.md              # Agent Skills definition and docs
├── references/            # Review procedures
│   └── REFERENCE.md      # Complete review guide
└── assets/               # Templates
    ├── review-checklist.md
    └── pr-review-template.md
```

---

## Agent Skills Standard Compliance

Both skills now fully comply with [Agent Skills specification](https://agentskills.io/specification):

✅ **SKILL.md format:**
- Required YAML frontmatter (name, description)
- Optional metadata (version, author, license, category)
- Clear body content with instructions

✅ **Directory structure:**
- `SKILL.md` - Required skill definition
- `references/` - Additional documentation (progressive disclosure)
- `assets/` - Templates and resources

✅ **Progressive disclosure:**
1. Metadata (~100 tokens) - Loaded at startup
2. SKILL.md body (< 500 lines) - Loaded when activated
3. References (as needed) - Loaded on demand

✅ **Best practices:**
- Self-documenting
- Portable (just files)
- Extensible
- Compatible with multiple AI agents

---

## Key Principles Applied

### 1. Standards Compliance
- Follows Agent Skills specification exactly
- Uses standard directory structure
- Proper YAML frontmatter

### 2. Progressive Disclosure
- Concise SKILL.md files
- Detailed information in references/
- Templates in assets/

### 3. Clear Documentation
- SKILL.md as primary skill documentation
- Detailed REFERENCE.md guides
- Practical examples

### 4. Default: Report Only
- platonic-code-review generates reports by default
- Never modifies code without explicit user request
- Asks for permission before changes

### 5. Practical Focus
- Real-world use cases
- Clear procedures
- Actionable recommendations

---

## Migration Guide

### For Existing Users

**If you were using platonic-specs:**
- Update any references from `prompts/` to `references/`
- Update any references from `templates/` to `assets/`
- Otherwise, functionality is identical

**If you were using review-code:**
- Skill is now `platonic-code-review`
- Purpose has changed: now validates against specs (not general review)
- For general code review, use other tools

---

## Files Changed

### Modified:
- `.claude-plugin/marketplace.json`
- `README.md`
- `skills/platonic-specs/SKILL.md`
- `skills/platonic-specs/references/init-specs.md`

### Renamed (platonic-specs):
- `prompts/` → `references/`
- `templates/` → `assets/`

### Created:
- `skills/platonic-specs/references/REFERENCE.md`
- `skills/platonic-code-review/` (entire directory)
- `skills/platonic-code-review/SKILL.md`
- `skills/platonic-code-review/references/REFERENCE.md`
- `skills/platonic-code-review/assets/review-checklist.md`
- `skills/platonic-code-review/assets/pr-review-template.md`

### Deleted:
- `.claude-plugin/plugin.json` (obsolete)
- `skills/review-code/` (replaced by platonic-code-review)

---

## Next Steps

1. **Review changes** - Verify all changes are correct
2. **Test skills** - Try both skills with AI agents
3. **Update documentation** - Add any project-specific notes
4. **Commit changes** - Stage and commit when ready
5. **Share** - Publish to marketplace or share with team

---

## Resources

- [Agent Skills Specification](https://agentskills.io/specification)
- [Agent Skills Documentation](https://agentskills.io)
- [Integration Guide](https://agentskills.io/integrate-skills)
- [Example Skills](https://github.com/anthropics/skills)

---

**Restructuring completed:** 2026-01-28  
**Standards followed:** Agent Skills 1.0  
**License:** MIT
