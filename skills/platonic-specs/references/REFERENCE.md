# Platonic Coding Specs - Complete Reference

This document provides detailed information about all operations available in the Platonic Coding Specs skill.

## Table of Contents

1. [Operation Overview](#operation-overview)
2. [Detailed Operation Guides](#detailed-operation-guides)
3. [Template Variables](#template-variables)
4. [File Structure](#file-structure)
5. [Workflow Examples](#workflow-examples)
6. [Troubleshooting](#troubleshooting)

## Operation Overview

The skill provides 8 operations organized into three categories:

### Initialization Operations
- **Initialize Specs Folder** (`init-specs.md`) - Bootstrap a new specification system

### Generation Operations
- **Generate History** (`generate-history.md`) - Create/update RFC change history
- **Generate Index** (`generate-index.md`) - Create/update RFC index with quick links
- **Generate Namings** (`generate-namings.md`) - Extract and organize terminology

### Validation Operations
- **Validate Consistency** (`validate-consistency.md`) - Check cross-references and metadata
- **Check Taxonomy** (`check-taxonomy.md`) - Verify terminology usage
- **Check Standard Compliance** (`check-standard-compliance.md`) - Validate RFC format
- **Refine Specifications** (`refine-specs.md`) - Comprehensive validation and generation

## Detailed Operation Guides

### 1. Initialize Specs Folder

**Reference**: `init-specs.md`

**Purpose**: Create a new specification system with all foundation files.

**Inputs**:
- **Project name**: The name of your project (e.g., "MyProject", "PlatonicCodingSkills")
- **Specs directory**: Path where specs will be created (e.g., "./specs", "./docs/specs")

**Process**:
1. Creates the specs directory if it doesn't exist
2. Reads all template files from `assets/`
3. Replaces `{{PROJECT_NAME}}` with provided project name
4. Replaces `YYYY-MM-DD` with current date
5. Writes output files to specs directory

**Output Files**:
- `rfc-standard.md` - Project-specific RFC format and guidelines
- `rfc-history.md` - Change history template (empty, ready for events)
- `rfc-index.md` - RFC index template (empty, ready for entries)
- `rfc-namings.md` - Terminology reference template (empty, ready for terms)

**Example Usage**:
```
Read references/init-specs.md and apply it with:
- Project name: "MyProject"
- Specs directory: "./specs"
```

**Notes**:
- Skips files that already exist (won't overwrite)
- Preserves exact capitalization of project name
- Creates parent directories if needed

---

### 2. Refine Specifications

**Reference**: `refine-specs.md`

**Purpose**: Comprehensive operation that validates, checks, and regenerates all specification files.

**Inputs**:
- **Specs directory**: Path to your specs folder
- **Verbose mode** (optional): Enable detailed warnings

**Process**:
1. Validates consistency (cross-references, dependencies, metadata)
2. Checks taxonomy (terminology usage, deprecated terms)
3. Validates standard compliance (RFC format)
4. Generates updated history file
5. Generates updated index file
6. Generates updated namings file

**Outputs**:
- Updated `rfc-history.md`
- Updated `rfc-index.md`
- Updated `rfc-namings.md`
- Validation report with errors and warnings

**Example Usage**:
```
Read references/refine-specs.md and apply it to the ./specs directory.
Show me the validation report when complete.
```

**Best Used When**:
- Preparing for a release
- After significant RFC changes
- Regular maintenance (weekly/monthly)
- Before team reviews

---

### 3. Generate History

**Reference**: `generate-history.md`

**Purpose**: Scan all RFC files and create/update the change history document.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Process**:
1. Scans all RFC files (rfc-*.md)
2. Extracts lifecycle events (Created, Updated, Status changes)
3. Sorts events chronologically
4. Generates formatted history document

**Output**:
- Updated `rfc-history.md` with all RFC events in chronological order

**History Format**:
```markdown
## YYYY-MM-DD - RFC-XXX: Title
- Status: Active
- Description: Brief description of change
```

**Example Usage**:
```
Read references/generate-history.md and update the history file
for all RFCs in ./specs/
```

---

### 4. Generate Index

**Reference**: `generate-index.md`

**Purpose**: Create an index of all RFCs with metadata and quick links.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Process**:
1. Scans all RFC files
2. Extracts metadata (title, status, author, created date)
3. Generates table of active RFCs
4. Creates quick link sections by category/tag

**Output**:
- Updated `rfc-index.md` with:
  - Active RFCs table
  - Quick links by status
  - Quick links by category (if present)

**Example Usage**:
```
Read references/generate-index.md and regenerate the index
for all RFCs in ./specs/
```

---

### 5. Generate Namings

**Reference**: `generate-namings.md`

**Purpose**: Extract terminology from RFCs and create a terminology reference.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Process**:
1. Scans active RFC files
2. Identifies defined terms, concepts, and terminology
3. Extracts definitions and usage contexts
4. Organizes alphabetically
5. Generates terminology document

**Output**:
- Updated `rfc-namings.md` with current terminology

**Important Rules**:
- Only includes terms from ACTIVE RFCs
- Removes terms from DEPRECATED RFCs
- No version history in namings (history goes in rfc-history.md)
- Each term links back to its defining RFC

**Example Usage**:
```
Read references/generate-namings.md and update terminology
from all active RFCs in ./specs/
```

---

### 6. Validate Consistency

**Reference**: `validate-consistency.md`

**Purpose**: Check for consistency issues across all RFC files.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Validation Checks**:
- **Cross-references**: Verify all RFC references point to existing files
- **Dependencies**: Check dependency chains are valid
- **Metadata**: Ensure required fields are present and valid
- **Status values**: Verify status is one of: Draft, Active, Deprecated, Superseded
- **Date formats**: Check all dates use YYYY-MM-DD format

**Output**:
- List of errors (must fix)
- List of warnings (should review)

**Example Usage**:
```
Read references/validate-consistency.md and check all RFCs
in ./specs/ for consistency issues
```

---

### 7. Check Taxonomy

**Reference**: `check-taxonomy.md`

**Purpose**: Verify terminology is used consistently across RFCs.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Checks**:
- Terms are used consistently (same meaning everywhere)
- No conflicting definitions
- Deprecated terms are not used in active RFCs
- All significant terms are defined in namings

**Output**:
- Taxonomy consistency report with issues and recommendations

**Example Usage**:
```
Read references/check-taxonomy.md and verify terminology
consistency across ./specs/
```

---

### 8. Check Standard Compliance

**Reference**: `check-standard-compliance.md`

**Purpose**: Validate RFCs follow the format defined in rfc-standard.md.

**Inputs**:
- **Specs directory**: Path to your specs folder

**Checks**:
- Required sections are present
- Metadata format is correct
- Numbering follows conventions
- File naming follows pattern (rfc-NNN-title.md)

**Output**:
- Compliance report with errors and warnings per RFC

**Example Usage**:
```
Read references/check-standard-compliance.md and validate
all RFCs in ./specs/ against the standard
```

## Template Variables

Templates use placeholders that are replaced during initialization:

| Variable | Description | Example |
|----------|-------------|---------|
| `{{PROJECT_NAME}}` | Project name provided during init | "MyProject" |
| `YYYY-MM-DD` | Current date in ISO format | "2026-01-28" |

**Processing Rules**:
- Variable names are case-sensitive
- Preserve exact capitalization of provided values
- All other content preserved exactly as in template
- Maintain markdown formatting

## File Structure

```
platonic-specs/
├── SKILL.md                           # Skill definition and user-facing docs
├── references/                        # Reference documentation
│   ├── REFERENCE.md                   # This file
│   ├── init-specs.md                  # Initialize operation
│   ├── refine-specs.md                # Refine operation
│   ├── generate-history.md            # History generation
│   ├── generate-index.md              # Index generation
│   ├── generate-namings.md            # Namings generation
│   ├── validate-consistency.md        # Consistency validation
│   ├── check-taxonomy.md              # Taxonomy checking
│   └── check-standard-compliance.md   # Standard compliance
└── assets/                            # Template files
    ├── rfc-standard.md.template       # RFC guidelines template
    ├── rfc-history.md.template        # History template
    ├── rfc-index.md.template          # Index template
    ├── rfc-namings.md.template        # Namings template
    └── rfc-template.md                # Individual RFC template
```

## Workflow Examples

### Example 1: Starting a New Project

```
1. Read references/init-specs.md and apply it with:
   - Project name: "MyProject"
   - Specs directory: "./docs/specs"

2. Review the generated rfc-standard.md and customize if needed

3. Create your first RFC using assets/rfc-template.md as a guide
```

### Example 2: Weekly Maintenance

```
1. Read references/validate-consistency.md and check ./specs/

2. If issues found, fix them

3. Read references/refine-specs.md to regenerate all indices

4. Review the validation report
```

### Example 3: Before Release

```
1. Read references/check-taxonomy.md to verify terminology

2. Read references/check-standard-compliance.md to validate format

3. Read references/refine-specs.md for comprehensive update

4. Commit all changes to version control
```

### Example 4: After Adding New RFCs

```
1. Read references/generate-index.md to update the index

2. Read references/generate-namings.md if new terminology was added

3. Read references/generate-history.md to record the change
```

## Troubleshooting

### Issue: Templates not found during initialization

**Solution**: Ensure you're running the operation from a location where `assets/` can be accessed via relative paths, or provide absolute paths.

### Issue: Generated files are empty

**Solution**: Check that your specs directory contains valid RFC files with proper frontmatter metadata.

### Issue: Validation reports many errors

**Solution**: Run operations one at a time:
1. First fix cross-reference issues (validate-consistency)
2. Then fix format issues (check-standard-compliance)
3. Finally check terminology (check-taxonomy)

### Issue: History file missing events

**Solution**: Ensure RFC files have proper metadata with dates. Re-run `generate-history.md` to rescan all files.

### Issue: Namings contains deprecated terms

**Solution**: Verify deprecated RFCs have status "Deprecated" in their frontmatter. Re-run `generate-namings.md` to rebuild the terminology list.

## Integration with Other Tools

This skill integrates well with:

- **Version control**: Commit specs after running refine operations
- **Documentation generators**: Use the index as input to doc generators
- **Code generation**: Reference RFC terminology in generated code
- **Review processes**: Use validation reports in pull requests

## Best Practices Summary

1. **Initialize once**: Use init-specs.md when starting a new project
2. **Validate often**: Run consistency checks regularly
3. **Update indices**: Regenerate after any RFC changes
4. **Follow the standard**: Keep your rfc-standard.md as the source of truth
5. **Maintain history**: Record all significant changes
6. **Clean terminology**: Remove deprecated terms promptly
7. **Use refine-specs**: Run comprehensive refine before releases

## Related Resources

- See SKILL.md for quick start and skill definition
- See individual reference files for detailed operation instructions
