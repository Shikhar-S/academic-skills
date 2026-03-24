---
name: experiment-design
description: "Academic research experiment design skill—a complete workflow from research hypothesis to reproducible experiment plan. Use this skill whenever the user needs to plan experiments, design ablation studies, choose baselines, define evaluation metrics, or asks what experiments should be run. Trigger terms include: experiment design, ablation, baseline, evaluation metric, and how to validate a method. Applicable to machine learning, NLP, CV, and related fields."
license: MIT
compatibility: Works with Claude Code, ChatGPT/Codex CLI, and Gemini CLI.
metadata:
  author: Research Reading Agent
  version: "1.0.0"
---

# Experiment Design Skill

## Overview

This skill provides a structured experiment design workflow for academic research in machine learning, natural language processing, computer vision, and related areas. The goal is to help researchers move from a vague research idea to a rigorous, reproducible, and persuasive experiment plan.

## Core Design Principles

A good experiment design should have the following properties:

- **Falsifiability**: Results must be able to support or reject the research hypothesis.
- **Fairness**: All methods should be evaluated under the same conditions.
- **Reproducibility**: Others should be able to fully reproduce the experiments from the description.
- **Sufficiency**: Experiments should cover enough dimensions to support the paper's conclusions.

---

## Experiment Design Pipeline

A complete experiment design follows this six-step process:

```
Hypothesis -> Variables -> Metrics -> Baseline -> Ablation -> Compute Budget
```

The output of each step is the input to the next step, forming a rigorous reasoning chain.

---

## Step 1: Clarify Research Hypotheses

### Purpose

Transform a vague research motivation into concrete, testable hypotheses.

### Method

1. **Identify the research question**: What question are you trying to answer?
2. **Propose the core hypothesis**: What is your expected answer?
3. **Make it explicit**: The hypothesis must be measurable and falsifiable.
4. **Decompose into sub-hypotheses**: Break a complex hypothesis into sub-hypotheses that can be tested one by one.

### Hypothesis Quality Criteria

| Criterion | Description |
|------|------|
| Specificity | Clearly states the expected effect direction and magnitude |
| Measurability | Can be validated with quantitative metrics |
| Falsifiability | There exists a possible experimental outcome that can refute it |
| Relevance | Directly tied to the research question |

### Example

- Weak: "Our method is better"
- Good: "On the SQuAD 2.0 dataset, adding cross-attention improves F1 by at least 2 points over a self-attention-only baseline"

See details: [Experiment Planning Reference](references/experiment-planning.md)

---

## Step 2: Define Variables

### Independent Variables

Variables actively controlled by the researcher—the things changed in experiments.

- Model architecture variants
- Differences in training strategy
- Differences in data processing

### Dependent Variables

Variables used to measure outcomes—the things being measured.

- Model performance metrics (accuracy, F1, BLEU, etc.)
- Efficiency metrics (inference time, memory usage)
- Quality metrics (human evaluation scores)

### Control Variables

Variables held constant to ensure fair comparison.

- Random seeds
- Training dataset and split protocol
- Hyperparameters (parts not under study)
- Hardware environment
- Pretrained model version

### Variable Control Principles

1. **Single-variable principle**: Change only one independent variable per experiment.
2. **Complete-record principle**: Record all variable values.
3. **Reasonable-range principle**: Independent variable ranges should be theoretically justified.

See details: [Experiment Planning Reference](references/experiment-planning.md)

---

## Step 3: Choose Evaluation Metrics

### Selection Principles

1. **Field convention**: Prioritize metrics recognized as standards in the field.
2. **Multi-dimensional coverage**: Report performance, efficiency, and robustness together.
3. **Statistical significance**: Report mean and standard deviation across multiple runs.
4. **Validity**: Metrics should truly reflect the aspects targeted by the hypothesis.

### Common Metric Categories

| Category | Example Metrics |
|------|----------|
| Classification tasks | Accuracy, Precision, Recall, F1-score, AUC-ROC |
| Generation tasks | BLEU, ROUGE, METEOR, BERTScore, human evaluation |
| Information retrieval | MAP, MRR, NDCG, Recall@K |
| Efficiency metrics | FLOPs, parameter count, inference latency, memory footprint |
| Robustness | Cross-dataset performance, adversarial accuracy |

### Statistical Testing

- Report mean and standard deviation across multiple random seeds.
- Apply statistical significance testing when needed (e.g., paired t-test, bootstrap test).
- Annotate significance level (p < 0.05, p < 0.01).

---

## Step 4: Select and Configure Baselines

### Required Baseline Types

1. **Classic methods**: Historically important approaches in the field.
2. **Current SOTA**: Most recent best-performing methods.
3. **Simple baselines**: Simple but reasonable references (e.g., random, majority class, TF-IDF).

### Fair Comparison Principles

