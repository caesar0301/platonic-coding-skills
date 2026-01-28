# Platonic Coding Specs Skill

A reusable agent skill for managing RFC-style specifications in development projects using AI-driven operations.

## Overview

This skill abstracts the RFC (Request for Comments) specification management system, providing:

- **Templates** for creating project-specific specification standards
- **AI prompts** for initialization, refinement, and validation
- **Dynamic generation** of history, index, and namings files via AI operations
- **Consistency checks** across all specification documents

## Structure

```
.claude/skills/platonic-coding-specs/
├── SKILL.md                    # Skill definition (Claude Code standard)
├── README.md                   # This file
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

## Usage

### Initialize a New Project

**For AI Agent**: Read `prompts/init-specs.md` and apply it with:
- Project name: "MyProject"
- Specs directory: "./specs"

The AI agent will:
1. Read the prompt file
2. Process templates with project name replacement
3. Create initialized specs folder

### Refine Specifications

**For AI Agent**: Read `prompts/refine-specs.md` and apply it to the specs directory.

This comprehensive operation:
- Validates consistency between RFC files
- Checks taxonomy consistency
- Syncs namings with current RFCs
- Ensures compliance with rfc-standard.md
- Generates updated history, index, and namings files

### Individual Operations

Use specific prompts for targeted operations:

- **Generate History**: Read `prompts/generate-history.md`
- **Generate Index**: Read `prompts/generate-index.md`
- **Generate Namings**: Read `prompts/generate-namings.md`
- **Validate Consistency**: Read `prompts/validate-consistency.md`
- **Check Taxonomy**: Read `prompts/check-taxonomy.md`
- **Check Compliance**: Read `prompts/check-standard-compliance.md`

## How It Works

This skill uses **AI prompts** instead of code. Each operation is defined as a detailed prompt that guides the AI agent through:

1. **Reading** relevant files
2. **Analyzing** content according to rules
3. **Generating** or **updating** files
4. **Validating** results

## Template Variables

Templates use `{{PROJECT_NAME}}` as a placeholder that will be replaced during initialization.

## Integration

This skill is designed for:
- AI agent workflows (Claude Code, Cursor, etc.)
- Automated specification management
- Documentation generation systems
- Project initialization workflows

## Key Features

1. **No Code Required**: All operations are prompt-based
2. **Template-Based**: Easy to customize for different projects
3. **Dynamic Generation**: History, index, and namings are generated from RFCs
4. **Consistency Validation**: Ensures RFCs stay consistent
5. **Standard Compliance**: Validates against rfc-standard.md

## Best Practices

1. **Always read the prompt file first** before performing operations
2. **Follow prompts step-by-step** - they contain detailed instructions
3. **Check rfc-standard.md** for conventions before making changes
4. **Update history** when making changes to RFCs
5. **Keep namings current** - remove deprecated terms immediately
6. **No version history in namings** - version history belongs in rfc-history.md

## Related Documents

- [SKILL.md](SKILL.md) - Skill definition and operation details
- [prompts/](prompts/) - Individual operation prompts
- [templates/](templates/) - Template files
