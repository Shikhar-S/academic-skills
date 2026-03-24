# Story Templates and Analogy Library

This guide provides narrative structures and analogy material for use in "Step 3: Story-Based Explanation."

---

## Three Narrative Structures

### 1) Hero's Journey

**Best for**: papers with brand-new methods, pioneering work, or strong SOTA challenges.

**Structure mapping**:

| Story phase | Paper component | What to say |
|---------|------------|--------|
| Ordinary world | Background | Current technical status: "everyone uses method X" |
| Call to adventure | Problem/Gap | Existing weakness: "but X has a fatal limitation" |
| Mentor guidance | Related Work | Prior attempts and insights: "people tried Y, but it wasn't enough" |
| Crossing threshold | Core Idea | Spark of the new method: "one day they realized..." |
| Trials | Method Details | Design process and technical hurdles: "they had to overcome three barriers" |
| Final showdown | Experiments | Benchmark competition: "they fought across five arenas" |
| Triumphant return | Results | Outcome presentation: "they won the championship" |
| Bring back treasure | Contribution | Field-level value: "their treasure changed the village" |

**Opening example**:
```
Let Granny tell you a hero story—

In the deep-learning world, there was a challenge like One Piece:
everyone knew it existed, but no one could reach it.
The challenge: how can a model learn a new skill after seeing only a few examples?

Countless heroes tried—MAML from the Meta-Learning school,
Prototypical Networks from the Metric Learning school.
Everyone showed great moves, but each fell just short.

Then the authors of this paper appeared...
```

---

### 2) Detective Reasoning

**Best for**: analytical papers, theory papers, papers diagnosing issues in existing methods, interpretability papers.

**Structure mapping**:

| Story phase | Paper component | What to say |
|---------|------------|--------|
| Crime scene | Problem | Unusual phenomenon discovered: "model behavior is abnormal" |
| Gather clues | Observation/Analysis | Experiments and evidence collection |
| Eliminate suspects | Related Work | Rule out known explanations: "not A, not B" |
| Key evidence | Key Finding | Root cause identified: "aha, this is it" |
| Detective inference | Method/Theory | Infer conclusions and solutions from evidence |
| Truth revealed | Experiments | Validate whether inference is correct |
| Case report | Conclusion | Summarize findings and recommendations |

**Opening example**:
```
Kiddo, today's story is a detective case—better than Death Note.

Here's the scene: everyone says Transformers are powerful, right?
But then a strange thing appears—
when used on long sequences, performance suddenly collapses.

Is it a bug? Data issue? Or a design flaw in Transformers?

The authors put on their detective hats and started the investigation...
```

---

### 3) Cooking Competition

**Best for**: papers with many comparative experiments, benchmark-heavy papers, experimental parts of surveys.

**Structure mapping**:

| Story phase | Paper component | What to say |
|---------|------------|--------|
| Competition rules | Task Definition | Task and evaluation criteria |
| Contestant intro | Baselines | Competing methods |
| Secret ingredient | Novel Component | Distinctive part of proposed method |
| Cooking process | Method | How techniques are combined |
| Judges tasting | Evaluation | Metric outcomes |
| Component scoring | Ablation | Importance of each ingredient/step |
| Winner announced | Main Results | Final ranking and conclusion |
| Judges' comments | Analysis | Why it won, and how to improve |

**Opening example**:
```
Today Granny brings you a cooking competition, even more intense than Food Wars.

Challenge: with limited ingredients (small training data),
make a dish (high accuracy) that satisfies judges (benchmarks).

Contestants:
No.1: Chef MAML, expert in rapid seasoning (fast adaptation)
No.2: Chef ProtoNet, expert in ingredient grouping (prototype comparison)
No.3: this paper's method, a newcomer with a mysterious sauce!

Let the match begin—
```

---

## Choosing the Narrative Structure

| Paper characteristic | Recommended structure | Reason |
|---------|---------|------|
| Proposes a brand-new architecture/method | Hero's Journey | Clear "from nothing to something" story arc |
| Improves existing methods | Hero's Journey or Cooking Competition | Choose based on scale of improvement |
| Analysis/diagnosis research | Detective Reasoning | Natural "find issue → find cause → solve" logic |
| Heavy comparative experiments | Cooking Competition | Emphasis is on comparison and ranking |
| Theoretical proof papers | Detective Reasoning | Strong logical-inference story line |
| Survey / Review | Skip story; use a guided-tour tone | Reader needs structured overview |

---

## Analogy Library: Everyday Mappings for Common ML Concepts

### Models and Architectures

