---
name: idea-generation
description: "A skill for generating academic research ideas—from divergence to convergence—to systematically produce high-quality research concepts. Use this skill whenever users want to brainstorm research directions, find new research ideas, or ask 'what should I study next?'. Trigger phrases include: brainstorm, idea generation, research direction, next step, what can I research, find gaps, research proposal. Suitable for idea generation at any stage of academic research."
license: MIT
compatibility: Works with Claude Code, ChatGPT/Codex CLI, and Gemini CLI.
metadata:
  author: research-skills
  version: "1.0.0"
---

# 02 — Idea Generation: Producing Academic Research Concepts

## Overview

This skill provides a systematic workflow for generating research ideas, helping researchers produce concepts with novelty, feasibility, and impact from scratch. The process has three stages: **Divergence**, **Literature Search Validation**, and **Convergence**, ending with a refined one-page research proposal.

This skill is suitable for:
- Master's and PhD students searching for thesis topics
- Researchers opening new research directions
- Cross-disciplinary teams brainstorming together
- Research groups running regular ideation sessions

---

## Three-Stage Workflow

### Overview

```
Stage 1: Divergence      Stage 2: Literature Validation      Stage 3: Convergence
─────────────────      ───────────────────────────      ─────────────────
Generate 10–20 ideas    Search related papers              Narrow down to 1
candidate ideas         verify novelty                     best idea
                        build literature table

[10 ideation frameworks] → [search strategy + tools] → [scoring matrix + filtering criteria]
```

---

## Stage 1: Divergence — Generate 10–20 Candidate Ideas

### Goal

Generate as many candidate ideas as possible without imposing early constraints. The key principle is **"quantity before quality"**—maximize breadth first, then go deeper.

### Preparation

1. **Define the exploration scope**: Set your broad research area (e.g., NLP, computer vision, reinforcement learning)
2. **Collect raw material**: Review papers you recently read, talks you attended, and observations from experiments
3. **Set time limits**: Spend 15–30 minutes per framework to avoid getting stuck in details too early

### 10 Ideation Frameworks

Below are 10 frameworks from different angles. It is recommended to use at least 3–5 of them to generate candidate ideas. See [references/brainstorming-frameworks.md](references/brainstorming-frameworks.md) for details.

#### Framework 1: Problem-First

Start from real-world pain points and identify research problems that are still inadequately solved.

- Observe bottlenecks in existing systems
- Collect user complaints and needs
- Examine failure cases on benchmarks

#### Framework 2: Solution-First (Find Applications from a Technique)

Start from a new technique or method and explore where it can be applied.

- What other problems can this new algorithm solve?
- Can a breakthrough in one field transfer to another?

#### Framework 3: Abstraction Ladder

Move across abstraction levels: rise from concrete issues to abstract principles, then descend to new concrete applications.

- Upward abstraction: What is the essence of this problem?
- Downward concretization: What can this principle be instantiated as?

#### Framework 4: Contradiction Hunting

Identify contradictions, assumption conflicts, or unquestioned defaults in existing methods.

- Which "common truths" actually lack evidence?
- Do two papers reach conflicting conclusions?

#### Framework 5: Cross-Domain Transfer

Import successful methods or concepts from other domains into your own.

- Can biological mechanisms inspire algorithm design?
- Can social science theories explain technical phenomena?

#### Framework 6: What Changed (Focus on Recent Shifts)

Track recent technical or environmental changes and ask what new possibilities they unlock.

- New hardware capabilities (larger models, faster inference)
- New data sources (multimodal data, synthetic data)
- New social demands (privacy, fairness, interpretability)

#### Framework 7: Failure Analysis

Look for opportunities in failed attempts, rejected papers, or underperforming methods.

- Why did this method fail? Can it be fixed?
- Does the failure point to a deeper underlying problem?

#### Framework 8: Simplicity Test

Challenge complex methods with simpler alternatives and test whether complexity is truly necessary.

