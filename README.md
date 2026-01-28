# AI Coding Skills

A professional collection of [Agent Skills](https://agentskills.io) for AI-powered development workflows.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Agent Skills Format](https://img.shields.io/badge/format-Agent%20Skills%201.0-blue)](https://agentskills.io)

## Overview

This repository provides production-ready Agent Skills that enhance AI agent capabilities for development workflows. All skills follow the [Agent Skills specification](https://agentskills.io/specification) for maximum compatibility across AI coding agents.

**Agent Skills** are a simple, open format for giving agents new capabilities and expertise. Write once, use everywhere.

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

### Quick Install via Marketplace

If your AI agent supports marketplace installation:

```bash
# For Claude Code CLI
/plugin marketplace add caesar0301/ai-coding-skills
/plugin
```

### Manual Installation

Clone this repository to your skills directory:

```bash
# Clone to your agent's skills directory
git clone https://github.com/caesar0301/ai-coding-skills.git ~/.claude/skills/ai-coding-skills

# Or use a specific skills directory
git clone https://github.com/caesar0301/ai-coding-skills.git /path/to/skills/
```

## Usage

### Using with AI Coding Agents

Once installed, skills are automatically discovered by compatible agents. Simply reference them in your conversations:

**Method 1: Natural Language (Recommended)**

```
Use the platonic-coding-specs skill to initialize specs 
for project "MyProject" in ./specs
```

```
Use the review-code skill to review my changes in the 
current branch, focusing on security issues
```

**Method 2: Explicit Reference**

```
Read the platonic-coding-specs skill's references/init-specs.md
and apply it with project name "MyProject" and specs directory "./specs"
```

**Method 3: Step-by-Step**

```
1. Use review-code skill to audit src/api/UserService.ts
2. Generate a report with prioritized findings
3. Show me the critical and high-priority issues
```

### Supported AI Agents

These skills work with any agent supporting the [Agent Skills format](https://agentskills.io):

- ✅ Claude Code CLI
- ✅ Cursor
- ✅ Windsurf
- ✅ Other Agent Skills-compatible agents

## Project Structure

```
ai-coding-skills/
├── .claude-plugin/
│   └── marketplace.json            # Marketplace configuration
├── skills/
│   ├── platonic-coding-specs/      # RFC specification management
│   │   ├── SKILL.md                # Skill definition (Agent Skills format)
│   │   ├── README.md               # User documentation
│   │   ├── references/             # Reference documentation
│   │   │   ├── REFERENCE.md        # Complete guide
│   │   │   └── *.md                # Operation references
│   │   └── assets/                 # Templates and resources
│   │       └── *.template          # RFC templates
│   └── review-code-per-specs/      # Spec-to-code validation
│       ├── SKILL.md                # Skill definition (Agent Skills format)
│       ├── README.md               # User documentation
│       ├── references/             # Review procedures
│       │   └── REFERENCE.md        # Complete review guide
│       └── assets/                 # Review templates
├── LICENSE
└── README.md                       # This file
```

Each skill follows the [Agent Skills standard](https://agentskills.io/specification):
- `SKILL.md` - Required skill definition with metadata and instructions
- `references/` - Additional documentation loaded on demand
- `assets/` - Templates, resources, and static files

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

## Contributing

Contributions are welcome! To add or improve skills:

1. Follow the [Agent Skills specification](https://agentskills.io/specification)
2. Include comprehensive documentation
3. Provide examples and usage guides
4. Test with multiple AI agents
5. Submit a pull request

## Best Practices

### For Skill Users

1. **Read skill documentation** before first use
2. **Start with examples** to understand capabilities
3. **Customize for your project** - adapt templates and references
4. **Provide context** - give agents necessary information
5. **Iterate and refine** - use skills regularly for best results

### For Skill Authors

1. **Follow the Agent Skills spec** for compatibility
2. **Keep SKILL.md concise** (< 500 lines recommended)
3. **Use progressive disclosure** - move details to references/
4. **Provide clear examples** in documentation
5. **Test across agents** - ensure broad compatibility

## About Agent Skills

This project follows the [Agent Skills](https://agentskills.io) format, an open standard maintained by [Anthropic](https://anthropic.com) for giving AI agents new capabilities.

**Key Benefits:**
- 📝 Simple format (just folders with SKILL.md files)
- 🔄 Reusable across different AI agents
- 📦 Easy to share and distribute
- 🎯 Progressive disclosure for efficient context use
- 🤝 Open standard, community-driven

Learn more:
- [Agent Skills Documentation](https://agentskills.io)
- [Format Specification](https://agentskills.io/specification)
- [Integration Guide](https://agentskills.io/integrate-skills)

## Resources

- **Documentation**: See individual skill README files
- **Examples**: Check each skill's REFERENCE.md for detailed examples
- **Issues**: [GitHub Issues](https://github.com/caesar0301/ai-coding-skills/issues)
- **Discussions**: [GitHub Discussions](https://github.com/caesar0301/ai-coding-skills/discussions)

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Author

**Xiaming Chen**
- Website: [https://xiaming.site/](https://xiaming.site/)
- GitHub: [@caesar0301](https://github.com/caesar0301)

---

*Built with ❤️ following the [Agent Skills](https://agentskills.io) standard*