| Concept | Analogy | Source |
|------|------|------|
| Neural Network | A team of connected workers, each doing a small part of processing | Everyday |
| CNN | A detective with a magnifying glass scanning image patches | Everyday |
| RNN | A storyteller with memory who remembers earlier parts | Everyday |
| Transformer | An all-seeing moderator who listens to everyone and decides who matters most | Everyday |
| GAN | Counterfeit artist vs. inspector duel (generator vs discriminator) | Everyday |
| VAE | Magician that compresses into a tiny box and reconstructs from it | Everyday |
| Diffusion Model | Restorer who first dirties a painting, then learns to recover it | Everyday |
| Autoencoder | Fax machine process: compress then decompress and see how much is preserved | Everyday |

### Training Concepts

| Concept | Analogy | Source |
|------|------|------|
| Training | Skill cultivation / practice | Naruto |
| Overfitting | Memorizing past exam papers and failing a new one | Everyday |
| Underfitting | Taking the exam before studying enough | Everyday |
| Regularization | Limiting sweets per day to prevent cavities | Everyday |
| Dropout | Randomly sealing pathways during practice to strengthen remaining ones | Naruto |
| Batch Normalization | Re-calibrating seasoning after each batch to keep flavor stable | Everyday |
| Learning Rate | Step size while descending a mountain | Everyday |
| Epoch | One full pass through the textbook | Everyday |
| Batch Size | Number of exams graded at one time | Everyday |
| Gradient | Mountain slope indicating fastest descent direction | Everyday |
| Backpropagation | Teacher tracing mistakes backward from final score step by step | Everyday |
| Convergence | Different starts reaching the same skill level eventually | Everyday |

### Data Concepts

| Concept | Analogy | Source |
|------|------|------|
| Dataset | Ingredient pantry | Everyday |
| Data Augmentation | Re-cut and recook same ingredients to create more dishes | Everyday |
| Label | Tags on ingredients: this is apple, that is orange | Everyday |
| Feature | Attributes used to recognize a person | Everyday |
| Embedding | Representing something complex as a numeric vector | Everyday |
| Tokenization | Splitting a sentence into pieces like beads from a necklace | Everyday |

### Evaluation Concepts

| Concept | Analogy | Source |
|------|------|------|
| Accuracy | Hit rate of correct shots | Everyday |
| Precision | Of those you flagged as bad, how many were truly bad | Everyday |
| Recall | Of all truly bad cases, how many you caught | Everyday |
| F1 Score | Balance score between precision and recall | Everyday |
| Benchmark | Martial-arts tournament arena | Naruto |
| SOTA | Current arena champion | Everyday |
| Ablation Study | Remove one car part to test its necessity | Everyday |

### Advanced Concepts

| Concept | Analogy | Source |
|------|------|------|
| Transfer Learning | A pianist learns guitar faster due to transferable fundamentals | Everyday |
| Fine-tuning | A master chef adapting quickly to a new dish | Everyday |
| Pre-training | Build inner skill first, then learn any style faster | Wuxia literature |
| Self-supervised Learning | Create blanks in your own text and practice filling them | Everyday |
| Contrastive Learning | Learn what is similar and what is not | Everyday |
| Few-shot Learning | Recognize a new animal after seeing only a few photos | Everyday |
| Reinforcement Learning | Training a puppy with rewards for correct behavior | Everyday |
| Prompt Engineering | Giving precise instructions to a smart assistant | Everyday |
| Hallucination | Model speaks nonsense with confidence | Everyday |
| Scaling Law | Bigger models + more data usually means stronger performance | Dragon Ball |
| Emergent Ability | New capability suddenly appears after sufficient scale | Dragon Ball |
| Knowledge Distillation | Master condenses expertise to teach an apprentice | Everyday |
| Ensemble | Combined strength of multiple contributors | Everyday |
| Latent Space | Hidden parallel world where everything has a compact identity | Everyday |
| Attention Mechanism | Your eyes naturally locking onto the most important person in a crowd | Everyday |

---

## Principles for Using Analogies

1. **Accuracy first** — analogies must preserve technical correctness
2. **Intuition first** — choose easiest-to-understand analogies; anime is optional
3. **Use in moderation** — 2–3 analogies per step are usually enough
4. **Stay consistent** — keep the same analogy for the same concept within one explanation
5. **Reader first** — if reader does not watch anime, use more everyday analogies
6. **Keep it fresh** — avoid repetitive near-identical analogies in one paper

---

## Story Ending Template

After each story, provide a mapping back to technical content:

```
Alright, story time is over.
Let Granny map the story back to the paper:
- "___" in the story corresponds to "___" in the paper
- "___" in the story corresponds to "___" in the paper
- "___" in the story corresponds to "___" in the paper

Clearer now? Ask Granny if you want another walkthrough.
```

This mapping is essential so readers retain technical meaning, not just narrative flavor.
