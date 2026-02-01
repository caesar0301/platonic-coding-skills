# Platonic Coding Skills

A professional collection of [Agent Skills](https://agentskills.io) for AI-powered Platonic Coding workflow.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Agent Skills Format](https://img.shields.io/badge/format-Agent%20Skills%201.0-blue)](https://agentskills.io)

## Overview

**Platonic Coding** is a coding style designed for complex projects and cross-team collaboration with AI agents. Instead of relying on prompts, vibes, or implicit assumptions, it treats specifications as abstract laws that define what can exist, what can change, and what must always hold. Agents operate inside a shared, closed spec world where meaning is explicit, violations are detectable, and evolution is traceable over time, making large systems reproducible, reviewable, and stable across teams, agents, and long development cycles.

![manifesto-infographic](./platonic-coding-manifesto.png)

See a full description in [PLATONIC_CODING_MANIFESTO.md](https://github.com/caesar0301/platonic-coding-skills/blob/main/PLATONIC_CODING_MANIFESTO.md).

This repository provides production-ready Agent Skills that enhance Platonic Coding. All skills follow the [Agent Skills specification](https://agentskills.io/specification) for maximum compatibility across AI coding agents.

## In Practice

### 🚀 Grism: Hypergraph Database in 3 Days

We built [**Grism**](https://github.com/mirasoth/Grism), an AI-native, neurosymbolic hypergraph database, from concept to *working prototype* in just **three days** using the Platonic Coding method.

Grism features:
- **Hypergraph-first architecture** with n-ary relations as the core primitive
- **Multi-layered engine** (Python API → Logical Plan → Optimizer → Storage)
- **Neurosymbolic integration** for combining symbolic reasoning with neural signals
- **Comprehensive RFC specifications** driving all design decisions

By defining the system's form through RFCs before writing code, agents operated within a closed, legally defined space. Every architectural decision was traceable, every component was spec-compliant, and the entire codebase remained coherent across rapid iteration cycles.

*This demonstrates that Platonic Coding doesn't slow you down, it accelerates complex system development by eliminating ambiguity and drift.*

## Available Skills

### 📋 platonic-code-specs

Manage RFC-style specifications with AI-driven operations.

**Capabilities:**
- Initialize new specification systems from templates
- Generate and maintain RFC history, index, and terminology files
- Validate consistency and cross-references
- Check taxonomy and standard compliance
- Comprehensive specification refinement

**Use when:** Managing technical specifications, RFCs, documentation standards, terminology systems

[**→ Full Documentation**](skills/platonic-code-specs/SKILL.md)

---

### ✅ platonic-code-review

Review code implementation against specifications for consistency validation.

**Capabilities:**
- Validate code matches RFC specifications and requirements
- Check feature completeness against specs
- Identify gaps (specs without code, code without specs)
- Find discrepancies where implementation differs from specs
- Generate detailed compliance reports (default: report-only, no code modification)

**Use when:** Validating implementation against specs, checking requirements compliance, ensuring spec-to-code consistency

[**→ Full Documentation**](skills/platonic-code-review/SKILL.md)

---

### 📐 platonic-impl-guide

Create concrete, project-specific implementation designs from RFC specifications.

**Capabilities:**
- Create implementation guides that translate RFC specs into implementation-ready designs
- Validate guides against RFCs for contradictions
- Update guides when RFCs change
- Language-aware and framework-aware technical architecture

**Use when:** Planning implementation of RFCs, creating detailed technical designs, documenting implementation architecture

[**→ Full Documentation**](skills/platonic-impl-guide/SKILL.md)

## Installation

### Method 1: Claude Code CLI Marketplace (Easiest)

If using Claude Code CLI with marketplace support:

```bash
# Add the skills marketplace
claude-code marketplace add caesar0301/platonic-coding-skills
```

### Method 2: Install using npx skills (Recommended for Most)

```bash
npx skills add caesar0301/platonic-coding-skills
```

### Method 3: Clone to Skills Directory

Clone this repository to your agent's skills directory:

```bash
git clone https://github.com/caesar0301/platonic-coding-skills.git ~/.claude/skills/platonic-coding-skills
```

## Examples

### Example 1: Initialize Project Specifications

```
I'm starting a new project called "AI Assistant Platform".
Use the platonic-code-specs skill to initialize the 
specification system in ./docs/specs/
```

**Result:** Creates RFC specification system with standard, history, index, and namings files.

### Example 2: Validate Code Against Specs

```
Use the platonic-code-review skill to verify that src/auth/ 
correctly implements all requirements from specs/rfc-001-authentication.md
```

**Result:** Detailed compliance report showing what's implemented, what's missing, and what's inconsistent.

### Example 3: Maintain Specifications

```
Use the platonic-code-specs skill to refine all 
specifications in ./specs/, checking consistency and 
regenerating all index files.
```

**Result:** Validated specifications with updated history, index, and terminology files.

### Example 4: Gap Analysis

```
Use the platonic-code-review skill to identify gaps between 
all RFCs in ./specs/ and the implementation in ./src/
```

**Result:** Bi-directional analysis showing unimplemented specs and undocumented code features.

### Example 5: Create Implementation Guide

```
Use platonic-impl-guide to create an implementation guide for 
RFC-0042 (Message Queue Protocol) targeting the acme-queue crate.
Use Rust with async/await patterns.
```

**Result:** Concrete implementation guide with module structure, types, interfaces, and implementation details that align with the RFC.

## Practical Workflows

### Workflow 1: New Feature Development

```
# Step 1: Create specification
Use platonic-code-specs to create a new RFC for the user authentication feature

# Step 2 (optional): Create implementation guide
Use platonic-impl-guide to create a technical design from the RFC

# Step 3: Implement the feature
[You implement the code]

# Step 4: Validate implementation
Use platonic-code-review to verify src/auth/ implements 
specs/rfc-001-auth.md completely

# Step 5: Update documentation
Use platonic-code-specs to update the RFC history and index
```

### Workflow 2: Code Review Before Merge

```
# Review both specs and code
1. Use platonic-code-specs to validate specs consistency
2. Use platonic-code-review to check PR changes against all relevant RFCs
3. Generate compliance report
4. Fix any discrepancies before merge
```

### Workflow 3: Legacy Code Documentation

```
# Document existing code
1. Use platonic-code-review to analyze src/ and identify undocumented features
2. Use platonic-code-specs to create RFCs for undocumented features
3. Use platonic-code-review to verify RFCs accurately describe the code
```

### Workflow 4: Continuous Compliance

```
# Regular maintenance
Weekly:
- Use platonic-code-specs to refine specs (validate, update indices)
- Use platonic-code-review to check new commits against specs

Before releases:
- Use platonic-code-review for comprehensive audit (Level 3)
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
