# Platonic Coding Specs

An Agent Skill for managing RFC-style specifications in development projects with AI-driven operations.

## What This Skill Does

This skill helps you:

- **Initialize** RFC specification systems for new projects
- **Validate** specifications for consistency and compliance
- **Generate** history, index, and terminology files automatically
- **Maintain** specification quality with taxonomy and format checks

All operations are AI-driven using reference documents - no code required.

## Quick Start

### For New Projects

Tell your AI agent:

```
Read the platonic-coding-specs skill references/init-specs.md and initialize
specs for project "MyProject" in the ./specs directory
```

This creates:
- `rfc-standard.md` - Your project's RFC guidelines
- `rfc-history.md` - Change history (initially empty)
- `rfc-index.md` - RFC index (initially empty)
- `rfc-namings.md` - Terminology reference (initially empty)

### For Existing Specs

Run a comprehensive refinement:

```
Read the platonic-coding-specs skill references/refine-specs.md and
apply it to my ./specs directory
```

This validates, checks, and regenerates all specification files.

## Available Operations

The skill provides 8 operations:

| Operation | Reference File | What It Does |
|-----------|----------------|--------------|
| **Initialize** | `init-specs.md` | Bootstrap new specification system |
| **Refine** | `refine-specs.md` | Comprehensive validation and update |
| **Generate History** | `generate-history.md` | Update RFC change history |
| **Generate Index** | `generate-index.md` | Update RFC index |
| **Generate Namings** | `generate-namings.md` | Update terminology reference |
| **Validate Consistency** | `validate-consistency.md` | Check cross-references |
| **Check Taxonomy** | `check-taxonomy.md` | Verify terminology usage |
| **Check Compliance** | `check-standard-compliance.md` | Validate RFC format |

## File Structure

```
platonic-coding-specs/
├── SKILL.md              # Agent Skills format definition
├── README.md             # This file
├── references/           # Reference documentation
│   ├── REFERENCE.md      # Complete operation guide
│   └── *.md              # Individual operation references
└── assets/               # Template files
    └── *.template        # RFC templates
```

## How It Works

This skill follows the [Agent Skills](https://agentskills.io) format:

1. **Discovery**: AI agents see the skill name and description
2. **Activation**: When relevant, agents read the full SKILL.md
3. **Execution**: Agents follow reference documents to perform operations

All operations are defined as reference documents that guide the AI through the process.

## Examples

### Initialize and Create First RFC

```
1. Read references/init-specs.md with project "MyProject" in ./specs
2. Review the generated rfc-standard.md
3. Copy assets/rfc-template.md to ./specs/rfc-001-my-first-spec.md
4. Edit the new RFC with your content
```

### Weekly Maintenance

```
1. Read references/validate-consistency.md for ./specs
2. Fix any reported issues
3. Read references/refine-specs.md to update all files
```

### Before Release

```
Read references/refine-specs.md for ./specs to run comprehensive
validation and regenerate all indices
```

## Integration

This skill works with:

- **AI Coding Agents**: Claude Code, Cursor, Windsurf, etc.
- **Version Control**: Git-friendly markdown files
- **Documentation Systems**: Generate docs from RFC indices
- **Development Workflows**: Reference RFCs in code and PRs

## Key Features

✓ No code required - all AI-driven operations  
✓ Template-based initialization  
✓ Dynamic generation of history, index, and terminology  
✓ Comprehensive validation and consistency checks  
✓ Follows [Agent Skills](https://agentskills.io) standard  

## Documentation

- **[SKILL.md](SKILL.md)** - Agent Skills format definition
- **[references/REFERENCE.md](references/REFERENCE.md)** - Complete operation guide with examples
- **[references/](references/)** - Individual operation references
- **[assets/](assets/)** - RFC templates

## Best Practices

1. Read reference files before performing operations
2. Customize rfc-standard.md for your project conventions
3. Update history when making RFC changes
4. Run validation regularly to catch issues early
5. Keep terminology current in rfc-namings.md

## License

MIT - See [LICENSE](../../LICENSE) for details
