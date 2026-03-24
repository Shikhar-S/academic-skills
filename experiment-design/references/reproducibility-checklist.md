# Reproducibility Checklist

## Overview

This document provides a comprehensive reproducibility checklist, adapted and extended from the NeurIPS Reproducibility Checklist, to ensure experimental results can be accurately reproduced by other researchers. Reproducibility is a foundation of scientific research and a key criterion in top-tier peer review.

---

## 1. Hardware Environment

### Required Disclosures

- [ ] GPU model (e.g., NVIDIA A100 80GB)
- [ ] Number of GPUs
- [ ] CPU model and core count
- [ ] System memory size
- [ ] Storage type (SSD / HDD)

### Recommended Disclosures

- [ ] GPU driver version
- [ ] CUDA version
- [ ] cuDNN version
- [ ] Whether multi-node distributed training is used
- [ ] Inter-node network setup (if distributed)

### Example Format

```
Hardware Environment:
- GPU: 4 × NVIDIA A100 (80GB)
- CPU: AMD EPYC 7763 64-Core
- Memory: 512 GB DDR4
- Storage: NVMe SSD
- CUDA: 12.1
- cuDNN: 8.9.0
- Driver Version: 535.86.10
```

---

## 2. Software Environment

### Required Disclosures

- [ ] Operating system and version
- [ ] Programming language version (e.g., Python 3.10.12)
- [ ] Deep learning framework and version (e.g., PyTorch 2.1.0)
- [ ] Version list of key packages

### Recommended Disclosures

- [ ] Full `requirements.txt` or `environment.yml`
- [ ] Docker image (if provided)
- [ ] Package installation commands

### Key Package Version Checklist

Versions of the following package categories should be explicitly recorded:

| Category | Common Packages |
|------|---------|
| Deep learning frameworks | PyTorch / TensorFlow / JAX |
| NLP tools | Transformers / spaCy / NLTK |
| Data processing | NumPy / Pandas / scikit-learn |
| Evaluation tools | SacreBLEU / seqeval / pycocotools |
| Distributed training | DeepSpeed / FSDP / Horovod |
| Experiment tracking | Weights & Biases / MLflow / TensorBoard |

### Example Format

```
Software Environment:
- OS: Ubuntu 22.04 LTS
- Python: 3.10.12
- PyTorch: 2.1.0
- Transformers: 4.35.0
- NumPy: 1.24.3
- CUDA Toolkit: 12.1
```

---

## 3. Random Seeds and Determinism

### Required Disclosures

- [ ] Whether random seeds were set
- [ ] Exact random seed values
- [ ] Number of different seeds used

### Recommended Disclosures

- [ ] How each randomness source is seeded
- [ ] Whether deterministic mode is enabled
- [ ] Known non-deterministic sources and their impact

### Randomness Source Checklist

Randomness sources that should be controlled include:

1. **Python built-in RNG**: `random.seed()`
2. **NumPy RNG**: `np.random.seed()`
3. **PyTorch CPU RNG**: `torch.manual_seed()`
4. **PyTorch GPU RNG**: `torch.cuda.manual_seed_all()`
5. **cuDNN determinism**: `torch.backends.cudnn.deterministic = True`
6. **cuDNN benchmark mode**: `torch.backends.cudnn.benchmark = False`
7. **Data loader randomness**: DataLoader `worker_init_fn` and `generator`
8. **Environment variable**: `PYTHONHASHSEED`

### Example Code

```python
import random
import numpy as np
import torch

def set_seed(seed: int):
    random.seed(seed)
    np.random.seed(seed)
    torch.manual_seed(seed)
    torch.cuda.manual_seed_all(seed)
    torch.backends.cudnn.deterministic = True
    torch.backends.cudnn.benchmark = False
    os.environ['PYTHONHASHSEED'] = str(seed)

# Seed list used: 42, 123, 456, 789, 1024
```

### Multi-Run Reporting Format

```
Table: Results Across Random Seeds

Seed   | F1     | Acc
-------|--------|------
42     | 88.3   | 89.7
123    | 88.1   | 89.5
456    | 88.5   | 89.9
789    | 87.9   | 89.3
1024   | 88.4   | 89.8
-------|--------|------
Mean   | 88.24  | 89.64
Std    | ±0.23  | ±0.23
```

---

## 4. Training Details

### Required Disclosures

- [ ] Optimizer type and parameters (learning rate, momentum, weight decay, etc.)
- [ ] Learning-rate schedule strategy and parameters
- [ ] Batch size (per GPU and total)
- [ ] Total training steps or epochs
- [ ] Early stopping strategy and patience
- [ ] Gradient clipping threshold
- [ ] Warmup steps or ratio

