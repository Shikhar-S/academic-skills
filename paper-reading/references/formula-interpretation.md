# Formula and Figure Interpretation Guide

This guide provides explanation strategies and templates used in "Step 4: Formula and Figure Interpretation."

---

## Three-Step Template for Formula Explanation

Explain each formula using the following three steps:

### Step 1: Intuition First

Use one plain-language sentence to tell readers what the formula is doing. Avoid symbols; explain as if talking with someone new to math.

**Template**:
> This formula is doing: "___".

**Examples**:
- Loss function: "This formula measures how far the model's prediction is from the correct answer; larger error gives a higher score, so the model must improve."
- Attention: "This formula decides which other words each word should pay more attention to, like your eyes naturally focusing on key words while reading."
- Softmax: "This formula converts a bunch of numbers into probabilities that sum to 1, so they can be used as confidence scores."

### Step 2: Break Down Symbols

List and explain every symbol in the formula using a table or list for side-by-side reading.

**Template**:

| Symbol | Pronunciation | Meaning | Granny's Analogy |
|------|------|------|-----------|
| x | x | input data | ingredients |
| θ | theta | model parameters | seasoning ratios in a recipe |
| L | L | loss value | customer dissatisfaction score |

**Notes**:
- Do not skip any symbol, including subscripts and superscripts
- If a symbol was defined earlier, briefly point to where
- For Greek letters, include pronunciation

### Step 3: Explain Significance

Answer three questions:
1. Why is this formula important?
2. What happens if this formula is removed (or replaced)?
3. What assumptions or limitations does this formula have?

---

## Explanation Strategies by Common Formula Type

### Loss Function

**Core intuition**: A score of "how wrong the model is"; objective is to minimize it.

**What to explain**:
- Why this loss instead of alternatives?
- What behavior does this loss encourage?
- Is there a regularization term, and what does it do?

**Common analogies**:
- "Loss is like exam point deductions—the more mistakes, the more points you lose"
- "Cross-entropy compares your answer distribution with the correct distribution"
- "L2 regularization is like limiting seasoning so the dish doesn't become too heavy"

**Quick reference of common losses**:

| Loss Name | Intuition | Use Case |
|-----------|------|------|
| MSE (Mean Squared Error) | Average squared distance between prediction and truth | Regression |
| Cross-Entropy | Difference between two probability distributions | Classification |
| Binary Cross-Entropy | Binary-version cross-entropy | Binary/multi-label |
| Contrastive Loss | Pull similar items together, push dissimilar apart | Contrastive learning |
| Triplet Loss | Pull anchor to positive, push away from negative | Metric learning |
| KL Divergence | Asymmetric distribution difference | VAE / distillation |
| Hinge Loss | Margin size at decision boundary | SVM / ranking |

---

### Attention Mechanism

**Core intuition**: The model decides where to look.

**What to explain**:
- What do Query, Key, and Value represent?
- How is the attention score computed?
- What different heads in multi-head attention focus on?

**Common analogies**:
- "Attention is like shopping in a market: your eyes naturally focus on fresh vegetables and ignore rotten ones"
- "Query is your question, Key is each candidate label, Value is actual content—match question to labels, then retrieve best content"
- "Multi-head is like sending 8 detectives to investigate from different angles and then combining reports"

**Standard formula breakdown**:

```
Attention(Q, K, V) = softmax(QK^T / √d_k) V
```

| Symbol | Meaning | Analogy |
|------|------|------|
| Q | Query matrix | the question you ask |
| K | Key matrix | name tags of candidates |
| V | Value matrix | information carried by each candidate |
| d_k | key dimension | number of words on each name tag (for normalization) |
| QK^T | query-key similarity | question-tag match score |
| softmax | convert to probabilities | convert match scores to attention allocation |
| √d_k | scaling factor | prevent scores from becoming too extreme |

---

### Optimization

**Core intuition**: How to update the model step by step so it gets better.

**What to explain**:
- Which optimizer is used? (SGD, Adam, AdamW...)
- How is learning rate set? Any schedule?
- Any special training tricks? (warmup, gradient clipping...)

**Common analogies**:
- "Gradient descent is like descending a mountain by following the steepest downward direction"
- "Learning rate is your step size—too large overshoots the valley; too small takes forever"
- "Adam is a smart hiker that remembers previous path patterns and adapts stride"
- "Warmup is pre-exercise: start slow, then speed up"

---

### Probability & Statistics

**Core intuition**: Mathematical language for uncertainty.

**What to explain**:
- Intuition of conditional probability P(A|B)
- Role of Bayes' theorem in this paper
- Meaning of expectation and variance

**Common analogies**:
- "P(rain | dark clouds) means: given dark clouds, how likely is rain?"
- "Expectation is like your average score across many exams"
- "Variance is score stability—alternating between 100 and 30 means high variance"

---

## Figure Interpretation Method

### General Three Steps

#### 1. Read Trend
- Is overall trajectory increasing, decreasing, or flat?
- Any clear turning points?
- Core question: "What overall direction does this figure show?"

#### 2. Find Anomalies
- Any unusually high/low points?
- Any region with large divergence from other lines?
- Core question: "Does anything look unusual?"

#### 3. Link Context
- Is figure evidence consistent with textual claims?
- Does the figure reveal phenomena not discussed in text?
- Core question: "Did authors report results transparently?"

---

### Interpretation by Common Figure Type

#### Training Curves
- **X-axis**: usually epoch or step
- **Y-axis**: usually loss or accuracy
- **Check**:
  - Convergence behavior and speed
  - Overfitting signs (training loss down, validation loss up)
  - Relative convergence speed across methods

#### Bar Charts
- Often compare methods on metrics
- **Check**:
  - Does Y-axis start at 0? (truncated axes can exaggerate gaps)
  - Are error bars present? (absence lowers confidence)
  - Are differences statistically significant?

#### Tables
- Main carrier of experimental results
- **Check**:
  - Bold often marks best results
  - Underline often marks second-best
  - Captions often contain critical details

#### Attention Visualizations
- Show where model "looks"
- **Check**:
  - Is attention distribution reasonable?
  - Do different heads show different focus patterns?
  - Useful conclusion: model is focusing on meaningful regions, not guessing randomly

#### t-SNE / UMAP Plots
- 2D projection of high-dimensional features
- **Check**:
  - Are same-class points clustered?
  - Are class boundaries separated?
  - Useful conclusion: better clustering suggests better learned features

---

## Granny's Formula Teaching Principles

1. **Conclusion before derivation** — First tell readers what the formula computes, then unpack it
2. **Ground with analogy** — Provide at least one everyday analogy per core formula
3. **Complete symbol table** — No symbol should be omitted
4. **Do not fear repetition** — Brief recap is okay when concepts reappear
5. **Admit uncertainty** — If a design choice is unclear, say so honestly
6. **Connect context** — Explain how this formula relates to previous/next formulas
