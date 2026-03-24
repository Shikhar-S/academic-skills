# Convergence Process and Filtering Criteria

This document explains how to systematically filter, merge, and refine multiple candidate ideas, and finally converge on one best research concept.

---

## I. Filtering Criteria

### 1.1 Novelty

Assess how different the idea is from existing work.

| Level | Description |
|------|------|
| 5 — Groundbreaking | Proposes a new problem or method with no close prior work |
| 4 — Highly novel | Significant differentiation, clearly distinct from related work |
| 3 — Moderately novel | New elements exist, but overall structure has precedent |
| 2 — Low novelty | Mostly incremental improvement or direct application |
| 1 — No novelty | Already done or highly similar work exists |

**Assessment basis**:
- Results from literature search stage
- Does it propose a new problem definition?
- Does it introduce a new method or perspective?
- Does it provide new theoretical insight?

### 1.2 Feasibility

Assess the likelihood of completion under current conditions.

| Level | Description |
|------|------|
| 5 — Highly feasible | Resources are sufficient; techniques are mature; can finish on schedule |
| 4 — Mostly feasible | Some challenges but manageable risk |
| 3 — Conditionally feasible | Requires specific resources or technical breakthroughs |
| 2 — Barely feasible | Major technical/resource barriers, low success chance |
| 1 — Infeasible | Cannot be completed with current conditions |

**Assessment basis**:
- Enough compute resources (GPU/memory/storage)?
- Available datasets?
- Reproducible baselines available?
- Time estimate fits deadline?
- Requires special domain expertise or collaborators?

### 1.3 Impact

Assess potential contribution to the field.

| Level | Description |
|------|------|
| 5 — Transformative | Could change field direction or paradigm |
| 4 — High impact | Substantial contribution to an important problem |
| 3 — Moderate impact | Meaningful progress on a specific sub-problem |
| 2 — Low impact | Incremental progress with limited scope |
| 1 — Very low impact | Problem is too small or too niche |

**Assessment basis**:
- How many researchers/users care about it?
- Can other work cite or use this result?
- Can it enable downstream applications?
- What venue tier is plausible?

### 1.4 Timeliness

Assess whether the idea falls in the right time window.

| Level | Description |
|------|------|
| 5 — Perfect timing | Enabling technology just matured; community attention is high; competition not saturated |
| 4 — Good timing | Direction is rising with growth space |
| 3 — Neutral | Timing is neither particularly favorable nor unfavorable |
| 2 — Slightly late | Direction is saturating or losing attention |
| 1 — Outdated | Direction is outdated or competition is very intense |

**Assessment basis**:
- Any recent breakthrough/resources in this direction?
- Trend of related top-venue papers?
- Are major teams still investing?
- Too many competitors on similar topics?

### 1.5 Personal Interest

Assess your motivation and enthusiasm.

| Level | Description |
|------|------|
| 5 — Very excited | Eager to start and willing to invest significant time |
| 4 — Interested | Interested and willing to explore deeply |
| 3 — Neutral | Neither excited nor resistant |
| 2 — Reluctant | Not very interested but sees value |
| 1 — Not interested | Would not do it even if valuable |

**Why it matters**:
- Research is a long-term commitment; passion sustains persistence
- Strong intuition often comes from deep interest
- Interest-driven work often yields deeper insight
- Authentic enthusiasm improves writing and presentation quality

---

## II. Convergence Process

### 2.1 Round 1: Eliminate

**Purpose**: Quickly remove clearly unsuitable candidates.

**Elimination conditions** (discard if any condition is met):

1. **Insufficient novelty**
   - Literature search finds nearly identical prior work
   - No meaningful differentiation point can be found

2. **Fundamentally infeasible**
   - Required data is unavailable and unobtainable
   - Compute demand far exceeds available resources
   - Required technology does not yet exist

3. **Problem invalidity**
   - Core assumptions are incorrect
   - Problem is already solved or not important

**How to run**:
- Sweep all candidates against elimination conditions
- Mark reason for each eliminated idea and move to "eliminated pool"
- Keep uncertain ones temporarily
- Expect to eliminate ~30–50%

### 2.2 Round 2: Merge

**Purpose**: Merge related or complementary ideas into stronger candidates.

**Merge criteria**:

1. **Common-origin merge**
   - Two ideas target the same problem with different solutions
   - Merge into one problem + best combined solution

2. **Complementary merge**
   - Two ideas solve different facets of the same issue
   - Merge into one integrated plan covering both facets

3. **Hierarchy merge**
   - One idea is a subset/special case of another
   - Keep the general form; use special case as first experiment

**How to run**:
- Compare surviving ideas pairwise
- Mark mergeable pairs
- Check whether merged outcome is truly better (sometimes 1+1 < 2)
- Give merged ideas new title and description

### 2.3 Round 3: Refine

**Purpose**: Turn vague ideas into concrete research plans.

**Refinement steps**:

1. **Concretize problem**
   - Narrow broad problem to paper-scale scope
   - Define inputs/outputs clearly
   - Define evaluation metrics clearly

