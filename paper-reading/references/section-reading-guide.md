# Section Reading Guide

This guide provides section-by-section reading methods and key-point extraction strategies for use in "Step 2: Section-by-Section Guided Tour."

---

## Abstract

### Reading Goal
Capture the full picture of the paper in minimal time.

### Four-Element Extraction Method

Extract these four elements from every abstract:

| Element | What to find | Common keywords |
|------|---------|-----------|
| **Problem** | What problem is being solved? | challenge, problem, limitation, issue, gap |
| **Method** | How is it solved? | propose, introduce, present, framework, approach |
| **Result** | How well does it work? | achieve, outperform, state-of-the-art, improvement |
| **Significance** | Why does it matter? | enable, contribute, potential, impact, advance |

### Granny's Reading Approach
- Quick first pass for overall sense
- Second pass to mentally mark the four elements
- Restate in your own words to verify understanding

### Common Pitfalls
- Some abstracts omit or blur significance; infer it yourself
- Some abstracts over-claim; keep healthy skepticism
- Some abstracts are too long and noisy; cleanly reorganize for readers

---

## Introduction

### Reading Goal
Understand motivation, current-method limitations, and the paper's positioning.

### Three-Part Analysis

Most introductions can be split into three parts:

1. **Big-picture background** (first 1–2 paragraphs)
   - What does this field do and why is it important?
   - Analogy lens: "the village's current state"

2. **Research gap** (middle paragraphs)
   - What is missing or weak in existing methods?
   - Signals: however, but, despite, limitation, challenge, remains
   - Analogy lens: "the village's crisis"

3. **Paper contributions** (last 1–2 paragraphs)
   - What did the authors do, and what is distinctive?
   - Common format: numbered list (i), (ii), (iii) or bullets
   - Analogy lens: "hero enters with a new weapon"

### Key Extraction Checklist
- [ ] What research area is this?
- [ ] What are at least two major limitations of existing methods?
- [ ] How many claimed contributions, and what are they?
- [ ] Which prior works are explicitly compared?

### Special Reminders
- Papers cited in the introduction are often core related work
- If introduction is very long (>2 pages), focus on middle and ending parts
- An overview figure in the introduction is often more informative than dense text

---

## Method / Approach

### Reading Goal
Understand architecture and operation of the proposed method.

### Modular Decomposition Method

No matter how complex the method is, use module decomposition.

#### Step 1: Find overall architecture figure
- Most papers include a system diagram (often Figure 1 or 2)
- Start there to build global understanding
- Analogy lens: "read the full recipe before cooking"

#### Step 2: Identify modules
- Break method into 3–5 modules
- Each module: **input → processing → output**
- Use a table:

| Module | Input | What it does | Output |
|---------|------|--------|------|
| Module A | raw data | feature extraction | feature vectors |
| Module B | feature vectors | attention computation | weighted features |
| Module C | weighted features | classification | predictions |

#### Step 3: Find core innovation
- Which modules are new vs. borrowed?
- Focus explanation on new modules
- Briefly summarize borrowed modules with citation pointers

#### Step 4: Understand training process
- What is the loss function?
- How many training stages? (pre-train + fine-tune? end-to-end?)
- Any special strategy? (warmup, curriculum learning, data augmentation)

### Common Pitfalls
- Method sections are often dense; skip low-value detail
- Symbol definitions may be scattered; consolidate into one symbol table
- If subsection headers exist, follow them for efficient reading

---

## Experiments

### Reading Goal
Verify whether the method truly works and by how much.

### Four-Dimension Check

#### 1. Experimental setup
Confirm:
- **Datasets** — which datasets, size, and domain?
- **Metrics** — accuracy, F1, BLEU, perplexity, etc.
- **Baselines** — who are the comparators? Are they strong and recent?
- **Implementation details** — hardware, hyperparameters, training time

Pay special attention to:
- missing important recent baselines
- unreasonable metric choices
- setup insufficiency vs. claimed conclusions

#### 2. Main results
- Find the main result table (usually Table 1 or 2)
- Identify where the proposed method wins and margin size
- Distinguish tiny gains (0.1%) from meaningful gains (e.g., 5%)

#### 3. Ablation study
- Often the most revealing part
- Shows contribution of each module
- Ask:
  - How much drop if core module is removed?
  - Any component removal that improves performance (warning sign)?
  - How sensitive are hyperparameters?

#### 4. Analysis & visualization
- Are there case studies?
- Attention maps or feature visualizations?
- Error analysis? (failure cases are especially informative)

### Table-Reading Tactics
- Start with final row (often proposed method)
- Compare with second-to-last row (often strongest baseline)
- Inspect margin
- Then scan full ranking
- Watch bold/underline/asterisk markers

---

## Conclusion

### Reading Goal
Validate authors' self-assessment and identify future directions.

### Three Key Extractions

#### 1. Summary recap
- How do authors summarize their work?
- Is it consistent with abstract, or does it introduce new claims?
- Compare abstract vs. conclusion for inconsistencies

#### 2. Limitations
- What limitations do authors admit?
- Also inspect what they did **not** mention
- Common hidden limits:
  - Works only on specific datasets
  - High compute cost
  - Heavy labeled-data dependence
  - Tested only in English
  - Scalability not verified

#### 3. Future work
- What next steps do authors propose?
- Are these directions practically plausible?
- Distinguish meaningful future work from routine boilerplate

### Conclusion Reading Tips
- Conclusion is often one of the easiest sections to read
- If short on time, abstract + conclusion can deliver ~80% of core content
- Limitations in conclusion are often the paper's most honest part

---

## Related Work

### Not in the five-core path, but still important

- Quickly scan and identify 2–3 most relevant prior works
- Understand differences between this paper and those works
- If reader wants depth, recommend 1–2 must-read predecessors

---

## Handling Special Paper Structures

### Survey / Review papers
- Do not force five-section flow; organize by topic categories
- Build a "technology evolution roadmap" for readers

### Workshop / short papers
- Content is compact; merge Step 2 and Step 3 when needed
- Focus on core idea rather than demanding exhaustive experiments

### System papers
- Method section may be architecture-focused
- Explain system design with "building a house" analogy

### Theoretical papers
- May have no experiments and focus on theorem proofs
- Spend more time in formula interpretation (Step 4)
