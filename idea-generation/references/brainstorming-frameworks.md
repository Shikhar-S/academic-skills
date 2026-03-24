# Detailed Guide to 10 Ideation Frameworks

This document provides detailed explanations of the ten ideation frameworks used in the idea-generation workflow. Each framework includes a definition, operating steps, example, and suitable scenarios.

---

## Framework 1: Problem-First

### Definition

Start from real, existing pain points or unmet needs, then work backward to possible research directions. This is the most intuitive ideation style and helps ensure practical value.

### Operating Steps

1. **List problem sources**
   - Review difficulties you encountered in research or practice
   - Browse domain forums and Q&A sites (e.g., Stack Overflow, Reddit)
   - Read limitations sections of recent papers
   - Interview practitioners in the domain

2. **Classify and prioritize problems**
   - Group by severity, impact scope, and frequency
   - Prioritize high-frequency, high-impact problems

3. **Decompose problems**
   - Break big problems into researchable sub-problems
   - Identify root causes instead of surface symptoms

4. **Check researchability**
   - Can this be formalized as a research question?
   - Are there measurable evaluation metrics?
   - Is data obtainable?

### Example

- **Problem**: Large language models degrade significantly on long-context input
- **Decomposition**: Attention complexity, positional extrapolation, context information loss
- **Research direction**: Design a new positional encoding scheme that extrapolates beyond training length

### Suitable Scenarios

- You want clear practical value
- You have deep practical experience in a domain
- You want topics likely to gain fast community traction
- You are writing a problem-driven thesis

---

## Framework 2: Solution-First (Find Applications from Technique)

### Definition

Start from a new technique, algorithm, or tool, then ask where it can be applied. Useful when you already have a promising method but no best-fit use case yet.

### Operating Steps

1. **Analyze technique characteristics**
   - What are its core strengths?
   - Under what conditions does it work best?
   - What are its limits?

2. **Search application scenarios**
   - Which domains share similar demand structures?
   - Which existing methods are constrained by missing this capability?
   - Are there emerging scenarios still underexplored?

3. **Evaluate fit**
   - Does input/output format match the target problem?
   - Does it require heavy adaptation?
   - Are compute requirements reasonable?

4. **Define differentiation**
   - What unique advantages does this technique offer vs. existing methods?
   - Are those advantages substantial enough?

### Example

- **Technique**: Diffusion-model denoising mechanism
- **Property**: Can progressively recover structured information from noise
- **Application exploration**: Beyond image generation—molecules, protein folding, urban planning?
- **Research direction**: Apply diffusion models to code repair by treating buggy code as a noisy version

### Suitable Scenarios

- You just learned a new method and want to push its potential
- A method-oriented team is searching for applications
- You want cross-domain applied research
- The technique is saturated in its original domain

---

## Framework 3: Abstraction Ladder

### Definition

Move between abstraction levels. Going up reveals essence and shared structure; going down reveals new concrete instances. This helps you escape your current thinking level and discover hidden links.

### Operating Steps

1. **Set a starting point**
   - Choose a concrete problem or method you know well

2. **Climb up (abstract)**
   - Ask: What is the essence of this problem?
   - Ask: What broader class does it belong to?
   - Ask: What underlying principle drives it?
   - Continue upward until abstraction is sufficient

3. **Move sideways**
   - At the same abstraction level, identify other instances
   - Where else does this principle apply?

4. **Climb down (concretize)**
   - Start from the new abstract concept and materialize it
   - How can this principle be implemented?
   - Which datasets/tasks can validate it?

### Example

```
Concrete problem: Rare-word handling in machine translation
    ↑ abstraction
Rare-event handling (long-tail distribution)
    ↑ abstraction
Learning from limited samples (few-shot learning)
    → lateral move
Rare disease recognition in medical imaging
    ↓ concretization
Research direction: Use language-model knowledge to improve rare-disease image recognition
```

### Suitable Scenarios

- You feel stuck at one level of thought
- You want links between seemingly unrelated fields
- You want to generalize a successful specific experience
- You need deeper theoretical motivation

---

## Framework 4: Contradiction Hunting

### Definition

Actively seek contradictions, assumption conflicts, unquestioned defaults, or inconsistent results in existing research. Contradictions often indicate where understanding is incomplete.

### Operating Steps

1. **Inventory assumptions**
   - List widely accepted assumptions in your field
   - Ask: How strong is the evidence behind each?
   - Are counterexamples ignored?

2. **Compare results**
   - Compare similar experiments across papers
   - Are findings inconsistent?
   - Are inconsistencies due to setup differences?

3. **Theory vs. practice**
   - Do theoretical predictions match empirical behavior?
   - Which theoretically sound methods fail in practice?
   - Which theoretically weak methods surprisingly succeed?