2. **Concretize method**
   - Sketch the main technical approach
   - Identify key technical challenges
   - Draft at least two possible solution paths

3. **Concretize contributions**
   - List expected contributions clearly (2–3 items)
   - Separate primary vs. secondary contributions
   - Confirm contribution is enough for one paper

4. **Concretize experiments**
   - Select datasets
   - Select baseline methods
   - Select evaluation metrics
   - Draft initial experiment plan

**Refined format**:

```
## Idea: [Title]

### Problem
[One-sentence problem statement]

### Motivation
[Why this problem matters; why now]

### Method Overview
[2–3 sentences describing approach]

### Expected Contributions
1. [Contribution 1]
2. [Contribution 2]
3. [Contribution 3] (optional)

### Experiment Plan
- Datasets: [list]
- Baselines: [list]
- Metrics: [list]

### Risks
- [Main risks and mitigation]
```

### 2.4 Round 4: Score and Rank

**Purpose**: Rank refined candidates quantitatively.

See [evaluation-matrix.md](evaluation-matrix.md) for detailed matrix.

**How to run**:
1. Score each candidate on five dimensions (1–5)
2. Compute weighted total
3. Rank by total
4. Focus on top 2–3 for final comparison

### 2.5 Round 5: Final Decision

**Purpose**: Select one final idea from top candidates.

**Decision factors**:

1. **Quantitative result**: which has highest weighted total?
2. **Intuition**: which one do you most want to do?
3. **Risk profile**: which has most controllable risk?
4. **Strategic fit**:
   - Which best supports your career goals?
   - Which best matches your current team?
   - Which best fits your timeline constraints?

**If logic and intuition conflict**:
- Spend time identifying why
- Intuition may capture factors missed by quantitative scoring
- Discuss with trusted peers/mentors
- If unresolved, prefer the idea you are more motivated to execute

---

## III. Common Pitfalls

### 3.1 Confirmation Bias

**Symptoms**:
- Searching only literature that supports your preferred idea
- Ignoring/downplaying counter-evidence
- Scoring favored ideas leniently and disliked ideas harshly

**Prevention**:
- Deliberately search for counter-evidence
- Ask others to independently assess candidates
- For each idea, list "reasons this may fail"
- Use blind scoring when possible

### 3.2 Sunk Cost Fallacy

**Symptoms**:
- Refusing to drop an idea due to prior time investment
- Continuing despite known severe flaws because early results exist
- Thinking "I have done too much to stop now"

**Prevention**:
- Remind yourself past time is unrecoverable
- Ask: if starting from zero today, would I still choose this?
- Set explicit checkpoints for possible pivot decisions
- Treat prior work as learning cost, not waste

### 3.3 Novelty Bias

**Symptoms**:
- Over-prioritizing novelty while ignoring feasibility
- Choosing the coolest idea rather than the best idea
- Ignoring simple effective solutions for unproven complexity

**Prevention**:
- Give feasibility and impact sufficient weight
- Ask whether novelty creates substantive benefit
- Use a minimal viable research test for the novel core

### 3.4 Bandwagon Effect

**Symptoms**:
- Choosing direction only because it is hot
- Assuming popularity implies value
- Avoiding less popular directions out of fear

**Prevention**:
- Distinguish valuable from popular
- Hot areas require stronger differentiation
- Less crowded areas may offer high-impact opportunities
- Ask: if nobody worked on this, would it still be valuable?

### 3.5 Perfectionism

**Symptoms**:
- Waiting for a perfect idea before starting
- Constantly delaying because idea is "not good enough yet"
- Seeing flaws in all ideas and failing to decide

**Prevention**:
- Accept that no idea starts perfect
- Set hard deadlines for decision-making
- Start once idea is good enough; it will evolve during execution
- A finished good study beats an unfinished perfect concept

### 3.6 Anchoring Effect

**Symptoms**:
- First idea dominates evaluation
- Later ideas are judged relative to first one instead of independently
- Difficulty escaping initial framing

**Prevention**:
- Intentionally evaluate first idea last
- Use multiple ideation frameworks to diversify candidate types
- Ask different people to produce independent rankings
- Shuffle evaluation order to reduce sequence effects

---

## IV. Convergence Checklist

### Elimination Stage
- [ ] Run elimination criteria on all candidates
- [ ] Record reason for each eliminated idea
- [ ] Keep uncertain ideas temporarily

### Merge Stage
- [ ] Compare all surviving ideas pairwise
- [ ] Mark mergeable pairs
- [ ] Evaluate merged outcomes
- [ ] Update descriptions for merged ideas

### Refinement Stage
- [ ] Each candidate has a concrete problem definition
- [ ] Each candidate has an initial method concept
- [ ] Each candidate lists expected contributions
- [ ] Each candidate has an initial experiment plan

### Scoring Stage
- [ ] All candidates scored on five dimensions
- [ ] Weighted totals computed
- [ ] Candidates ranked by total score

### Decision Stage
- [ ] Compare top 2–3 candidates
- [ ] Consider intuition
- [ ] Consider strategic factors
- [ ] Check cognitive biases
- [ ] Make final choice
- [ ] Write 1-page proposal
