# Idea Scoring Matrix

This document provides a quantitative tool for evaluating ideas, helping you make evidence-based decisions during convergence.

---

## I. Scoring Dimension Definitions

### Dimension 1: Novelty — Weight 25%

Measures how different the idea is from existing work.

| Score | Definition | Criteria |
|------|------|----------|
| 5 | Groundbreaking | Proposes a new problem or method with no close prior work |
| 4 | Highly novel | Clear differentiation even when related work exists |
| 3 | Moderately novel | Contains new elements but follows known overall patterns |
| 2 | Low novelty | Mostly incremental improvement or direct application |
| 1 | No novelty | Already done or very similar work exists |

**Self-check**:
- Did the literature search find highly similar work?
- Can I state the key difference from the closest work in one sentence?
- Would reviewers view this as sufficiently novel?

### Dimension 2: Feasibility — Weight 25%

Measures likelihood of successful completion under current conditions.

| Score | Definition | Criteria |
|------|------|----------|
| 5 | Highly feasible | Adequate resources, mature techniques, likely smooth execution |
| 4 | Mostly feasible | Some challenges but manageable risk |
| 3 | Conditionally feasible | Requires specific resources or technical breakthroughs |
| 2 | Barely feasible | Major obstacles and low success probability |
| 1 | Infeasible | Cannot be completed under current conditions |

**Self-check**:
- Do I have enough compute resources?
- Is the dataset available or reasonably obtainable?
- Do I have (or can learn) required skills?
- Can this finish before the deadline?
- Are external collaborators needed, and can I get them?

### Dimension 3: Impact — Weight 20%

Measures potential contribution to the field and society.

| Score | Definition | Criteria |
|------|------|----------|
| 5 | Transformative | Could shift research direction or paradigm |
| 4 | High impact | Substantial contribution to an important problem |
| 3 | Moderate impact | Meaningful progress on a specific sub-problem |
| 2 | Low impact | Incremental improvement with limited scope |
| 1 | Very low impact | Problem is too narrow or niche |

**Self-check**:
- How many researchers care about this problem?
- Can others cite or build on these results?
- Is there a clear downstream application?
- What venue tier is this suitable for?

### Dimension 4: Timeliness — Weight 15%

Measures whether the idea fits the right time window.

| Score | Definition | Criteria |
|------|------|----------|
| 5 | Perfect timing | Enabling tech just matured; attention is high; competition not saturated |
| 4 | Good timing | Direction is rising with room to grow |
| 3 | Neutral | Timing is neither especially good nor bad |
| 2 | Slightly late | Direction is saturating or losing attention |
| 1 | Outdated | Direction is outdated or competition is extremely intense |

**Self-check**:
- Did recent breakthroughs make this feasible now?
- Are top-venue papers on this topic trending up or down?
- Are major groups still investing here?
- Can I finish before competitors?

### Dimension 5: Personal Interest — Weight 15%

Measures your motivation and enthusiasm for the idea.

| Score | Definition | Criteria |
|------|------|----------|
| 5 | Very excited | Eager to start immediately and invest major time |
| 4 | Interested | Genuinely interested in deep exploration |
| 3 | Neutral | Neither excited nor resistant |
| 2 | Reluctant | Limited interest but recognizes value |
| 1 | Not interested | Would not do it even if valuable |

**Self-check**:
- Do I feel excited when thinking about this idea?
- Would I spend late nights or weekends on it?
- Would I regret not doing it?
- Will this help me grow?

---

## II. Scoring Matrix Templates

### Blank Template

| Candidate Idea | Novelty (x0.25) | Feasibility (x0.25) | Impact (x0.20) | Timeliness (x0.15) | Personal Interest (x0.15) | Weighted Total |
|-----------|----------------|----------------|----------------|----------------|-------------------|----------|
| Idea A    |     /5         |     /5         |     /5         |     /5         |      /5           |          |
| Idea B    |     /5         |     /5         |     /5         |     /5         |      /5           |          |
| Idea C    |     /5         |     /5         |     /5         |     /5         |      /5           |          |
| Idea D    |     /5         |     /5         |     /5         |     /5         |      /5           |          |
| Idea E    |     /5         |     /5         |     /5         |     /5         |      /5           |          |

### Weighted Total Formula

```
Weighted total = Novelty × 0.25 + Feasibility × 0.25 + Impact × 0.20 + Timeliness × 0.15 + Personal Interest × 0.15
```

**Example calculation**:

| Dimension | Score | Weight | Weighted Score |
|------|------|------|----------|
| Novelty | 4 | 0.25 | 1.00 |
| Feasibility | 3 | 0.25 | 0.75 |
| Impact | 4 | 0.20 | 0.80 |
| Timeliness | 5 | 0.15 | 0.75 |
| Personal Interest | 4 | 0.15 | 0.60 |
| **Total** | | | **3.90** |

### Filled Example

