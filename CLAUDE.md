# Academic Research Skills — Orchestrator

This repository provides a complete academic research skill suite, covering the full workflow from paper reading to writing and peer review.

This suite follows the [Agent Skills Open Standard](https://agentskills.io/specification) and supports Claude Code, ChatGPT/Codex CLI, and Gemini CLI.

## Skill Routing

| Command | Skill | Description |
|------|-------|------|
| `/read-paper` | `paper-reading/SKILL.md` | Story-driven paper walkthrough style |
| `/brainstorm` | `idea-generation/SKILL.md` | Three-stage ideation: diverge -> search -> converge |
| `/experiment` | `experiment-design/SKILL.md` | Experiment design and planning |
| `/prove` | `proof-writer/SKILL.md` | Theoretical derivation and mathematical proofs |
| `/write-paper` | `paper-writing/SKILL.md` | Paper writing (top-conference standard) |
| `/review` | `paper-review/SKILL.md` | 4-step academic review process |
| `/prof-fit` | `professor-fit-analyser/SKILL.md` | Advisor fit analysis |

## Skill Pipeline

```
professor-fit-analyser ─┐
                        ↓
paper-reading ──→ idea-generation ──→ experiment-design
      │                                       │
      ↓                                       ↓
paper-review ←── paper-writing ←──── proof-writer
      │                 ↑
      └─────────────────┘  (revision cycle)
```

## Language Conventions

- **Default language**: English for all analysis, explanation, discussion, and outputs
- **Specialized content**: LaTeX generation, formal review output, and mathematical symbols/theorem names should also remain in English
- **Academic terminology**: Use consistent and standard English terminology

## Quality Standards

- Every `SKILL.md` must include YAML frontmatter compliant with the [agentskills.io standard](https://agentskills.io/specification) (required: name, description; optional: license, compatibility, metadata)
- Recommended length for each `SKILL.md`: 200-500 lines
- Reference files provide detailed guidance, and `SKILL.md` should reference them via relative paths
- All templates should use Markdown or LaTeX format

## Cross-Reference Rules

- Skills may reference each other via relative paths, for example: `../paper-writing/SKILL.md`
- Shared resources are stored in the `shared/` directory
- Each skill's `references/` directory should only contain skill-specific materials

## Usage

1. Clone this repository into your working directory
2. Open that directory in Claude Code
3. Use the `/` commands in the table above to activate the corresponding skill
4. Follow the Skill Pipeline to complete the end-to-end research workflow