- Were simple baselines compared fairly?
- Which components of complex methods are genuinely necessary?

#### Framework 9: Stakeholder Rotation

Reframe the problem from the perspectives of different users and stakeholders.

- What do end users care about most?
- What is the biggest pain point for developers?
- What information do decision makers need?

#### Framework 10: Combine / Decompose

Create new directions by combining or decomposing existing methods and concepts.

- Combine: What happens if Method A + Method B are integrated?
- Decompose: Which subsystem of a complex system deserves standalone study?

### Output of Stage 1

After divergence, you should have a list of 10–20 candidate ideas. Each idea should include:

| Field | Description |
|------|------|
| ID | Running index |
| Title | One-sentence description |
| Framework used | Which ideation framework was used |
| Summary | Initial concept in 2–3 sentences |
| Intuition score | Initial gut score from 1–5 |

---

## Stage 2: Literature Search Validation — Verify Novelty

### Goal

Validate the novelty of candidate ideas through systematic literature search and build a related-work table. The key is to **confirm the idea has not already been done**, while finding relevant prior work you can build on.

### Search Strategy

See [references/paper-search-strategy.md](references/paper-search-strategy.md) for details. Quick flow:

#### Step 1: Keyword Design

- Create 3–5 keyword sets for each candidate idea
- Expand with synonyms, hypernyms, and hyponyms
- Combine English and Chinese keywords

#### Step 2: Multi-Platform Search

- **Semantic Scholar**: semantic search, good for exploratory search
- **Google Scholar**: broad coverage, good for confirmation search
- **arXiv**: latest preprints, good for frontier tracking
- **DBLP**: comprehensive index for computer science
- **ACL Anthology**: specialized for NLP

#### Step 3: Snowballing

- Forward tracking: after finding key papers, see who cited them
- Backward tracking: check who key papers cited
- Author tracking: review other work by key authors

#### Step 4: Novelty Assessment

For each candidate idea, assign a novelty outcome:

| Outcome | Description | Action |
|----------|------|------|
| Fully new | No directly relevant prior work found | Keep, then verify feasibility |
| Partially overlapping | Related but not identical work exists | Identify differences and refine idea |
| Already done | Nearly identical work found | Discard or substantially revise |

### Output of Stage 2

After completion, you should have:

1. **Filtered candidate list**: remove already-done ideas; typically 5–10 remain
2. **Literature table**: for each surviving idea, 5–10 related papers
3. **Novelty annotations**: novelty outcome plus key differences per idea

---

## Stage 3: Convergence — Select One Best Idea

### Goal

From the surviving candidates, use systematic evaluation and filtering to select one best idea for deep development.

### Convergence Process

See [references/idea-convergence.md](references/idea-convergence.md) for details. Quick flow:

#### Step 1: Eliminate

Quickly remove clearly infeasible ideas:
- Technically impossible to complete in a reasonable time
- Lacking required data or compute resources
- Insufficient novelty

#### Step 2: Merge

Check whether candidate ideas can be merged:
- Do two ideas address different facets of the same problem?
- Can merging produce a stronger contribution?

#### Step 3: Refine

Refine remaining candidates:
- Narrow scope to make the problem more concrete
- Clarify technical contributions
- Sketch an initial experiment design

#### Step 4: Scoring Matrix

Use a quantitative scoring matrix. See [references/evaluation-matrix.md](references/evaluation-matrix.md) for the template.

Scoring dimensions:

| Dimension | Weight | Description |
|------|------|------|
| Novelty | 25% | Degree of difference from prior work |
| Feasibility | 25% | Likelihood of completion under current resources |
| Impact | 20% | Potential contribution to the field |
| Timeliness | 15% | Alignment with current research trends |
| Personal interest | 15% | Your motivation and enthusiasm |

#### Step 5: Final Decision

