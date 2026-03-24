---
name: academic-research
description: "Complete academic research skill suite covering the full pipeline: paper reading (read/explain papers with storytelling), idea generation (brainstorm research directions), experiment design (plan experiments, ablation, baselines), proof writing (mathematical proofs, LaTeX theorems), paper writing (draft to camera-ready for top venues like NeurIPS/ICLR/ACL), paper review (structured 4-step review with scoring), and professor fit analysis (evaluate advisors, cold emails, interview strategy). Trigger keywords: read paper, brainstorm, experiment design, ablation, baseline, prove, theorem, derivation, write paper, improve my paper, review, reviewer feedback, professor fit, advisor selection, cold email, application strategy, LaTeX, research, NeurIPS, ICLR, ACL, arXiv."
license: MIT
compatibility: Works with Claude Code, ChatGPT/Codex CLI, and Gemini CLI.
metadata:
  author: research-skills
  version: "1.0.0"
---

# Academic Research Skills Suite

A complete academic research skill suite spanning the full lifecycle from paper reading to writing and peer review. Supports Claude Code, ChatGPT/Codex CLI, and Gemini CLI.

---

## Skill Routing Table

Load the corresponding sub-skill based on user intent:

| Trigger Condition | Sub-skill | Path | Description |
|----------|---------|------|------|
| read papers, explain papers, paper reading, cannot understand this paper | Paper Reading | [paper-reading/SKILL.md](paper-reading/SKILL.md) | Story-driven paper walkthrough style |
| brainstorm ideas, research directions, what should I do next | Idea Generation | [idea-generation/SKILL.md](idea-generation/SKILL.md) | Three-stage ideation: diverge -> search -> converge |
| experiment design, ablation, baseline, what experiments should I run | Experiment Design | [experiment-design/SKILL.md](experiment-design/SKILL.md) | Experiment design and planning |
| mathematical proof, prove, theorem, derivation | Proof Writer | [proof-writer/SKILL.md](proof-writer/SKILL.md) | Theoretical derivation and mathematical proofs |
| paper writing, improve my paper, LaTeX | Paper Writing | [paper-writing/SKILL.md](paper-writing/SKILL.md) | Paper writing (top-conference standard) |
| review, what would reviewers say, acceptance likelihood | Paper Review | [paper-review/SKILL.md](paper-review/SKILL.md) | 4-step academic review |
| professor analysis, professor fit, advisor selection, cold email, application strategy | Professor Fit Analyser | [professor-fit-analyser/SKILL.md](professor-fit-analyser/SKILL.md) | Advisor fit analysis and application strategy |

**Guidance**: When a user request matches one of the triggers above, read the corresponding `SKILL.md` and execute its instructions. If the request spans multiple skills, process them in the pipeline order below.

---

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

---

## Language Conventions

- **Default language**: Traditional Chinese (analysis, explanation, discussion)
- **English scenarios**: LaTeX generation, formal review output, mathematical symbols and theorem names
- **Academic terminology**: Refer to [shared/chinese-academic-glossary.md](shared/chinese-academic-glossary.md) for consistency

---

## Shared Resources

- [shared/chinese-academic-glossary.md](shared/chinese-academic-glossary.md) — bilingual academic terminology mapping
- [shared/conference-standards.md](shared/conference-standards.md) — top-conference formatting standards
- [shared/researcher-philosophies.md](shared/researcher-philosophies.md) — researcher philosophies and writing styles

---

## Cross-Platform Installation

This suite follows the [Agent Skills Open Standard](https://agentskills.io/specification) and can be used on the following platforms:

### Claude Code
```bash
# Method 1: Clone into skills directory
git clone <repo-url> ~/.claude/skills/academic-research

# Method 2: Use in a project
git clone <repo-url> .claude/skills/academic-research
```

### ChatGPT / Codex CLI
```bash
git clone <repo-url> ~/.codex/skills/academic-research
# or in a project
git clone <repo-url> .codex/skills/academic-research
```

### Gemini CLI
```bash
git clone <repo-url> ~/.gemini/skills/academic-research
# or in a project
git clone <repo-url> .gemini/skills/academic-research
```

### Generic Method
Copy this repository into your AI agent's skills directory. The root `SKILL.md` serves as the entry point, and the agent auto-discovers all sub-skills using the `*/SKILL.md` pattern.