### Recommended Disclosures

- [ ] Mixed-precision settings (FP16 / BF16)
- [ ] Gradient accumulation steps
- [ ] Weight initialization method
- [ ] Dropout rate
- [ ] Label smoothing coefficient
- [ ] Full loss function definition
- [ ] Regularization methods and parameters

### Example Training Hyperparameters

```
Training Setup:
- Optimizer: AdamW (β1=0.9, β2=0.999, ε=1e-8)
- Learning Rate: 2e-5
- LR Scheduler: Linear decay with warmup
- Warmup Steps: 10% of total steps
- Weight Decay: 0.01
- Batch Size: 32 (per GPU) × 4 (GPU) = 128 (total)
- Epochs: 10
- Early Stopping: Validation F1 not improved for 3 consecutive epochs
- Gradient Clipping: max_norm = 1.0
- Dropout: 0.1
- Mixed Precision: BF16
- Gradient Accumulation: 2 steps
```

---

## 5. Data Preprocessing

### Required Disclosures

- [ ] Dataset name, version, and source link
- [ ] Sizes of train / validation / test sets
- [ ] Data splitting protocol (whether official split is used)
- [ ] Text preprocessing steps (tokenization, cleaning, normalization, etc.)
- [ ] Maximum sequence length and truncation strategy
- [ ] Usage of special tokens

### Recommended Disclosures

- [ ] Criteria for data filtering/selection
- [ ] Data augmentation strategy
- [ ] Method for class imbalance handling
- [ ] Vocabulary size and construction method
- [ ] Handling of missing values/outliers
- [ ] Dataset license terms

### Example Data Preprocessing Description

```
Data Preprocessing:
- Dataset: SQuAD 2.0 (official v2.0)
- Split: Official train/dev split
- Training set: 130,319 QA pairs
- Validation set: 11,873 QA pairs
- Tokenizer: BPE (from bert-base-uncased)
- Vocabulary size: 30,522
- Max sequence length: 384
- Doc stride: 128
- Truncation strategy: truncate context, keep full question
- Lowercasing: enabled
```

---

## 6. Evaluation Protocol

### Required Disclosures

- [ ] Exact definition of evaluation metrics
- [ ] Source of evaluation scripts (official or custom implementation)
- [ ] Model selection criterion (which checkpoint is used for final evaluation)
- [ ] Decoding strategy during evaluation

### Recommended Disclosures

- [ ] Evaluation frequency (every N steps or epochs)
- [ ] Post-processing steps (e.g., answer normalization, deduplication)
- [ ] Method for confidence intervals or statistical significance testing
- [ ] Human evaluation design (if applicable)

### Example Evaluation Protocol

```
Evaluation Protocol:
- Metrics: Exact Match (EM), F1
- Evaluation script: Official SQuAD 2.0 script
- Model selection: Checkpoint with best validation F1
- Evaluation frequency: Every 1000 steps
- Answer post-processing: Remove articles, punctuation, extra spaces
- Statistics: Mean ± std over 5 random seeds
- Significance test: Paired bootstrap test (p < 0.05)
```

---

## 7. Code and Data Release

### Strongly Recommended

- [ ] Release full training and evaluation code
- [ ] Provide pretrained model weight download links
- [ ] Provide preprocessing scripts
- [ ] Write a clear README for reproducing results

### Recommended

- [ ] Provide one-command reproducibility script
- [ ] Provide Docker environment
- [ ] Maintain code on GitHub
- [ ] Include expected outputs for verification

---

## 8. Full Reproducibility Verification Workflow

Before paper submission, run this final check workflow:

### Round 1: Documentation Check

1. Does the paper include all required experimental details?
2. Does the appendix include complete hyperparameter tables?
3. Is the code link provided?

### Round 2: Independent Reproduction Test

1. Ask a colleague not involved in the project to reproduce results from the paper description.
2. Record all issues encountered during reproduction.
3. Fill missing details based on feedback.

### Round 3: Code Check

1. Can the code run from scratch in a clean environment?
2. Are README commands complete and correct?
3. Is random seed control working as intended?

---

## 9. Common Reproducibility Issues and Solutions

| Issue | Cause | Solution |
|------|------|----------|
| Results vary run to run | Randomness not fully controlled | Verify seed setup for all randomness sources |
| Package install fails | Version conflicts | Provide full requirements.txt or Docker |
| Large discrepancy from paper results | Missing training details | Compare all hyperparameters/settings one by one |
| Different GPUs produce different results | Floating-point computation differences | Record hardware details and accept minor variance |
| Dataset version mismatch | Dataset updated | Clearly record dataset version and download link |
