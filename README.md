# Platonic Coding Skills

A professional collection of [Agent Skills](https://agentskills.io) for AI-powered Platonic Coding workflow.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Agent Skills Format](https://img.shields.io/badge/format-Agent%20Skills%201.0-blue)](https://agentskills.io)

## Overview

**Platonic Coding** is a coding style designed for complex projects and cross-team collaboration with AI agents. Instead of relying on prompts, vibes, or implicit assumptions, it treats specifications as abstract laws that define what can exist, what can change, and what must always hold. Agents operate inside a shared, closed spec world where meaning is explicit, violations are detectable, and evolution is traceable over time, making large systems reproducible, reviewable, and stable across teams, agents, and long development cycles.

![manifesto-infographic](./platonic-coding-manifesto.png)

See a full description in [PLATONIC_CODING_MANIFESTO.md](https://github.com/caesar0301/platonic-coding-skills/blob/main/PLATONIC_CODING_MANIFESTO.md).

## Available Skills

This repository provides production-ready Agent Skills that enhance Platonic Coding. All skills follow the [Agent Skills specification](https://agentskills.io/specification) for maximum compatibility across AI coding agents.

### 📋 platonic-specs

Manage RFC-style specifications with AI-driven operations.

**Capabilities:**
- Initialize new specification systems from templates
- Generate and maintain RFC history, index, and terminology files
- Validate consistency and cross-references
- Check taxonomy and standard compliance
- Comprehensive specification refinement

**Use when:** Managing technical specifications, RFCs, documentation standards, terminology systems

[**→ Full Documentation**](skills/platonic-specs/SKILL.md)

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

### 🔄 platonic-workflow

Orchestrate the full Platonic Coding workflow from conceptual design to RFC, implementation guide, code, and review.

**Capabilities:**
- Always show current workflow phase (0–4, then FINISHED)
- Phase 0: Interactive chat and optional items → design draft (default: `docs/drafts/`)
- Phase 1: Generate RFC from draft (may ask for RFC index), then **platonic-specs** refine (default: `docs/specs/`)
- Phase 2: **platonic-impl-guide** to create impl guide from RFC (may ask for RFC index) (default: `docs/impl/`)
- Phase 3: Run coding agents to implement from guide
- Phase 4: **platonic-code-review** for code vs specs and impl RFCs

**Use when:** Running the full design → spec → impl guide → code → review workflow with clear phase visibility and handoffs

[**→ Full Documentation**](skills/platonic-workflow/SKILL.md)

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

## General Workflow

Platonic Coding follows a **five-phase, closed-world workflow**. Meaning is progressively *constrained*, *materialized*, and *verified* as the system moves from abstract intent to concrete code.

```

┌──────────────────────────────────────────────────────────────┐
│ Phase 0: Conceptual Design & Requirements Elicitation        │
│                                                              │
│  • Clarify problem space, goals, constraints, and invariants │
│  • Explore domain knowledge and prior art                    │
│  • Identify core abstractions and system boundaries          │
│  • Resolve ambiguity before formalization                    │
│                                                              │
│  Output: Shared mental model, requirement notes, concepts    │
│  Tooling: AI with strong logic + broad knowledge (human-led) │
└───────────────┬──────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│ Phase 1: Design Specifications (RFC World Construction)      │
│                                                              │
│  • Formalize requirements as RFCs                            │
│  • Define entities, relations, invariants, and constraints   │
│  • Establish terminology, taxonomy, and evolution rules      │
│  • Create a closed, legally-defined specification space      │
│                                                              │
│  Output: RFCs, index, history, terminology                   │
│  Skill:  platonic-specs                                 │
└───────────────┬──────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│ Phase 2: Implementation Guide (Spec → Concrete Design)       │
│                                                              │
│  • Translate RFCs into implementation-ready architecture     │
│  • Fix language, framework, module boundaries, and APIs      │
│  • Make all design decisions explicit and traceable          │
│  • Validate against RFCs (no new meaning allowed)            │
│                                                              │
│  Output: Implementation guides                               │
│  Skill:  platonic-impl-guide                                 │
└───────────────┬──────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│ Phase 3: Code Implementation (Mechanical Realization)        │
│                                                              │
│  • Write code strictly following guides and RFCs             │
│  • No speculative design or undocumented behavior            │
│  • Code is a realization, not a source of truth              │
│                                                              │
│  Output: Source code                                         │
│  Tooling: agent uses specs & guides as law                   │
└───────────────┬──────────────────────────────────────────────┘
                │
                ▼
┌──────────────────────────────────────────────────────────────┐
│ Phase 4: Spec Compliance Review (Reality Check)              │
│                                                              │
│  • Verify code against RFCs and implementation guides        │
│  • Detect gaps, drift, and contradictions                    │
│  • Identify specs without code and code without specs        │
│  • Produce traceable compliance reports                      │
│                                                              │
│  Output: Review & compliance reports                         │
│  Skill:  platonic-code-review                                │
└──────────────────────────────────────────────────────────────┘
```

## Examples

Examples are ordered by the general workflow: specs → impl guide → code (manual) → review. Each shows a single skill in action.

### Example 0: Full workflow (platonic-workflow)

```
Use the platonic-workflow skill to run the full workflow for a new feature.
Start at Phase 0: I want to add a "user preferences" feature — we need
stored settings, sync with backend, and UI in settings page.
```

**Result:** Agent shows current phase; in Phase 0 conducts interactive design → design draft in `docs/drafts/`; in Phase 1 generates RFC and refines with platonic-specs; in Phase 2 creates impl guide with platonic-impl-guide; in Phase 3 implements code; in Phase 4 runs platonic-code-review; then FINISHED with summary.

### Example 1: Create design specs (Phase 1)

```
I'm starting a new project called "AI Assistant Platform".
Use the platonic-specs skill to initialize the
specification system in docs/specs/
```

**Result:** RFC specification system with standard, history, index, and namings files.

### Example 2: Create implementation guide (Phase 2)

```
Use the platonic-impl-guide skill to create an implementation guide for
RFC-001 (Authentication) targeting the auth module. Use TypeScript and
the existing Express patterns in this repo.
```

**Result:** Implementation guide with module structure, types, interfaces, and implementation details aligned with the RFC.

### Example 3: Implement from guide (Phase 3)

```
Implement the user authentication feature following docs/impl/rfc-001-auth-impl.md
and docs/specs/rfc-001-authentication.md. Do not deviate from the spec or the guide.
```

**Result:** Code that matches the implementation guide and the RFC (no separate skill; the agent uses the docs as source of truth).

### Example 4: Review code against spec (Phase 4)

```
Use the platonic-code-review skill to verify that src/auth/
correctly implements all requirements from docs/specs/rfc-001-authentication.md.
```

**Result:** Compliance report showing what is implemented, what is missing, and what is inconsistent.

### Example 5: Maintain specifications

```
Use the platonic-specs skill to refine all specifications in docs/specs/,
check consistency, and regenerate history, index, and namings.
```

**Result:** Validated specifications with updated history, index, and terminology files.

### Example 6: Gap analysis

```
Use the platonic-code-review skill to identify gaps between
all RFCs in docs/specs/ and the implementation in src/.
```

**Result:** Bi-directional analysis of unimplemented specs and undocumented code.

### Example 7: Validate implementation guide

```
Use the platonic-impl-guide skill to validate that docs/impl/rfc-001-auth-impl.md
does not contradict docs/specs/rfc-001-authentication.md.
```

**Result:** Validation report confirming the guide is spec-compliant or listing contradictions to fix.

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Author

**Xiaming Chen**
- Website: [https://xiaming.site/](https://xiaming.site/)
- GitHub: [@caesar0301](https://github.com/caesar0301)

---

*Built with ❤️ following the [Agent Skills](https://agentskills.io) standard*
