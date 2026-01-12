# Vendatta Config Inizio

**Battle-tested agent rules, skills, and commands for AI coding assistants**

This repository provides a comprehensive collection of production-ready configurations for AI coding assistants like OpenCode, Cursor, and Claude Code.

## 📦 What's Included

### Core Plugins

- **core**: Essential rules, skills, and commands for any project
  - TDD Best Practices
  - Git Workflow
  - Playwright Skill
  - Shell Executor
  - Test Suite Command
  - Lint All Command

### Language-Specific Plugins

- **golang**: Go development guidelines and conventions
  - Senior Go guidelines (error handling, concurrency, package structure)
  - Testify usage patterns
  - Interface design principles

- **node**: Node.js and TypeScript/JavaScript guidelines
  - TypeScript conventions
  - Type safety patterns
  - Async/await best practices

### Infrastructure Plugins

- **docker**: Containerization best practices
  - Production-ready Docker patterns
  - Multi-stage builds
  - Security guidelines

## 🏗️ Plugin Structure

Each plugin follows this structure:

```
plugins/
└── <plugin-name>/
    ├── plugin.yaml              # Plugin manifest
    └── templates/
        ├── rules/              # Coding standards and guidelines
        ├── skills/             # AI capabilities (web, browser, etc.)
        └── commands/          # Reusable development workflows
```

### Plugin Manifest (plugin.yaml)

```yaml
name: <plugin-name>
version: 1.0.0
description: <plugin description>
conditions:
  - file: <detect-file>     # File that triggers plugin load
  - file: <another-file>
```

### Rule Template

```yaml
---
title: <rule title>
description: <what this rule enforces>
globs: ["**/*.<ext>", "**/*.<ext>"]
alwaysApply: true
source: <authoritative source URL>
references:
  - <additional reading>
  - <reference link>
---

# RULE TITLE

<rule content in markdown>
```

### Skill Template

```yaml
---
name: <skill-name>
description: <what this skill enables>
parameters:
  type: object
  properties:
    <param-name>: { type: string, description: "..." }
execute:
  command: "<command>"
  args: ["<arg1>", "{{.<param>}}"]
source: <reference URL>
references:
  - <additional resources>
---

# Skill Title

<skill documentation in markdown>
```

### Command Template

```yaml
---
name: <command-name>
description: <what this command does>
steps:
  - name: <step name>
    command: "<command>"
---

# Command Title

<command documentation in markdown>
```

## 🚀 Usage with Vendatta

1. Add plugin reference to your `.vendatta/config.yaml`:

```yaml
extends:
  - inizio/vendatta-config-inizio
```

2. Vendatta automatically:
   - Clones the latest plugin version
   - Applies rules based on file detection
   - Activates skills for your AI assistant
   - Makes commands available

## 🤝 Contributing

This repository follows the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
feat: add new plugin
fix: correct rule behavior
docs: update documentation
test: add test coverage
```

### Adding a New Plugin

1. Create plugin directory: `plugins/<plugin-name>/`
2. Add `plugin.yaml` with manifest
3. Create templates in `templates/rules/`, `templates/skills/`, or `templates/commands/`
4. Follow the template structure above
5. Test by adding to your `.vendatta/config.yaml`

## 📚 References

This repository aggregates best practices from:

- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) - Curated Claude Code resources
- [agent-rules](https://github.com/steipete/agent-rules) - Peter Steinberger's agent rules
- [agent-scripts](https://github.com/steipete/agent-scripts) - Shared agent helper scripts
- Conventional Commits specification
- Official language style guides (Go, TypeScript, etc.)

## 📄 License

MIT License - See LICENSE file for details
