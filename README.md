# Coding Rules for AI Coding Agents

Opinionated reusable coding rules for AI-assisted development. This repository
provides a baseline `AGENTS.md`, `CLAUDE.md`, Cursor rule, and focused rule
documents for service-first architecture, typed validation, intent-based naming,
and modern Docker Compose conventions.

Use it as a starting ruleset for coding agents, then customize it for your own
project.

## Why This Exists

AI coding agents produce better code when rules are short, explicit, and close
to the repository. This template gives agents a portable baseline for common
engineering expectations and helps teams avoid repeating the same instructions
in every chat.

## Supported Agents

| Tool | File |
| --- | --- |
| Generic agents / Codex-style agents | `AGENTS.md` |
| Claude Code | `CLAUDE.md` with `@AGENTS.md` |
| Cursor | `.cursor/rules/read-agents-md.mdc` |
| Agent frameworks using `.agents/rules` | `.agents/rules/read-agents-md.md` |

If your tool does not support include syntax like `@AGENTS.md`, copy the
content from `AGENTS.md` directly into that tool's rule file.

## Quick Start

Copy the baseline files into your project:

```bash
cp AGENTS.md /path/to/your/project/AGENTS.md
cp CLAUDE.md /path/to/your/project/CLAUDE.md
cp -R docs /path/to/your/project/docs
mkdir -p /path/to/your/project/.cursor/rules
cp .cursor/rules/read-agents-md.mdc /path/to/your/project/.cursor/rules/
mkdir -p /path/to/your/project/.agents/rules
cp .agents/rules/read-agents-md.md /path/to/your/project/.agents/rules/
```

Then edit the copied files to match your project's architecture, tools, and
team preferences.

## What's Included

- `AGENTS.md`: compact entry point for agent guidance.
- `CLAUDE.md`: Claude Code bridge that includes `AGENTS.md`.
- `.cursor/rules/read-agents-md.mdc`: Cursor rule that loads `AGENTS.md`.
- `.agents/rules/read-agents-md.md`: always-on bridge for agent frameworks that
  read `.agents/rules`.
- `docs/`: focused rule documents with Good/Bad examples.

## Rule Catalog

| Rule | Purpose |
| --- | --- |
| `docs/service-first-architecture.md` | Keeps business logic reusable and interface layers thin. |
| `docs/data-shapes-validation.md` | Keeps data shape and validation in Pydantic or Zod models. |
| `docs/naming.md` | Pushes agents toward intent-based names instead of vague type suffixes. |
| `docs/docker-compose.md` | Captures modern Docker Compose conventions and practical exceptions. |

## Customize

Replace this README with your real project README after copying the template.
Keep the rule files only if they match how your project should be built. Remove
irrelevant rules, tighten loose ones, and add project-specific guidance where it
helps agents make better changes.

## Contributing

Contributions are welcome when they keep the rules reusable, concise, and
agent-friendly. Prefer small rule documents with concrete examples over broad
policy text.

## License

MIT
