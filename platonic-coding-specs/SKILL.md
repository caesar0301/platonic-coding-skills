---
name: platonic-coding-specs
description: Manage RFC-style specifications with templates, validation, and dynamic generation of history, index, and namings files. Ensures consistency, taxonomy compliance, and standard adherence across all specification documents.
---

# Platonic Coding Specs Skill

A reusable agent skill for managing RFC-style specifications in development projects using AI-driven operations instead of code.

## Overview

This skill abstracts the RFC (Request for Comments) specification management system, providing:

- **Templates** for creating project-specific specification standards
- **AI prompts** for initialization, refinement, and validation
- **Dynamic generation** of history, index, and namings files via AI operations
- **Consistency checks** across all specification documents

## When to Use This Skill

Use this skill when:

- Initializing a new project's specification system
- Refining and validating existing RFC specifications
- Generating or updating history, index, or namings files
- Ensuring consistency between RFC files
- Checking taxonomy and terminology compliance
- Validating RFCs against the standard

## Skill Operations

### 1. Initialize Specs Folder

**Prompt**: Use `prompts/init-specs.md`

Initializes a new specs folder with project-specific templates.

**Inputs**:
- Project name (replaces `{{PROJECT_NAME}}` in templates)
- Target specs directory path

**Outputs**:
- `rfc-standard.md` - RFC specifications guide
- `rfc-history.md` - Change history template
- `rfc-index.md` - RFC index template
- `rfc-namings.md` - Terminology reference template

### 2. Refine Specifications

**Prompt**: Use `prompts/refine-specs.md`

Comprehensive refinement operation that:
- Validates consistency between RFC files
- Checks taxonomy consistency
- Syncs namings with current RFCs
- Ensures compliance with rfc-standard.md
- Generates updated history, index, and namings files

**Inputs**:
- Specs directory path
- Optional: verbose mode for detailed warnings

**Outputs**:
- Updated `rfc-history.md`
- Updated `rfc-index.md`
- Updated `rfc-namings.md`
- Validation report

### 3. Generate History

**Prompt**: Use `prompts/generate-history.md`

Scans RFC files and generates/updates `rfc-history.md` with lifecycle events.

**Inputs**:
- Specs directory path

**Outputs**:
- Updated `rfc-history.md` with chronological change history

### 4. Generate Index

**Prompt**: Use `prompts/generate-index.md`

Generates/updates `rfc-index.md` with current RFC list and quick links.

**Inputs**:
- Specs directory path

**Outputs**:
- Updated `rfc-index.md` with active RFCs table and quick links

### 5. Generate Namings

**Prompt**: Use `prompts/generate-namings.md`

Extracts terminology from active RFCs and updates `rfc-namings.md`.

**Inputs**:
- Specs directory path

**Outputs**:
- Updated `rfc-namings.md` with current terminology

### 6. Validate Consistency

**Prompt**: Use `prompts/validate-consistency.md`

Checks cross-references, dependencies, and metadata consistency.

**Inputs**:
- Specs directory path

**Outputs**:
- List of errors and warnings

### 7. Check Taxonomy

**Prompt**: Use `prompts/check-taxonomy.md`

Verifies consistent use of terminology and checks for deprecated terms.

**Inputs**:
- Specs directory path

**Outputs**:
- Taxonomy consistency report

### 8. Check Standard Compliance

**Prompt**: Use `prompts/check-standard-compliance.md`

Validates RFCs follow rfc-standard.md conventions.

**Inputs**:
- Specs directory path

**Outputs**:
- Compliance report with errors and warnings

## Usage Examples

### Example 1: Initialize a New Project

```
Read prompts/init-specs.md and apply it with:
- Project name: "MyProject"
- Specs directory: "./specs"
```

### Example 2: Refine All Specifications

```
Read prompts/refine-specs.md and apply it to the specs/ directory.
Follow all steps to validate, check, and generate updated files.
```

### Example 3: Generate History Only

```
Read prompts/generate-history.md and update rfc-history.md based on
all RFC files in the specs/ directory.
```

## Template Variables

Templates use `{{PROJECT_NAME}}` as a placeholder that should be replaced with the actual project name during initialization.

## File Structure

```
.claude/skills/platonic-coding-specs/
├── SKILL.md                    # This file
├── prompts/                    # AI prompt instructions
│   ├── init-specs.md
│   ├── refine-specs.md
│   ├── generate-history.md
│   ├── generate-index.md
│   ├── generate-namings.md
│   ├── validate-consistency.md
│   ├── check-taxonomy.md
│   └── check-standard-compliance.md
└── templates/                  # Template files
    ├── rfc-standard.md.template
    ├── rfc-history.md.template
    ├── rfc-index.md.template
    ├── rfc-namings.md.template
    └── rfc-template.md
```

## Guidelines

1. **Always read the prompt file first** before performing operations
2. **Follow prompts step-by-step** - they contain detailed instructions
3. **Check rfc-standard.md** for conventions before making changes
4. **Update history** when making changes to RFCs
5. **Keep namings current** - remove deprecated terms immediately
6. **No version history in namings** - version history belongs in rfc-history.md

## Dependencies

- Access to specs directory
- Read access to RFC files
- Write access to rfc-history.md, rfc-index.md, rfc-namings.md
- Reference to rfc-standard.md for validation

## Related Skills

This skill works with any project that uses RFC-style specifications. It can be combined with documentation skills or code generation skills that reference RFCs.
