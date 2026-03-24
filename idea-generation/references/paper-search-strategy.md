# Literature Search Strategy

This document explains how to search literature systematically to validate idea novelty and build a knowledge foundation of related work.

---

## I. Keyword Design

Keyword quality directly determines search efficiency and coverage. Strong keyword sets help you quickly locate highly relevant literature.

### 1.1 Extract Core Keywords

Extract these keyword types from your research idea:

| Type | Description | Examples |
|------|------|------|
| Method keywords | Techniques or algorithms used | transformer, diffusion model, contrastive learning |
| Problem keywords | Task/problem being solved | text summarization, object detection, drug discovery |
| Domain keywords | Academic field | NLP, computer vision, bioinformatics |
| Data keywords | Data type or dataset | clinical notes, satellite images, ImageNet |

### 1.2 Expand with Synonyms and Related Terms

For each core keyword, list synonyms, hypernyms, and hyponyms:

```
Core keyword: text summarization
├── Synonyms: document summarization, automatic summarization
├── Hypernyms: text generation, natural language generation
├── Hyponyms: extractive summarization, abstractive summarization,
│            multi-document summarization
└── Related: information compression, key point extraction
```

### 1.3 Keyword Combination Strategy

Use Boolean operators:

- **AND**: narrow scope, e.g. `"diffusion model" AND "text generation"`
- **OR**: broaden scope, e.g. `"summarization" OR "compression"`
- **NOT**: exclude irrelevant results, e.g. `"transformer" NOT "electrical"`
- **Quotes**: exact phrase matching, e.g. `"chain of thought"`

### 1.4 Iterative Keyword Refinement

Search is iterative:

1. Search with initial keywords
2. Learn new terms from found papers
3. Update keyword sets with new terms
4. Repeat until no new relevant literature appears

---

## II. Recommended Search Tools

### 2.1 Semantic Scholar

- **URL**: https://www.semanticscholar.org
- **Features**:
  - Semantic search that captures intent
  - Influence indicators (Highly Influential Citations)
  - API support for programmatic search
  - TLDR feature for quick paper summaries
- **Best for**: exploratory search, high-impact paper discovery
- **Tips**:
  - Use natural-language queries; Boolean operators often unnecessary
  - Filter by "Fields of Study"
  - Prioritize "Highly Influential" citations over raw citation counts
  - Use Research Feed to track topics

### 2.2 Google Scholar

- **URL**: https://scholar.google.com
- **Features**:
  - Broadest coverage across sources
  - Strong citation tracing
  - "Cited by" and "Related articles"
  - Alert subscriptions
- **Best for**: confirmatory search, citation tracing
- **Tips**:
  - Use `allintitle:` to target title terms
  - Use `author:` for author-specific search
  - Use "Since [year]" for recent work
  - Create a Scholar profile to track field dynamics
  - Set Scholar alerts for key terms

### 2.3 arXiv

- **URL**: https://arxiv.org
- **Features**:
  - Preprint platform, often earliest release point
  - Fully open access
  - Daily updates
  - Category browsing (cs.CL, cs.CV, cs.LG, etc.)
- **Best for**: latest frontier tracking, unpublished-yet work
- **Tips**:
  - Use arXiv Sanity (or similar) for semantic discovery
  - Subscribe to daily category digests
  - Use Papers With Code for linked implementations
  - Note: arXiv papers are not peer-reviewed and quality varies

### 2.4 DBLP

- **URL**: https://dblp.org
- **Features**:
  - Comprehensive CS bibliography index
  - Browse by author, conference, or journal
  - Structured data suitable for batch analysis
- **Best for**: checking formal publication versions, full author records
- **Tips**:
  - Verify whether a paper was accepted by top venues
  - Browse historical proceedings for target conferences

### 2.5 ACL Anthology

- **URL**: https://aclanthology.org
- **Features**:
  - Dedicated NLP repository
  - Full ACL-family venue coverage
  - Fully open access
- **Best for**: deep NLP literature search

### 2.6 Other Tools

| Tool | Use |
|------|------|
| Connected Papers | Visualize paper relationships |
| Research Rabbit | Explore related papers via recommendation-style discovery |
| Elicit | Use AI to extract information from papers |
| Litmaps | Build visual literature maps |
| Papers With Code | Find code and leaderboards linked to papers |

---

## III. Snowballing

Snowballing starts from known papers and progressively expands literature coverage.

### 3.1 Forward Snowballing

Start from an important known paper and inspect later papers that cite it.

