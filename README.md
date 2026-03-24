# Academic Research Skills

A complete academic research skill suite aligned with the [Agent Skills Open Standard](https://agentskills.io/specification). Supports **Claude Code**, **ChatGPT / Codex CLI**, and **Gemini CLI**.

## Usage  
Claude Code: `git clone <repo> ~/.claude/skills/academic-research` 

ChatGPT/Codex CLI: `git clone <repo> ~/.codex/skills/academic-research` 

Gemini CLI: `git clone <repo> ~/.gemini/skills/academic-research` 

## Feature Overview

| # | Skill | Description |
|---|-------|------|
| 01 | Paper Reading | Story-driven paper walkthrough style |
| 02 | Idea Generation | Three-stage ideation: diverge -> search -> converge |
| 03 | Experiment Design | Hypothesis -> variables -> metrics -> baseline -> ablation |
| 04 | Proof Writer | Theoretical derivation and LaTeX mathematical proofs |
| 05 | Paper Writing | Top-conference-standard paper writing |
| 06 | Paper Review | 4-step academic review workflow |
| 07 | Professor Fit Analyser | Advisor fit analysis and application strategy |

## Research Pipeline

```
Advisor analysis ─┐
       07        ↓
Paper reading -> Idea generation -> Experiment design -> Theoretical proof -> Paper writing -> Review and revision
      01               02                  03                  04               05                 06
                                                                             ↑                      │
                                                                             └──────────────────────┘
                                                                            (revision cycle)
```

## Installation and Use

This suite supports three major AI agent platforms. Choose your platform and clone this repository into the matching skills directory.

### Claude Code

```bash
# User-level install (global)
git clone <repo-url> ~/.claude/skills/academic-research

# Project-level install (this project only)
git clone <repo-url> .claude/skills/academic-research
```

Use slash commands in Claude Code:

```
/read-paper          # Start walking through a paper
/brainstorm          # Generate new ideas from papers
/experiment          # Design an experiment plan
/prove               # Write mathematical proofs
/write-paper         # Draft paper sections
/review              # Review a paper
/prof-fit            # Analyze advisor fit
```

### ChatGPT / Codex CLI

```bash
# User-level install
git clone <repo-url> ~/.codex/skills/academic-research

# Project-level install
git clone <repo-url> .codex/skills/academic-research
```

Skills are auto-discovered. You can mention `@academic-research` to activate, or let the agent match tasks automatically.

### Gemini CLI

```bash
# User-level install
git clone <repo-url> ~/.gemini/skills/academic-research

# Project-level install
git clone <repo-url> .gemini/skills/academic-research
```

Skills are matched automatically through the `activate_skill` mechanism.

### Generic Setup

Copy this repository into your AI agent's skills directory. The root `SKILL.md` acts as the entry point, and the agent auto-discovers all sub-skills via the `*/SKILL.md` pattern.

## Directory Structure

```
├── SKILL.md                     # Root entry (monorepo skill routing to sub-skills)
├── CLAUDE.md                    # Claude Code orchestrator (defines slash-command routing)
├── paper-reading/               # Paper reading
│   ├── SKILL.md
│   └── references/
├── idea-generation/             # Idea generation
│   ├── SKILL.md
│   └── references/
├── experiment-design/           # Experiment design
│   ├── SKILL.md
│   ├── references/
│   └── templates/
├── proof-writer/                # Theoretical proofs
│   ├── SKILL.md
│   └── references/
├── paper-writing/               # Paper writing
│   ├── SKILL.md
│   └── references/
├── paper-review/                # Academic reviewing
│   ├── SKILL.md
│   ├── references/
│   └── templates/
├── professor-fit-analyser/      # Professor fit analysis
│   ├── SKILL.md
│   ├── references/
│   └── templates/
└── shared/                      # Shared resources
    ├── chinese-academic-glossary.md
    ├── conference-standards.md
    └── researcher-philosophies.md
```

## Language Notes

- Analysis, explanation, discussion: Traditional Chinese
- LaTeX output and formal review writing: English
- Mathematical symbols and theorem names: English

## Design References

- [Agent Skills Open Standard](https://agentskills.io/specification)
- [Orchestra-Research/AI-Research-SKILLs](https://github.com/Orchestra-Research/AI-Research-SKILLs)
- [Master-cai/Research-Paper-Writing-Skills](https://github.com/Master-cai/Research-Paper-Writing-Skills)

## License

MIT
