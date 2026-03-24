# Experiment Planning Methods

## Overview

This document provides detailed planning methods from research hypotheses to experimental workflows, including complete guidance on hypothesis writing, variable definition, and variable control.

---

## 1. How to Write Strong Research Hypotheses

### 1.1 The Role of Research Hypotheses

Research hypotheses are the anchor of the entire experiment design. A strong hypothesis can:

- Clearly define experiment goals and direction
- Determine what experiments are needed for validation
- Guide evaluation metric selection
- Bound the scope of paper contributions

### 1.2 Hierarchical Structure of Hypotheses

```
Main Hypothesis
├── Sub-hypothesis H1: Performance hypothesis
│   ├── H1a: Performance on dataset A
│   └── H1b: Performance on dataset B
├── Sub-hypothesis H2: Efficiency hypothesis
└── Sub-hypothesis H3: Generalization hypothesis
```

A complex research hypothesis should be decomposed into 2-5 sub-hypotheses, each mapped to one group of experiments.

### 1.3 Steps for Writing Hypotheses

**Step 1: Clarify the research problem**

- What problem exists in current methods?
- What solution do you propose?
- Why might your solution work?

**Step 2: Draft an initial hypothesis**

Use this template:

> We hypothesize that [proposed method/mechanism], because [theoretical rationale/intuition], will [increase/decrease] [expected magnitude] in [evaluation metric] on [task/dataset], compared with [baseline/comparator].

**Step 3: Check hypothesis quality**

- Falsifiability check: What result would refute this hypothesis?
- Specificity check: Does it include quantifiable expectations?
- Scope check: Is the applicability scope clearly defined?

**Step 4: Refine the hypothesis**

Revise based on the checks to improve precision.

### 1.4 Common Hypothesis Types

| Hypothesis Type | Example |
|----------|------|
| Performance hypothesis | "Method X achieves higher F1 than SOTA method Y on task T" |
| Efficiency hypothesis | "Method X is 2x faster in inference than method Y at comparable performance" |
| Component hypothesis | "Module A is the key factor behind method X's gain" |
| Generalization hypothesis | "Method X retains performance advantage on unseen domain D" |
| Scaling hypothesis | "The gain of method X increases as data scale grows" |

### 1.5 Common Mistakes in Hypothesis Writing

1. **Too vague**: "Our method is better" — lacks concrete metrics and comparators
2. **Not falsifiable**: "Our method may help in some cases" — cannot be disproven
3. **Overly ambitious**: "Our method is best on all tasks" — scope is too broad
4. **No theoretical support**: no reason provided for why the hypothesis should hold
5. **Disconnected from experiments**: hypothesis cannot be validated by planned experiments

---

## 2. From Hypotheses to Experimental Workflow

### 2.1 Hypothesis-Experiment Mapping Matrix

Build a mapping table between hypotheses and experiments:

| Hypothesis | Corresponding Experiment | Evaluation Metric | Expected Outcome |
|------|----------|----------|----------|
| H1: Performance hypothesis | Main results table | F1, Acc | +2 points or more |
| H2: Component hypothesis | Ablation study | F1 difference | Performance drops when removed |
| H3: Generalization hypothesis | Cross-dataset experiment | F1 | Advantage is maintained |

### 2.2 Experimental Workflow Design

**Phase 1: Pilot Experiments**

- Purpose: Validate code correctness and basic feasibility
- Scale: Small dataset or subset
- Time budget: 10-15% of total experiment time

**Phase 2: Main Experiments**

- Purpose: Validate core hypotheses
- Includes: Comparison against all baselines
- Requirements: Multiple random seeds, full dataset

**Phase 3: Analysis Experiments**

- Ablation study
- Hyperparameter sensitivity analysis
- Qualitative analysis and visualization

**Phase 4: Supplementary Experiments**

- Cross-dataset transfer
- Efficiency analysis
- Additional experiments likely requested by reviewers

### 2.3 Experiment Priority Order

Recommended execution order:

1. Pilot experiments (confirm feasibility)
2. Core baseline comparisons (validate main hypothesis)
3. Full ablation experiments (validate component hypotheses)
4. Hyperparameter sensitivity analysis
5. Cross-dataset transfer experiments
6. Qualitative analysis and visualization
7. Efficiency analysis

---

## 3. Principles of Variable Control

### 3.1 Single-Variable Principle

**Core idea**: In each experiment, change only one independent variable while keeping all other conditions fixed.

This is the most fundamental principle in experiment design. Violating it makes it impossible to identify the true cause of performance changes.

**Correct example**:

```
Experiment A (baseline): model = Transformer, learning rate = 1e-4, batch size = 32
Experiment B (model changed): model = Our Method, learning rate = 1e-4, batch size = 32
```

**Incorrect example**:

```
Experiment A: model = Transformer, learning rate = 1e-4, batch size = 32
Experiment B: model = Our Method, learning rate = 3e-4, batch size = 64
-> Cannot determine whether differences come from the model or hyperparameters
```

### 3.2 Complete-Record Principle

All variables (including seemingly minor ones) must be recorded, including:

- Environment variables (hardware, software versions)
- Randomness-related factors (seed values, data shuffle order)
- Implicit variables (data loader order, GPU non-determinism)

### 3.3 Reasonable-Range Principle

The value ranges of independent variables should:

- Be based on prior work or theoretical analysis
- Cover ranges likely in real applications
- Include enough values to observe trends

### 3.4 Control Variable Checklist

Common control variables in machine learning experiments:

**Data-related**

- Train/validation/test split protocol
- Data preprocessing pipeline
- Data augmentation strategy
- Vocabulary size and construction method

**Model-related**

- Pretrained model version and weights
- Hidden dimension
- Number of layers
- Number of attention heads

**Training-related**

- Optimizer type and parameters
- Learning rate schedule
- Batch size
- Number of epochs or steps
- Early stopping strategy
- Gradient clipping

**Evaluation-related**

- Evaluation frequency
- Model selection criterion (e.g., best validation performance)
- Decoding strategy (e.g., beam size for beam search)

### 3.5 When Full Control Is Not Feasible

In some cases, controlling all variables is impractical:

- **Countermeasure 1**: Explicitly document uncontrollable variables and discuss them in the paper
- **Countermeasure 2**: Average over repeated runs to reduce randomness impact
- **Countermeasure 3**: Run sensitivity analysis to estimate impact of uncontrollable variables

---

## 4. Experiment Design Checkpoints

### Design Stage

- [ ] All hypotheses are clearly written
- [ ] Hypothesis-experiment mapping matrix is created
- [ ] Independent, dependent, and control variables are defined
- [ ] Workflow and priority order are finalized

### Before Execution

- [ ] Code is validated by small-scale pilot experiments
- [ ] Random seed list is finalized
- [ ] Compute resources are confirmed sufficient
- [ ] Result logging format is prepared

### During Execution

- [ ] Full settings for each run are recorded
- [ ] Intermediate results are backed up regularly
- [ ] Anomalous results are flagged and investigated

### After Execution

- [ ] Every hypothesis has corresponding experiment results
- [ ] Statistical tests are completed
- [ ] Interpretation is consistent with hypotheses or has sound explanations
