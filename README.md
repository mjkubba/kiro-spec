# Kiro Spec

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Made for Kiro CLI](https://img.shields.io/badge/Made%20for-Kiro%20CLI-blue)](https://kiro.dev)

Reusable steering files for [Kiro](https://kiro.dev) CLI — spec-driven development workflow prompts reverse-engineered from Kiro IDE.

## Files

| File | Purpose |
|------|---------|
| `global/spec-workflow.md` | Full spec workflow reference: 3-phase process (requirements → design → tasks), templates, task format, bugfix methodology, session handling |
| `global/spec-creation-guide.md` | Step-by-step guide for creating specs from scratch with templates and quality rules |

## Installation

```bash
cp global/*.md ~/.kiro/steering/
```

## What does this do?

These steering files teach the Kiro CLI agent how to do structured spec-driven development — the same workflow that Kiro IDE uses with its built-in spec feature:

1. **Requirements** — User stories + acceptance criteria using EARS syntax
2. **Design** — Architecture, correctness properties, error handling, testing strategy
3. **Tasks** — Ordered implementation plan with checkboxes and requirement traceability

Supports feature specs (requirements-first or design-first) and bugfix specs (bug condition methodology).

## Usage

Once installed, ask the CLI agent to create a spec:

```
> create a spec for user authentication
> spec out a caching layer
> plan the API redesign
```

The agent will follow the workflow, creating `requirements.md` → `design.md` → `tasks.md` under `.kiro/specs/{feature-name}/`.

## Steering file inclusion

Both files use `inclusion: manual` front-matter — they're loaded into the knowledge base but don't bloat every conversation. The agent finds them via semantic search when spec-related requests come in.

## Compatibility

Tested with Kiro CLI. The steering files follow the standard `.kiro/steering/` convention and should work with any version that supports steering file loading.

## Contributing

Issues and PRs are welcome! If you have improvements to the workflow templates or want to add new steering files, feel free to open a PR.

## License

[MIT](LICENSE)