4. **Investigate deeply**
   - What causes the contradiction?
   - Would resolving it produce new understanding?
   - Can experiments isolate the cause?

### Example

- **Contradiction**: Transformers are highly expressive in theory but weak on simple counting tasks
- **Investigation**: Positional encoding limits length generalization
- **Research direction**: Architectural improvements for robust counting and arithmetic reasoning

### Suitable Scenarios

- You deeply understand a field and can detect subtle inconsistencies
- You see conflicting conclusions after extensive reading
- Your reproduction results disagree with published results
- You want critical, assumption-challenging work

---

## Framework 5: Cross-Domain Transfer

### Definition

Bring successful methods, concepts, or theories from one field into another. Cross-domain transfer is a key innovation source because structurally similar problems are often solved differently across fields.

### Operating Steps

1. **Build a knowledge base**
   - Read surveys across multiple fields
   - Attend interdisciplinary academic events
   - Talk with researchers from other areas

2. **Find structural analogies**
   - Does your problem have an analog elsewhere?
   - Can methods from another field solve your problem?
   - Are data structures across fields similar?

3. **Assess transfer feasibility**
   - Do method assumptions hold in the target field?
   - What adaptations are needed?
   - Does transfer provide extra advantages?

4. **Design validation**
   - How will you evaluate transfer effectiveness?
   - Are suitable baselines available?

### Example

- **Source field**: Numerical methods for Navier-Stokes equations in fluid dynamics
- **Target field**: Information propagation simulation on large graph networks
- **Analogy**: Information flow ≈ fluid flow
- **Research direction**: Use multi-scale fluid simulation methods to accelerate graph message propagation

### Suitable Scenarios

- Researchers with multi-domain background
- Your current field feels mature and needs outside inspiration
- You detect structurally similar problems between domains
- You aim for pioneering interdisciplinary research

---

## Framework 6: What Changed (Recent Changes)

### Definition

Track recent breakthroughs, resource shifts, or social-environment changes, and ask what now becomes possible that was previously impossible. Great ideas often appear at change boundaries.

### Operating Steps

1. **Map recent changes**
   - What important breakthroughs happened in the last 6–12 months?
   - What new datasets or tools were released?
   - How did hardware capabilities change?
   - What policy or social-demand trends emerged?

2. **Analyze impact**
   - What newly possible things does this change enable?
   - What old constraints does it remove?
   - What new demands does it create?

3. **Assess timing**
   - Is the direction at the right moment?
   - Too early (infrastructure immature) or too late (saturated)?
   - What are competitors doing?

4. **Quick prototype validation**
   - Can you run a proof of concept with minimal resources?
   - Do preliminary results support your hypothesis?

### Example

- **Change**: Open-source LLMs have significantly improved in scale and capability
- **New possibility**: Research once requiring closed APIs can now be analyzed locally
- **Research direction**: Mechanistic interpretability for open-source models

### Suitable Scenarios

- Researchers tracking the frontier
- You want time-sensitive work with fast publication potential
- New technology has just emerged and remains underexplored
- You can clearly answer "why now?"

---

## Framework 7: Failure Analysis

### Definition

Treat failures as clues to new directions. Failures often reveal blind spots in our understanding, and those blind spots are worth researching.

### Operating Steps

1. **Collect failure cases**
   - Your failed experiments or rejected papers
   - Known failures in the field
   - Poor benchmark cases (error analysis)
   - Deployment issues from industry

2. **Attribute failures**
   - What is the root cause?
   - Method issue, data issue, or inherently hard problem?
   - Is failure fixable or does it require a new approach?

3. **Identify opportunities**
   - Does this failure point to an underexplored sub-problem?
   - Would fixing it yield major gains?
   - Do new technologies now overcome old limits?

4. **Draft solutions**
   - Propose solutions based on failure causes
   - Did other fields face similar failures and solve them?

### Example

- **Failure case**: Few-shot learning collapses on out-of-distribution data
- **Attribution**: Over-reliance on spurious features, amplified in few-shot settings
- **Research direction**: Robust few-shot learning against spurious features

### Suitable Scenarios

- You want to mine your own failures for direction
- Error analysis reveals systematic issues
- Limitations sections inspire you
- You want deep work on root causes

---

## Framework 8: Simplicity Test

### Definition

Challenge complex mainstream methods with simpler alternatives to test whether complexity is truly necessary. If simple methods perform similarly, the value of complexity should be re-evaluated.

### Operating Steps

1. **Choose target**
   - Pick a recent method considered effective but complex
   - Or pick an SOTA system and analyze components

2. **Run simplification experiments**
   - Remove components and observe changes (extended ablation)
   - Replace components with simpler alternatives
   - Design a minimal baseline

