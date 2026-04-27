# Kiro Steering Files

Steering files for [Kiro](https://kiro.dev) IDE and CLI — reusable prompts that guide AI agent behavior across projects.

## Structure

```
├── global/                  # Machine-wide steering → ~/.kiro/steering/
│   ├── spec-workflow.md     # Spec-driven development workflow (req → design → tasks)
│   └── spec-creation-guide.md  # Step-by-step guide for creating specs
└── edi/                     # EDI parser project steering → edi/.kiro/steering/
    ├── implementation-rules.md  # Rust coding rules, X12 parsing rules, git practices
    ├── project-specification.md # Project architecture and patterns
    └── test-guidelines.md       # Testing methodology and demo file locations
```

## Installation

### Global (all projects)
```bash
cp global/*.md ~/.kiro/steering/
```

### EDI project
```bash
cp edi/*.md /path/to/edi/.kiro/steering/
```

## What are steering files?

Steering files provide persistent context and instructions to the Kiro AI agent. They're markdown files with front-matter controlling when they're included:

- `inclusion: always` — Included in every interaction (default)
- `inclusion: manual` — Only when explicitly referenced
- `inclusion: fileMatch` + `fileMatchPattern: 'README*'` — When matching files are read

## Origin

The spec workflow files were reverse-engineered from Kiro IDE's spec creation system prompts to make the same capability available in the Kiro CLI.