| Candidate Idea | Novelty (x0.25) | Feasibility (x0.25) | Impact (x0.20) | Timeliness (x0.15) | Personal Interest (x0.15) | Weighted Total |
|-----------|----------------|----------------|----------------|----------------|-------------------|----------|
| Long-context summarization improvement | 3 | 4 | 3 | 3 | 3 | 3.20 |
| Cross-lingual knowledge transfer | 4 | 3 | 4 | 4 | 5 | 3.90 |
| Low-resource language NER | 4 | 4 | 3 | 3 | 2 | 3.35 |
| Code generation security | 5 | 3 | 5 | 5 | 4 | 4.40 |
| Multimodal sentiment analysis | 3 | 5 | 3 | 2 | 4 | 3.45 |

In this example, "Code generation security" ranks first with 4.40.

---

## III. Weight Adjustment Guide

The weights above are suggested defaults. You can adjust based on your context.

### Scenario 1: PhD student selecting dissertation topic

Emphasize long-term feasibility and personal interest due to multi-year commitment.

| Dimension | Suggested Weight |
|------|----------|
| Novelty | 20% |
| Feasibility | 20% |
| Impact | 25% |
| Timeliness | 10% |
| Personal Interest | 25% |

### Scenario 2: Racing a conference deadline

Emphasize feasibility and timeliness for short-cycle delivery.

| Dimension | Suggested Weight |
|------|----------|
| Novelty | 25% |
| Feasibility | 35% |
| Impact | 15% |
| Timeliness | 15% |
| Personal Interest | 10% |

### Scenario 3: Exploring a brand-new direction

Emphasize novelty and impact, accepting higher risk.

| Dimension | Suggested Weight |
|------|----------|
| Novelty | 35% |
| Feasibility | 15% |
| Impact | 30% |
| Timeliness | 10% |
| Personal Interest | 10% |

### Scenario 4: Master's student selecting graduation topic

Emphasize feasibility to ensure completion within limited time.

| Dimension | Suggested Weight |
|------|----------|
| Novelty | 15% |
| Feasibility | 35% |
| Impact | 15% |
| Timeliness | 15% |
| Personal Interest | 20% |

---

## IV. Decision Guide

### 4.1 Clear Winner

If one idea clearly exceeds others (gap > 0.5), select it directly.

### 4.2 Close Scores

If top-two gap < 0.5, perform deeper comparison:

1. **Sensitivity analysis**
   - Does ranking change if weights change?
   - Is the conclusion stable under scoring uncertainty?
   - Try multiple weight settings

2. **Scenario simulation**
   - Best case: what publication level can each reach?
   - Worst case: what output remains?
   - If failure occurs, which teaches more?

3. **Intuition vote**
   - If you must choose one now, which one?
   - If you choose A, do you regret not choosing B?

### 4.3 No Strong Candidates

If all candidates score below 2.5:

- Return to divergence and generate new candidates
- Check whether scoring is overly strict
- Consider whether exploration scope is too narrow
- Discuss with advisor or peers

### 4.4 Post-Decision Validation

After selecting, run these checks:

1. **Elevator test**: Can you explain the idea to a non-expert in 30 seconds?
2. **Paper test**: Can you envision a clear title and abstract?
3. **Motivation test**: Are you eager to start tomorrow morning?
4. **Risk test**: Can the biggest risk be tested in the first two weeks?

---

## V. Common Scoring Questions

### Q1: How do I reduce subjective bias?

- Score descriptions before names when possible
- Ask 2–3 peers to score independently and average
- Score on multiple days and use median
- Score one dimension across all ideas before moving to next dimension

### Q2: What if I am unsure about one dimension?

- Assign a middle score (3) and mark as uncertain
- Gather more evidence for that dimension
- Lower the weight of highly uncertain dimensions

### Q3: Can I customize dimensions?

Yes. Add or revise dimensions based on your needs. Common extras:

| Extra Dimension | Description |
|----------|------|
| Data availability | How easy required data is to obtain |
| Team fit | Alignment with team expertise |
| Extension potential | Whether it can branch into multiple papers |
| Industry value | Commercial applicability |
| Ethical risk | Potential ethical/social risk |

### Q4: What if matrix results conflict with intuition?

- Intuition often captures factors quantitative scoring misses
- Analyze which dimension causes the mismatch
- You may need weight adjustment or new dimensions
- Use **informed intuition**: intuition after structured analysis is usually more reliable

---

## VI. Advanced Usage

### 6.1 Multi-Person Scoring

For team decisions:

1. Each member fills matrix independently
2. Aggregate all scores
3. Discuss dimensions with large disagreement
4. Update scores after consensus
5. Compute final weighted totals

### 6.2 Iterative Scoring

As research progresses, update scores regularly:

1. Re-evaluate monthly
2. Update scores based on new information
3. Revisit choice if ranking changes
4. Record why scores changed

### 6.3 Combined Decision Tools

Use the matrix with other tools:

- **SWOT analysis** for top candidates
- **Decision trees** for if-then scenarios
- **Risk matrix** for risk-return comparison