3. **Ensure fair comparison**
   - Keep data and hyperparameter budget comparable
   - Evaluate not only performance but also efficiency (speed, memory, energy)

4. **Analyze outcomes**
   - If simple is close: what components truly matter?
   - If simple is far behind: where does complexity create value?
   - Both outcomes can produce meaningful contributions

### Example

- **Target**: A multimodal system with multiple pretrained models and complex fusion
- **Simplification**: Single model + simple linear mapping
- **Finding**: Simple method reaches 90% performance at 10% compute
- **Research direction**: When complex fusion is actually necessary

### Suitable Scenarios

- You are skeptical of an "arms race" in a field
- You have limited compute and need efficiency
- You want critical work that sparks discussion
- You are writing an analysis paper

---

## Framework 9: Stakeholder Rotation

### Definition

Re-examine a problem from different stakeholder perspectives (users, developers, decision makers, affected groups, etc.). Different needs and constraints can reveal neglected directions.

### Operating Steps

1. **Identify stakeholders**
   - Who uses the technology?
   - Who deploys and maintains it?
   - Who is affected by outputs?
   - Who pays for it?
   - Who regulates it?

2. **Role-play perspectives**
   - Think from each stakeholder's viewpoint
   - What do they care about most? fear most?
   - What is their daily workflow?
   - How does this technology fit their process?

3. **Analyze demand differences**
   - Do stakeholder needs conflict?
   - Which needs are currently ignored?
   - What research is needed to satisfy them?

4. **Translate into research questions**
   - Turn needs into researchable questions
   - Prioritize high-impact, feasible items

### Example

- **Technology**: Automatic code generation tools
- **Developer view**: Wants correctness and efficiency
- **Engineering manager view**: Wants style and policy compliance
- **Security engineer view**: Worries about vulnerabilities
- **Beginner programmer view**: Wants learning support, not only answers
- **Research direction**: Security guarantees in automatic code generation

### Suitable Scenarios

- Technologies with social impact
- Human-computer interaction research
- Applied-value-oriented research
- Work involving ethics considerations

---

## Framework 10: Combine / Decompose

### Definition

Create new directions by combining or decomposing existing methods. Combination can deliver multiple strengths; decomposition helps deeply analyze and improve complex systems component-wise.

### Operating Steps

#### Combination Path

1. **List candidate methods**
   - Pick 2–3 methods with complementary strengths
   - Confirm overlapping or complementary problem coverage

2. **Analyze complementarity**
   - Can strengths of A offset weaknesses of B?
   - Can combination produce 1+1 > 2?
   - Is integration technically feasible?

3. **Design integration form**
   - Pipeline: output of A feeds B
   - Ensemble: run A and B jointly and fuse outputs
   - Hybrid: embed mechanism B inside architecture A

#### Decomposition Path

1. **Select target system**
   - Choose a complex end-to-end system

2. **Identify components**
   - What core components does it contain?
   - What is each component's function?
   - How do components interact?

3. **Study component-level opportunities**
   - Can one component be improved independently?
   - Can one component be replaced by a better alternative?
   - Are interactions sufficiently understood?

### Example

#### Combination example
- **Method A**: Retrieval-Augmented Generation (strong external knowledge use)
- **Method B**: Chain-of-Thought prompting (strong complex reasoning)
- **Combination**: Retrieve relevant knowledge, then perform chained reasoning for integration
- **Research direction**: A unified framework that dynamically decides retrieval and reasoning depth by problem complexity

#### Decomposition example
- **Target system**: In-context learning in large language models
- **Components**: Task recognition, pattern matching, knowledge extraction, format alignment
- **Research direction**: Mechanistic study of the task-recognition component

### Suitable Scenarios

- You want integrative research unifying multiple methods
- You want deep understanding of complex system behavior
- Two independent directions show intersection potential
- You are writing a system paper

---

## Framework Selection Guide

| Your current state | Recommended frameworks |
|----------|---------------|
| Clear problem but unclear solution | Problem-First, Failure Analysis |
| Learned a new method and seek applications | Solution-First, What Changed |
| Feeling stuck at one level | Abstraction Ladder, Cross-Domain Transfer |
| Skeptical of mainstream methods | Contradiction Hunting, Simplicity Test |
| Want socially impactful research | Stakeholder Rotation |
| Want integration or deeper analysis | Combine / Decompose |
| Unsure and want broad exploration | Use at least 3–5 frameworks in rotation |

---

## Usage Tips

1. **Do not use only one framework**: each has blind spots; combining frameworks covers more angles
2. **Quantity before quality**: avoid criticism while generating ideas
3. **Record everything**: keep all triggered ideas, even immature ones
4. **Set time constraints**: 15–30 minutes per framework to prevent premature deep dives
5. **Switch when stuck**: if one framework stalls, move to another