- Select the idea with the highest weighted total score
- Also consider: does your intuition agree? Do you have enough motivation to execute it?
- If logic and intuition conflict, spend time identifying why

### Common Pitfalls

In convergence, watch out for these cognitive biases:

1. **Confirmation bias**: searching only for evidence supporting your preferred idea
2. **Sunk cost fallacy**: refusing to drop weak ideas due to prior investment
3. **Novelty bias**: over-prioritizing novelty while ignoring feasibility
4. **Bandwagon effect**: following a trend only because it is popular
5. **Perfectionism**: waiting forever for a "perfect" idea before starting

---

## Final Outputs

After all three stages, you should produce four documents:

### 1. Candidate List

A complete list of all candidate ideas with status labels (survive/eliminated/merged).

### 2. Literature Table

Related-work list for each surviving idea, in this format:

```
## Idea: [Title]

1. [Author] (Year). [Paper Title]. [Conference/Journal].
   - Relevance: [High/Medium/Low]
   - Relation to this idea: [Brief note]

2. ...
```

### 3. Scoring Matrix

Quantitative scores for all surviving ideas, including per-dimension scores and weighted totals.

### 4. 1-Page Proposal

A one-page proposal for the final selected idea, including:

```
# [Research Title]

## Problem Statement
- What problem are you solving? Why is it important?

## Related Work & Gap
- What do existing methods do? What are the gaps?

## Proposed Approach
- What will you do? What is the core idea?

## Expected Contributions
- What contributions do you expect?

## Preliminary Experiment Plan
- Which datasets, metrics, and baselines will you use?

## Risks & Mitigation
- What are the main risks? What are contingency plans?

## Timeline
- Planned milestones and schedule
```

---

## Process Checklist

### Divergence Stage

- [ ] Set exploration scope and time limits
- [ ] Use at least 3 ideation frameworks
- [ ] Generate at least 10 candidate ideas
- [ ] For each idea: title, summary, intuition score
- [ ] Avoid premature filtering in this stage

### Literature Validation Stage

- [ ] Design search keywords for each idea
- [ ] Use at least 2 search platforms
- [ ] Apply snowballing to track key papers
- [ ] Annotate novelty outcome for each idea
- [ ] Build literature table

### Convergence Stage

- [ ] Eliminate clearly infeasible ideas
- [ ] Check mergeable ideas
- [ ] Refine remaining candidates
- [ ] Complete scoring matrix
- [ ] Select final idea
- [ ] Write 1-page proposal
- [ ] Check for cognitive biases

---

## Time Recommendations

| Stage | Suggested Time | Notes |
|------|----------|------|
| Divergence | 2–4 hours | Can be split across 2–3 days |
| Literature validation | 4–8 hours | About 30–60 minutes per idea |
| Convergence | 2–3 hours | Preferably done in one session |
| Proposal writing | 1–2 hours | Do immediately after convergence |
| **Total** | **9–17 hours** | **About 1–2 weeks** |

---

## Reference Resources

- [Detailed Ideation Frameworks](references/brainstorming-frameworks.md)
- [Literature Search Strategy](references/paper-search-strategy.md)
- [Convergence Process and Filtering Criteria](references/idea-convergence.md)
- [Scoring Matrix Template](references/evaluation-matrix.md)

---

## Advanced Suggestions

### Build an Idea Bank

- Record triggered ideas while reading papers
- Periodically review your idea bank and combine old ideas with new knowledge
- Use tags to classify ideas (domain, method, problem type)

### Interact with Others

- Explain your ideas to people from other fields and gather feedback
- Join reading groups and seminars to spark new perspectives
- Find an "idea buddy" for regular exchange

### Iterative Ideation

- Do not expect a perfect idea in one pass
- Allow yourself to return to divergence using new information
- Strong ideas are often products of multiple iterations

### Record and Reflect

- Record each ideation session, including ideas not selected
- Reflect on which frameworks work best for you
- Build a personal ideation workflow and preference profile