- Use the same data splits.
- Use the same evaluation protocol.
- Prefer original authors' code and hyperparameters whenever possible.
- If reimplementation is necessary, verify reproducibility against the original paper.

### Common Mistakes

- Comparing only with weak baselines
- Not including the latest SOTA baselines
- Not tuning baseline hyperparameters
- Inconsistent comparison settings (e.g., different pretrained models)

See details: [Baseline Selection Guide](references/baseline-selection.md)

---

## Step 5: Design Ablation Studies

Ablation studies are key experiments for validating contributions of individual components. This skill defines four ablation modes:

### Mode 1: Component Ablation

Remove or replace components one by one and observe performance changes.

- Remove one component at a time.
- Record the performance change after removal.
- Estimate the contribution of each component.

### Mode 2: Hyperparameter Sensitivity Analysis

Investigate how key hyperparameters affect performance.

- Select 2-4 most important hyperparameters.
- Vary values within reasonable ranges.
- Plot hyperparameter-performance curves.

### Mode 3: Cross-Dataset Transfer

Validate generalization capability.

- Test on multiple datasets.
- Include datasets of different scales and domains.
- Analyze conditions where the method works best or worst.

### Mode 4: Qualitative Analysis

Use visualization and case analysis to understand model behavior deeply.

- Attention-weight visualization
- Success/failure case analysis
- Feature-space visualization (e.g., t-SNE)
- Error-type categorization and statistics

See details: [Ablation Design Guide](references/ablation-design.md)

---

## Step 6: Estimate Compute Resources

### What to Estimate

1. **Cost per run**
   - GPU hours
   - Memory requirement
   - Storage requirement

2. **Total experiment volume**

   ```
   Total GPU hours = per-run hours × number of model variants × number of datasets × number of random seeds × number of hyperparameter combinations
   ```

3. **Safety factor**
   - Reserve 1.5-2x of estimated resources.
   - Account for debugging, pilot runs, and follow-up experiments.

### Resource Optimization Strategies

- Start with pilot experiments on smaller datasets.
- Use early stopping to reduce training time.
- Use mixed-precision training.
- Prioritize experiments strategically.

---

## Reproducibility Requirements

The experiment plan must include complete reproducibility information so others can reproduce results precisely.

### Required Disclosure Items

1. **Hardware environment**
   - GPU model and count
   - CPU specification
   - Memory size

2. **Software environment**
   - Programming language version
   - Deep learning framework version
   - Key package versions

3. **Randomness control**
   - Random seed configuration
   - Deterministic algorithm settings
   - Seed list for repeated runs

4. **Training protocol**
   - Full hyperparameter list
   - Optimizer settings
   - Learning rate schedule
   - Data augmentation strategy
   - Early stopping criteria

5. **Data processing**
   - Dataset version and source
   - Preprocessing steps
   - Data splitting strategy

6. **Evaluation protocol**
   - Exact metric definitions
   - Evaluation frequency
   - Model selection criteria

See details: [Reproducibility Checklist](references/reproducibility-checklist.md)

---

## Output: Structured Experiment Plan Document

The final output of this skill is a structured experiment plan containing these sections:

1. Research hypothesis and sub-hypotheses
2. Variable definition table
3. Evaluation metrics and statistical methods
4. Baseline list and settings
5. Ablation study design matrix
6. Compute-resource estimation and schedule
7. Reproducibility information

Use template: [Experiment Plan Template](templates/experiment-plan.md)

---

## Workflow

### Input

- Research topic or paper draft
- Description of the proposed method
- Available compute resources

### Process

1. Guide the user to clarify research hypotheses.
2. Help define independent, dependent, and control variables.
3. Recommend evaluation metrics based on task type.
4. Recommend baselines based on research domain.
5. Design ablation study protocols.
6. Estimate compute-resource requirements.

### Output

- Complete experiment plan document (following the template)
- Recommended experiment priority order
- Potential risks and mitigation plans

---

## Quality Checklist

After finishing the experiment plan, verify the following:

- [ ] Every research hypothesis has a corresponding validation experiment.
- [ ] Value ranges for all independent variables are clearly defined.
- [ ] All control variables are listed completely.
- [ ] Evaluation metrics cover multiple dimensions.
- [ ] Baselines include classic methods, SOTA, and simple baselines.
- [ ] Ablation studies cover all proposed components.
- [ ] Compute estimates are reasonable and include a safety factor.
- [ ] Reproducibility information is complete.
- [ ] Statistical testing methods are specified.

---

## References

- [Experiment Planning Methods](references/experiment-planning.md)
- [Baseline Selection Guide](references/baseline-selection.md)
- [Ablation Design Guide](references/ablation-design.md)
- [Reproducibility Checklist](references/reproducibility-checklist.md)
- [Experiment Plan Template](templates/experiment-plan.md)
