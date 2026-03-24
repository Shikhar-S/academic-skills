# Baseline Selection Guide

## Overview

Baseline selection directly affects the credibility and persuasiveness of experimental results. This document provides a systematic strategy to ensure fair and comprehensive comparisons.

---

## 1. Why Baseline Selection Matters

- **Credibility**: Only comparisons with strong baselines can demonstrate true value.
- **Positioning**: Baselines help readers place your method in the research landscape.
- **Fairness**: Poor baseline selection is one of the most common reviewer criticisms.
- **Completeness**: Diverse baselines reveal strengths and weaknesses across dimensions.

---

## 2. Required Baseline Types

### 2.1 Classic Methods

**Definition**: Historically influential methods in the field.

**Selection criteria**:

- Widely cited and broadly recognized
- Usually have mature, stable implementations
- Represent traditional solutions in the field

**Examples**:

| Field | Example Classic Methods |
|------|-------------|
| Text classification | TF-IDF + SVM, TextCNN |
| Sequence labeling | BiLSTM-CRF |
| Machine translation | Transformer (Vaswani et al., 2017) |
| Image classification | ResNet |
| Object detection | Faster R-CNN |

**Purpose**: Show progress relative to classic methods and provide historical context.

### 2.2 Current SOTA (State of the Art)

**Definition**: Methods with the best current performance on your target task and datasets.

**Selection criteria**:

- Publicly reported results on the same datasets
- Publication dates close to your submission timeline
- Preferably open-source implementations

**Notes**:

- SOTA changes over time; verify the latest progress before submission.
- If SOTA uses extra data or larger pretrained models, explain this clearly.
- Prefer including 2-3 recent SOTA methods.

**Purpose**: Show whether your method truly advances the field frontier.

### 2.3 Simple Baselines

**Definition**: Simple methods without complex modeling, used to establish lower-bound references.

**Common types**:

| Type | Description | Example |
|------|------|------|
| Random baseline | Random predictions | Random classifier |
| Majority class | Always predict most common class | Majority Class |
| Simple statistics | Based on simple statistical features | TF-IDF + Logistic Regression |
| Direct transfer | Pretrained model without adaptation | Zero-shot GPT |
| Human performance | Annotation agreement by humans | Human Agreement |

**Purpose**:

- Confirm task complexity (avoid cases where simple methods already solve it)
- Provide a baseline reference for later improvements
- Sometimes strong simple baselines are themselves important findings

---

## 3. Fair Comparison Principles

### 3.1 Data Consistency

All methods must use:

- **Same training set**: same splits and dataset versions
- **Same validation set**: for hyperparameter tuning
- **Same test set**: for final evaluation
- **Same preprocessing**: unless preprocessing itself is a research contribution

### 3.2 Evaluation Consistency

- Use the same metrics and computation definitions.
- Use the same evaluation scripts (to avoid implementation differences).
- Measure efficiency metrics in equivalent hardware environments.

### 3.3 Resource Consistency

- Parameter counts should be in the same order of magnitude (or differences clearly reported).
- Training compute should be comparable.
- If pretrained models are used, versions should match.

### 3.4 Tuning Consistency

- Perform reasonable hyperparameter tuning for baseline methods.
- Do not tune only your method while using defaults for baselines.
- Record tuning ranges and best hyperparameters for all methods.

### 3.5 Source of Baseline Results

Recommended priority:

1. **Re-run original open-source code**: most reliable.
2. **Cite numbers from original papers**: ensure equivalent conditions.
3. **Use leaderboard numbers**: verify evaluation protocol consistency.
4. **Self-reimplementation**: validate that reproduced results are close to original reports.

---

## 4. Baseline Selection Strategy

### 4.1 Literature Survey Strategy

1. Read representative papers from the last 2-3 years on the target task.
2. Compile the baseline lists used in those papers.
3. Identify high-frequency baselines used by many papers.
4. Add the latest published methods.

### 4.2 Recommended Number of Baselines

| Paper Type | Recommended Count |
|----------|----------|
| Top-conference full paper | 5-10 |
| Top-conference short paper | 3-5 |
| Workshop paper | 2-4 |

### 4.3 Grouped Baseline Presentation

In result tables, present baselines by category:

```
Table 1: Results on XX dataset

Method                    | F1    | Acc
--------------------------|-------|------
--- Simple Baselines ---
Majority Class            | 32.1  | 45.2
TF-IDF + LR               | 65.3  | 68.7
--- Classic Methods ---
TextCNN (Kim, 2014)       | 78.2  | 80.1
BiLSTM (Hochreiter, 1997) | 79.5  | 81.3
--- Recent SOTA ---
BERT (Devlin, 2019)       | 88.3  | 89.7
RoBERTa (Liu, 2019)       | 89.1  | 90.2
--- Our Method ---
Ours                      | 90.5  | 91.8
```

---

## 5. Common Mistakes and How to Avoid Them

### 5.1 Cherry-Picking

**Mistake**: Compare only against weaker methods and avoid strong baselines.

**How to avoid**:

- Include recognized SOTA methods.
- Refer to baseline sets used in recent papers.
- If your method is not better on some baselines, report honestly and analyze why.

### 5.2 Unfair Comparison Conditions

**Mistake**: Your method uses larger models, more data, or stronger pretraining without disclosure.

**How to avoid**:

- Clearly report parameter counts for all methods.
- Specify pretrained models used by each method.
- Add comparisons under matched parameter budgets.

### 5.3 Outdated Baselines

**Mistake**: All baselines are older than three years.

**How to avoid**:

- Include at least 1-2 methods from the last year.
- Check for new SOTA methods before submission.
- Track recent arXiv preprints.

### 5.4 Insufficient Baseline Tuning

**Mistake**: Baselines use default hyperparameters while your method is heavily tuned.

**How to avoid**:

- Perform reasonable hyperparameter search for each baseline.
- Use baseline papers' recommended tuning ranges.
- Report best baseline hyperparameters.

### 5.5 Ignoring Simple Baselines

**Mistake**: Compare only against complex methods and ignore the possibility that simple methods are already strong.

**How to avoid**:

- Always include at least one simple baseline.
- If simple baselines perform strongly, report and discuss it honestly.

### 5.6 Inconsistent Evaluation Metrics

**Mistake**: Different methods use different evaluation scripts or settings.

**How to avoid**:

- Use one shared evaluation codebase for all methods.
- Ensure tokenization, post-processing, and related steps are consistent.
- Use official evaluation scripts when available.

---

## 6. Baseline Selection Checklist

- [ ] Includes at least one simple baseline
- [ ] Includes classic methods in the field
- [ ] Includes recent SOTA methods from the last 1-2 years
- [ ] All baselines use the same data splits
- [ ] All baselines use the same metrics and evaluation scripts
- [ ] All baselines receive reasonable hyperparameter tuning
- [ ] Baseline result sources are recorded (original code / reimplementation / cited numbers)
- [ ] Differences in parameter count and compute budget are clearly reported
- [ ] Number of baselines is sufficient for the target venue's norms
