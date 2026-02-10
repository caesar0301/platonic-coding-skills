# Platonic Init — Complete Reference

This document provides detailed information about all operations available in the platonic-init skill.

## Table of Contents

1. [Operation Overview](#operation-overview)
2. [Execution Modes](#execution-modes)
3. [Detailed Operation Guides](#detailed-operation-guides)
4. [Template Variables](#template-variables)
5. [File Structure](#file-structure)
6. [Workflow Examples](#workflow-examples)
7. [Troubleshooting](#troubleshooting)

## Operation Overview

The skill provides 6 operations organized into two categories:

### Scaffolding Operations

- **Scaffold Project** (`scaffold-project.md`) — Create directories, config, and templates

### Recovery Operations

- **Scan Project** (`scan-project.md`) — Systematically analyze existing codebase
- **Plan Modular Specs** (`plan-modular-specs.md`) — Propose RFC dependency graph from scan results
- **Recover Conceptual Design** (`recover-conceptual.md`) — Generate conceptual design spec from code
- **Recover Architecture Design** (`recover-architecture.md`) — Generate architecture design spec from code
- **Recover Impl Interface Design** (`recover-impl-interface.md`) — Generate impl interface design spec (optional)

## Execution Modes

### Mode 1: Greenfield Init

For new projects with no existing code:

1. Read `scaffold-project.md` and execute it
2. Done — user writes specs from scratch using platonic-workflow

### Mode 2: Recovery Init

For projects with existing code:

1. Read `scaffold-project.md` and execute it
2. Read `scan-project.md` and scan the codebase
3. Read `plan-modular-specs.md` and propose an RFC graph to the user
4. After user confirms: read `recover-conceptual.md` and generate the conceptual design RFC
5. Read `recover-architecture.md` and generate architecture design RFCs
6. Optionally (if user requests): read `recover-impl-interface.md` and generate impl interface RFCs
7. Populate `rfc-index.md`, `rfc-namings.md`, `rfc-history.md` from generated specs

## Detailed Operation Guides

### 1. Scaffold Project

**Reference**: `scaffold-project.md`

**Purpose**: Create the Platonic Coding infrastructure for a project.

**Inputs**:
- Project name
- Project root directory
- Language and framework (optional, auto-detected if possible)
- Custom paths for specs, impl, drafts (optional)

**Output**:
- `.platonic.yml` at project root
- `specs/` directory with rfc-standard.md, rfc-history.md, rfc-index.md, rfc-namings.md, templates/
- `docs/impl/` directory with README.md
- `docs/drafts/` directory with README.md

---

### 2. Scan Project

**Reference**: `scan-project.md`

**Purpose**: Systematically analyze an existing codebase to understand its structure, types, interfaces, and design patterns.

**Inputs**:
- Project root directory
- Language (from `.platonic.yml` or auto-detected)

**Output**: Structured scan results (in-memory) covering:
- Project metadata (language, frameworks, entry points)
- Module/package structure and dependency graph
- Public types and interfaces catalog
- Data flow patterns and invariants
- Design patterns and error handling strategies

---

### 3. Plan Modular Specs

**Reference**: `plan-modular-specs.md`

**Purpose**: From scan results, propose a modular RFC dependency graph with a bounded number of specs.

**Inputs**: Scan results from step 2

**Output**: Proposed RFC graph presented to the user:
- RFC number, title, kind, one-line summary for each
- Dependency relationships between RFCs
- Total count within default limit (max 5)

**Critical**: The agent MUST present this plan and get user confirmation before generating any specs.

---

### 4. Recover Conceptual Design

**Reference**: `recover-conceptual.md`

**Purpose**: Generate a Conceptual Design RFC from scan results.

**Inputs**: Scan results + confirmed RFC plan

**Output**: `RFC-0001.md` (or user-specified number) with Status: Draft

---

### 5. Recover Architecture Design

**Reference**: `recover-architecture.md`

**Purpose**: Generate Architecture Design RFCs from scan results, one per major subsystem.

**Inputs**: Scan results + confirmed RFC plan + generated conceptual design

**Output**: `RFC-0002.md`, `RFC-0003.md`, etc. with Status: Draft

---

### 6. Recover Impl Interface Design

**Reference**: `recover-impl-interface.md`

**Purpose**: Generate Implementation Interface Design RFCs from scan results. Only if explicitly requested by the user.

**Inputs**: Scan results + confirmed RFC plan + generated architecture specs

**Output**: Additional RFC files with Status: Draft

## Template Variables

Templates use `{{PLACEHOLDER}}` syntax:

| Variable | Description | Example |
|----------|-------------|---------|
| `{{PROJECT_NAME}}` | Project name | "Acme" |
| `{{PROJECT_DESCRIPTION}}` | Brief description | "A task management API" |
| `{{LANGUAGE}}` | Primary language | "typescript" |
| `{{FRAMEWORK}}` | Framework if any | "nextjs" |
| `{{DATE}}` | Current date | "2026-02-10" |
| `{{RFC_NUMBER}}` | RFC number | "0001" |
| `{{TITLE}}` | RFC title | "System Vision" |
| `{{AUTHORS}}` | Author names | "Team Lead" |
| `{{DEPENDS_ON}}` | Dependencies | "RFC-0001" or "---" |

## File Structure

```
platonic-init/
├── SKILL.md                               # Skill definition
├── assets/                                # Templates
│   ├── platonic.yml.template              # Project config
│   ├── rfc-standard.md.template           # RFC process (with spec kinds)
│   ├── rfc-history.md.template            # History tracking
│   ├── rfc-index.md.template              # Spec index
│   ├── rfc-namings.md.template            # Terminology reference
│   ├── rfc-template.md                    # Generic RFC template
│   ├── conceptual-design.md.template      # Conceptual design template
│   ├── architecture-design.md.template    # Architecture design template
│   ├── impl-interface-design.md.template  # Impl interface design template
│   ├── impl-guide-template.md             # Implementation guide template
│   ├── impl-readme.md.template            # README for impl/ directory
│   └── drafts-readme.md.template          # README for drafts/ directory
├── references/                            # Operation guides
│   ├── REFERENCE.md                       # This file
│   ├── scaffold-project.md               # Scaffolding procedure
│   ├── scan-project.md                    # Codebase scanning
│   ├── plan-modular-specs.md              # RFC graph planning
│   ├── recover-conceptual.md              # Conceptual design recovery
│   ├── recover-architecture.md            # Architecture design recovery
│   └── recover-impl-interface.md          # Impl interface design recovery
```

## Workflow Examples

### Example 1: New Project Setup

```
1. User: "Initialize platonic coding for my new project Acme (TypeScript/Next.js)"
2. Agent: Reads scaffold-project.md
3. Agent: Creates .platonic.yml, specs/, docs/impl/, docs/drafts/ with all templates
4. Done — user starts with platonic-workflow Phase 0
```

### Example 2: Existing Codebase Adoption

```
1. User: "Adopt platonic coding for this existing project"
2. Agent: Reads scaffold-project.md — creates infrastructure
3. Agent: Reads scan-project.md — scans the codebase (5 phases)
4. Agent: Reads plan-modular-specs.md — proposes RFC graph:
   - RFC-0001: System Vision (Conceptual)
   - RFC-0002: API Layer Architecture (Architecture)
   - RFC-0003: Data Layer Architecture (Architecture)
5. User: Confirms the plan
6. Agent: Reads recover-conceptual.md — generates RFC-0001
7. Agent: Reads recover-architecture.md — generates RFC-0002, RFC-0003
8. Agent: Populates rfc-index.md, rfc-namings.md, rfc-history.md
9. Done — user reviews Draft RFCs, then uses platonic-workflow Phase 2+ for new features
```

### Example 3: Recovery with Custom Count

```
1. User: "Recover specs but limit to 3 RFCs total"
2. Agent: Adjusts max count to 3 during plan-modular-specs
3. Produces: 1 conceptual + 2 architecture specs (or 1 + 1 if project is small)
```

## Troubleshooting

### Issue: Auto-detection fails for language/framework

**Solution**: Specify language and framework explicitly when invoking the skill.

### Issue: Too many subsystems identified during scan

**Solution**: The plan-modular-specs step merges related subsystems to stay within the count limit. User can also manually merge during confirmation.

### Issue: Recovery produces thin specs

**Solution**: This is expected for small or simple projects. The specs serve as a starting point — refine with platonic-specs.

### Issue: .platonic.yml already exists

**Solution**: Read the existing config and use its values. Do not overwrite unless user explicitly requests it.

## Integration with Other Skills

- **platonic-specs**: Use `refine` post-init to validate and update specs. This skill handles all initialization that was previously part of platonic-specs.
- **platonic-workflow**: After init, start at appropriate phase for new features
- **platonic-impl-guide**: Create implementation guides from recovered specs
- **platonic-code-review**: Review code against recovered specs