**Procedure**:
1. Find a core related paper for your idea (seed paper)
2. Use "Cited by" in Google Scholar/Semantic Scholar
3. Scan cited-by list and pick likely relevant titles
4. Sort by time; prioritize recent citations
5. Repeat for newly found relevant papers

**Purpose**:
- Trace post-seed development directions
- Check whether your idea was already realized later
- Understand latest progress

### 3.2 Backward Snowballing

Start from a paper's references to trace prior foundations.

**Procedure**:
1. Read the seed paper's Related Work section
2. Scan its references
3. Pick repeatedly cited or emphasized papers
4. Repeat for newly found papers

**Purpose**:
- Find foundational work in the direction
- Understand historical evolution
- Discover overlooked earlier work

### 3.3 Author Tracking

Track key authors and their groups.

**Procedure**:
1. Identify first and corresponding authors of core papers
2. Visit their Scholar profiles or personal pages
3. Review their other publications
4. Track their latest output

**Purpose**:
- Identify major research teams
- Anticipate likely next moves
- Avoid direct collisions with highly active groups (or pursue collaboration)

### 3.4 Stopping Criteria for Snowballing

You can stop when:

- Newly found papers are no longer directly relevant
- The same set of papers keeps recurring (saturation)
- Major groups in the direction are covered
- You have a literature table with ~15–30 core papers

---

## IV. How to Judge Paper Importance

After finding many papers, quickly identify the important ones using these dimensions.

### 4.1 Publication Venue

Venue is an important quality signal (not the only one).

**Top-venue references**:
- **Machine Learning**: NeurIPS, ICML, ICLR
- **NLP**: ACL, EMNLP, NAACL
- **Computer Vision**: CVPR, ICCV, ECCV
- **AI**: AAAI, IJCAI
- **Data Mining / IR**: KDD, WWW, SIGIR
- **Journals**: JMLR, TPAMI, TACL, Nature Machine Intelligence

**Notes**:
- arXiv preprints can be excellent or weak
- Workshop papers are often early-stage but may contain novel ideas
- Rejection does not imply no value

### 4.2 Citation Quantity and Quality

- **Citation count**: high count often indicates influence, but consider paper age
- **Citation velocity**: rapid citation growth in short time is noteworthy
- **Citation quality**: citations from top venues vs. low-quality venues
- **Semantic Scholar "Highly Influential Citations"**: especially informative

### 4.3 Fast Reading Strategy

For large result sets, use this triage:

1. **Title** (5 sec): directly relevant?
2. **Abstract** (30 sec): does problem/method/result match your idea?
3. **Figures/Tables** (1 min): core results and architecture
4. **Conclusion** (1 min): main contributions and limits
5. **Last intro paragraph** (1 min): authors' contribution summary

If still relevant after these five steps, proceed to deeper reading.

### 4.4 Paper Categorization

Classify papers by relation to your idea:

| Category | Description | Action |
|------|------|------|
| Directly related | High overlap with your idea | Read carefully; assess differences |
| Method-related | Similar methods for different problems | Learn method details |
| Problem-related | Similar problem with different methods | Use as baseline references |
| Indirectly related | Background or theoretical support | Read selectively |
| Irrelevant | Off-topic | Exclude |

---

## V. Search Process Summary

### Full Search Checklist

- [ ] Extract core keywords from idea (method/problem/domain/data)
- [ ] Expand synonyms and related terms for each core keyword
- [ ] Build 3–5 keyword combinations
- [ ] Run exploratory search on Semantic Scholar
- [ ] Run confirmatory search on Google Scholar
- [ ] Search latest preprints on arXiv
- [ ] Select 2–3 seed papers for snowballing
- [ ] Perform forward snowballing (cited-by)
- [ ] Perform backward snowballing (references)
- [ ] Track other work by key authors
- [ ] Classify papers and assess importance
- [ ] Confirm saturation (no new relevant papers)
- [ ] Update novelty judgment for the idea
- [ ] Build structured literature table

### Suggested Time per Idea

| Step | Suggested Time |
|------|----------|
| Keyword design | 15–30 min |
| Multi-platform search | 1–2 h |
| Snowballing | 1–2 h |
| Classification and assessment | 1–2 h |
| **Total per idea** | **3–6 h** |

### Common Mistakes

1. **Keywords too narrow**: only searching familiar terms and missing work from other communities
2. **Only reading recent papers**: missing foundational classics
3. **Only searching English papers**: some fields have important non-English literature
4. **Confirmation-search bias**: seeking only supporting evidence
5. **Stopping too early**: stopping after a few related papers before saturation
6. **Over-searching**: endless search that blocks progression to next stage
