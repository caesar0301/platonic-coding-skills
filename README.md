# Platonic Coding Skills

A professional collection of [Agent Skills](https://agentskills.io) for AI-powered development workflows.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Agent Skills Format](https://img.shields.io/badge/format-Agent%20Skills%201.0-blue)](https://agentskills.io)

## Overview

This repository provides production-ready Agent Skills that enhance AI agent capabilities for development workflows. All skills follow the [Agent Skills specification](https://agentskills.io/specification) for maximum compatibility across AI coding agents.

## Available Skills

### 📋 platonic-coding-specs

Manage RFC-style specifications with AI-driven operations.

**Capabilities:**
- Initialize new specification systems from templates
- Generate and maintain RFC history, index, and terminology files
- Validate consistency and cross-references
- Check taxonomy and standard compliance
- Comprehensive specification refinement

**Use when:** Managing technical specifications, RFCs, documentation standards, terminology systems

[**→ Full Documentation**](skills/platonic-coding-specs/README.md)

---

### ✅ review-code-per-specs

Review code implementation against specifications for consistency validation.

**Capabilities:**
- Validate code matches RFC specifications and requirements
- Check feature completeness against specs
- Identify gaps (specs without code, code without specs)
- Find discrepancies where implementation differs from specs
- Generate detailed compliance reports (default: report-only, no code modification)

**Use when:** Validating implementation against specs, checking requirements compliance, ensuring spec-to-code consistency

[**→ Full Documentation**](skills/review-code-per-specs/README.md)

## Installation

### Method 1: Claude Code CLI Marketplace (Easiest)

If using Claude Code CLI with marketplace support:

```bash
# Add the skills marketplace
claude-code marketplace add caesar0301/platonic-coding-skills
```

### Method 2: Clone to Skills Directory (Recommended for Most)

Clone this repository to your agent's skills directory:

```bash
# For Claude Code / Cursor / Windsurf
git clone https://github.com/caesar0301/platonic-coding-skills.git ~/.claude/skills/platonic-coding-skills

# Or use a custom skills directory
git clone https://github.com/caesar0301/platonic-coding-skills.git /path/to/your/skills/platonic-coding-skills
```

### Verify Installation

**For Claude Code CLI users:**
```bash
claude-code
> /skills list
# You should see: platonic-coding-specs, review-code-per-specs
```

**For manual installation users:**
```bash
# List skills directory
ls ~/.claude/skills/

# You should see:
# - platonic-coding-specs/
# - review-code-per-specs/
```

**For all users:**  
Ask your AI agent: "List available skills" or "What skills do you have?"

## Examples

### Example 1: Initialize Project Specifications

```
I'm starting a new project called "AI Assistant Platform".
Use the platonic-coding-specs skill to initialize the 
specification system in ./docs/specs/
```

**Result:** Creates RFC specification system with standard, history, index, and namings files.

### Example 2: Validate Code Against Specs

```
Use the review-code-per-specs skill to verify that src/auth/ 
correctly implements all requirements from specs/rfc-001-authentication.md
```

**Result:** Detailed compliance report showing what's implemented, what's missing, and what's inconsistent.

### Example 3: Maintain Specifications

```
Use the platonic-coding-specs skill to refine all 
specifications in ./specs/, checking consistency and 
regenerating all index files.
```

**Result:** Validated specifications with updated history, index, and terminology files.

### Example 4: Gap Analysis

```
Use the review-code-per-specs skill to identify gaps between 
all RFCs in ./specs/ and the implementation in ./src/
```

**Result:** Bi-directional analysis showing unimplemented specs and undocumented code features.

## Practical Workflows

### Workflow 1: New Feature Development

```
# Step 1: Create specification
Use platonic-coding-specs to create a new RFC for the user authentication feature

# Step 2: Implement the feature
[You implement the code]

# Step 3: Validate implementation
Use review-code-per-specs to verify src/auth/ implements 
specs/rfc-001-auth.md completely

# Step 4: Update documentation
Use platonic-coding-specs to update the RFC history and index
```

### Workflow 2: Code Review Before Merge

```
# Review both specs and code
1. Use platonic-coding-specs to validate specs consistency
2. Use review-code-per-specs to check PR changes against all relevant RFCs
3. Generate compliance report
4. Fix any discrepancies before merge
```

### Workflow 3: Legacy Code Documentation

```
# Document existing code
1. Use review-code-per-specs to analyze src/ and identify undocumented features
2. Use platonic-coding-specs to create RFCs for undocumented features
3. Use review-code-per-specs to verify RFCs accurately describe the code
```

### Workflow 4: Continuous Compliance

```
# Regular maintenance
Weekly:
- Use platonic-coding-specs to refine specs (validate, update indices)
- Use review-code-per-specs to check new commits against specs

Before releases:
- Use review-code-per-specs for comprehensive audit (Level 3)
- Address all critical and high-priority gaps
- Update specs for any intentional deviations
```

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Author

**Xiaming Chen**
- Website: [https://xiaming.site/](https://xiaming.site/)
- GitHub: [@caesar0301](https://github.com/caesar0301)

---

*Built with ❤️ following the [Agent Skills](https://agentskills.io) standard*
