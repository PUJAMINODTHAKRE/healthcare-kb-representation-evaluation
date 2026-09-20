# Healthcare Knowledge Representation: Comparative Evaluation

[![Published](https://img.shields.io/badge/Published-Springer%202026-2E5AAC?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)
[![DOI](https://img.shields.io/badge/DOI-10.1007%2F978--3--032--24807--7__4-2E8B57?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)
[![Domain](https://img.shields.io/badge/Domain-Healthcare%20AI-6C757D?style=flat-square)](#)
[![Focus](https://img.shields.io/badge/Focus-Knowledge%20Representation%20%7C%20Knowledge%20Graphs-D97706?style=flat-square)](#)
[![Research](https://img.shields.io/badge/Research-Comparative%20Evaluation-7C3AED?style=flat-square)](#)

> **Research companion to a published comparative study of knowledge-representation paradigms for healthcare question answering.**

<p align="center">
  <img src="research-pipeline.svg" alt="Research Pipeline" width="900">
</p>

<p align="center">
  <em>
    From representation to reasoning: examining how the structure of knowledge
    influences query coverage, inference, and explainability.
  </em>
</p>

---

## Research Snapshot

| | |
|---|---|
| **Research Area** | Knowledge Representation & Reasoning |
| **Application Domain** | Healthcare Question Answering |
| **Benchmark** | 47 curated cardiovascular patient records |
| **Clinical Queries** | 5 progressively complex benchmark queries |
| **KR Paradigms** | 7 representation approaches |
| **Evaluation Dimensions** | Semantic expressiveness · Query coverage · Explainability · Scalability |
| **Core Analytical Measure** | Reasoning depth |
| **Implementation** | Python · SQLite · JSON · RDF · OWL · RDFLib · OWL-RL · SPARQL |
| **Publication** | Springer, 2026 |
| **Repository Role** | Research companion & methodological record |

---

## Overview

Healthcare Question Answering Systems (QAS) require more than retrieving isolated facts. Clinical questions may involve logical conditions, quantified statements, relationships among patient attributes, interacting comorbidities, treatment guidance, and contextual information.

This research investigates how the choice of **Knowledge Representation (KR)** paradigm influences the reasoning capability of healthcare expert systems and their ability to answer increasingly complex questions.

The study compares seven KR paradigms within a common evaluation framework:

**Propositional Logic · First-Order Predicate Logic · Rule-Based Systems · Relational Databases · Frame-Based Models · Ontologies · Knowledge Graphs**

A curated cardiovascular benchmark containing **47 patient records** was used together with **five benchmark clinical queries (Q1–Q5)** designed to increase progressively in reasoning complexity.

The work was published in the proceedings of the **2026 Computing Conference** by Springer.

### Published Article

**Tripathi, Atul Kumar; Thakre, Puja Minodji; Chatterjee, Niladri.**

*Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms*

*Intelligent Computing: Proceedings of the 2026 Computing Conference, Volume 2*

*Lecture Notes in Networks and Information Systems, Vol. 1950, pp. 38–54.*

Springer, 2026.

**DOI:** [10.1007/978-3-032-24807-7_4](https://doi.org/10.1007/978-3-032-24807-7_4)

---

## Research Question

> **How does the choice of knowledge representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

The study addresses this question by exposing different representation paradigms to a common cardiovascular knowledge domain and a sequence of clinical queries with increasing reasoning requirements.

The central relationship investigated is:

```text
Knowledge Representation
          ↓
Encoded Structure & Relations
          ↓
Reasoning Capability
          ↓
Query Coverage
          ↓
Explainability
```

The research therefore focuses not only on how information is represented, but also on how representation affects the kinds of questions an intelligent system can answer and explain.

---

## Motivation

Knowledge representation is a foundational component of intelligent systems.

Different representation paradigms provide different mechanisms for expressing:

- facts
- relationships
- logical constraints
- hierarchies
- semantic concepts
- contextual information
- inferential connections

A representation that is sufficient for a simple Boolean query may not naturally support a question involving several interacting entities and relations.

The study therefore uses a **progressively more demanding benchmark** to investigate the expressive and reasoning boundaries of different KR paradigms.

---

## What Was Compared?

The study examines seven representation paradigms.

| Paradigm | Representation Principle | Main Role |
|---|---|---|
| **Propositional Logic** | Atomic propositions and logical connectives | Boolean reasoning |
| **First-Order Predicate Logic (FOPL)** | Predicates, variables, relations, and quantification | Relational and quantified reasoning |
| **Rule-Based Systems** | Explicit IF–THEN rules and inference | Rule-driven reasoning |
| **Relational Databases** | Tabular representation accessed through SQL | Structured relational querying |
| **Frame-Based Models** | Slot–filler representation of entities | Structured entity and attribute reasoning |
| **Ontologies** | Concepts, hierarchies, constraints, and semantic relations | Semantic and subclass-based inference |
| **Knowledge Graphs** | Connected entities and relations | Multi-hop and contextual reasoning |

A common cardiovascular schema was used across the implementations to support a more consistent comparison.

---

## Evaluation Framework

The methodology evaluates the representation paradigms across four major dimensions.

| Dimension | What It Examines |
|---|---|
| **Semantic Expressiveness** | Ability to represent hierarchical, relational, and contextual medical knowledge |
| **Query Coverage** | Which benchmark queries can be successfully answered |
| **Explainability** | Transparency of reasoning and availability of interpretable traces |
| **Scalability** | Ability to accommodate larger datasets and increasingly complex reasoning tasks |

### Semantic Expressiveness

Semantic expressiveness concerns the ability of a representation to capture increasingly rich forms of medical knowledge, including relationships, hierarchical concepts, and contextual constraints.

### Query Coverage

Query coverage measures whether a representation paradigm can successfully answer a benchmark query.

The five benchmark queries progress through:

```text
Q1 → Boolean
Q2 → Universal / Quantified
Q3 → Relational
Q4 → Multi-relational
Q5 → Contextual
```

### Explainability

Explainability concerns how transparently a system can show why an answer was obtained.

Depending on the representation, this may involve:

- explicit rule traces
- SQL query results
- slot-based traversal
- inferred triples
- graph-based reasoning paths

### Scalability

Scalability concerns the ability to extend a representation toward larger datasets and increasingly complex reasoning tasks.

The main published comparative results emphasize **query coverage, reasoning depth, and explainability**, while scalability is discussed as an important broader consideration.

---

## Reasoning Depth

Reasoning depth measures the inferential complexity involved in deriving an answer.

For symbolic systems, it can correspond to the minimum chain of rules required for a derivation.

For graph-based reasoning, the paper defines reasoning depth as the minimum path length among valid reasoning paths supporting a query:

<p align="center">
  <strong><code>RD(q) = min<sub>p ∈ P(q)</sub> |p|</code></strong>
</p>

where:

- `P(q)` denotes the set of valid reasoning paths supporting query `q`
- `|p|` denotes the length of path `p`

For example:

```text
A → B → C → D
```

contains three relational steps and therefore has path length 3.

This provides a way to distinguish shallow fact retrieval from deeper multi-step inference.

---

## Research Pipeline

<p align="center">
  <img src="research-pipeline.svg" alt="Research Pipeline" width="900">
</p>

Conceptually, the study follows:

```text
Clinical Knowledge
        ↓
Common Representation Schema
        ↓
Multiple KR Paradigms
        ↓
Progressive Clinical Queries
        ↓
Expert-System Prototypes
        ↓
Comparative Evaluation
        ↓
Research Findings
```

The cardiovascular knowledge was aligned across the representation paradigms so that the comparison focused on differences in representation and reasoning capability.

---

## Benchmark Design

The benchmark consists of **47 curated cardiovascular patient records**.

Five benchmark queries were formulated to progressively stress the expressive and inferential capabilities of the representation paradigms.

The query sequence moves from simple Boolean conditions toward relational, multi-relational, and contextual reasoning.

---

## Benchmark Queries

### Q1 — Boolean

> **“Is a patient at risk of heart disease if chest pain is present and smoking history is negative?”**

**Reasoning category:** Boolean reasoning

---

### Q2 — Universal

> **“Are all patients over 60 years old with hypertension at elevated risk of cardiovascular disease?”**

**Reasoning category:** Universal / quantified reasoning

---

### Q3 — Relational

> **“What are the cardiovascular risks for patients with both diabetes and obesity?”**

**Reasoning category:** Relational reasoning

---

### Q4 — Multi-relational

> **“Which treatment guidelines are applicable for diabetic patients with left ventricular hypertrophy and a history of atrial fibrillation?”**

**Reasoning category:** Multi-relational reasoning

---

### Q5 — Contextual

> **“Suggest interventions for patients with comorbidities similar to those reported in recent literature.”**

**Reasoning category:** Contextual reasoning

---

## Progressive Query Complexity

The benchmark deliberately follows:

```text
Q1  Boolean
 ↓
Q2  Quantified
 ↓
Q3  Relational
 ↓
Q4  Multi-relational
 ↓
Q5  Contextual
```

This design makes it possible to examine how representation capability changes as reasoning requirements increase.

---

## Implementation

Lightweight expert-system prototypes were implemented using open-source tools.

All implementations shared a common schema aligned with the cardiovascular knowledge domain.

| KR Paradigm | Implementation Approach |
|---|---|
| **Propositional Logic** | Python logical conditions |
| **First-Order Predicate Logic (FOPL)** | Relational-query simulation using SQLite |
| **Rule-Based Systems** | Python rule execution |
| **Relational Databases** | SQLite / SQL queries |
| **Frame-Based Models** | Slot–filler JSON structures |
| **Ontologies** | RDF / OWL using RDFLib and OWL-RL |
| **Knowledge Graphs** | RDF triple stores with SPARQL queries |

The implementations were intentionally lightweight so that the comparison would focus on **representation and reasoning properties** rather than differences in software infrastructure.

---

## Comparative Results

### Published Query-Coverage Results

The following table reproduces the published comparative result reported in the paper.

| Paradigm | Q1 | Q2 | Q3 | Q4 | Q5 | Explainability | Reasoning Depth |
|---|:---:|:---:|:---:|:---:|:---:|---|:---:|
| **Propositional Logic** | ✓ | – | – | – | – | Rule-based trace | 1 |
| **Rule-Based Systems** | ✓ | ✓ | – | – | – | Rule-based trace with patient list | 1 |
| **Relational Database** | ✓ | ✓ | ✓ | – | – | Direct SQL query results | 1 |
| **Frames** | ✓ | ✓ | ✓ | – | – | Graph traversal with slot-based reasoning | 1–2 |
| **Ontology (OWL)** | ✓ | ✓ | ✓ | ✓ | – | Inferred triples via SPARQL | 1–2 |
| **Knowledge Graph** | ✓ | ✓ | ✓ | ✓ | ✓ | Path-based traces with multi-hop reasoning | 3 |

---

## Important FOPL Note

The paper discusses **First-Order Predicate Logic (FOPL)** as one of the seven investigated KR paradigms.

However, the published comparative table contains **six rows** and does not report a separate Q1–Q5 coverage row for FOPL.

This repository intentionally preserves the published table rather than inventing, estimating, or reconstructing an additional FOPL result.

This is an important distinction for scientific transparency and reproducibility.

---

## Interpreting the Results

Within the benchmark reported in the paper, the representation paradigms exhibit different coverage patterns as query complexity increases.

### Propositional Logic

Supports simple Boolean reasoning but is limited when richer relations among entities are required.

### Rule-Based Systems

Extend reasoning through explicitly encoded rules and support a broader range of structured reasoning than purely propositional conditions.

### Relational Databases

Support structured relational querying through SQL, extending coverage to Q3, but provide limited semantic and hierarchical reasoning.

### Frame-Based Models

Represent entities using structured slot–filler relationships and support Q1–Q3, while remaining limited for more complex multi-relational inference.

### Ontologies

Provide formal semantics and subclass-based inference, extending the published coverage through Q4.

### Knowledge Graphs

Achieved complete coverage of **Q1–Q5** in the published benchmark and supported:

- multi-hop reasoning
- contextual integration
- path-based explanation
- interconnected heterogeneous information

---

## Reasoning and Explainability

The research considers not only whether an answer can be generated, but also how the reasoning leading to that answer can be represented and inspected.

The published comparison associates different paradigms with different forms of reasoning trace:

| Representation | Example Reasoning Trace |
|---|---|
| **Propositional Logic** | Rule-based trace |
| **Rule-Based Systems** | Rules and derived patient lists |
| **Relational Database** | Direct SQL query results |
| **Frames** | Slot-based traversal |
| **Ontology** | Inferred triples through semantic relations |
| **Knowledge Graph** | Path-based multi-hop reasoning |

Knowledge Graphs make relationships explicit through connected entities and edges, enabling path-based explanations for multi-step reasoning.

---

## Why Query Coverage Matters

A representation may store information effectively while still being unable to support a particular type of question.

For this reason, **query coverage** is central to the comparative evaluation.

The benchmark does not ask all paradigms to solve only a simple retrieval task.

Instead, the requirements increase systematically:

```text
Simple logical conditions
          ↓
Quantified reasoning
          ↓
Relational reasoning
          ↓
Multi-relational reasoning
          ↓
Contextual reasoning
```

This exposes the points at which different representation paradigms encounter expressive or inferential limitations.

---

## Research Contribution

This project was conducted collaboratively by:

### Puja Minodji Thakre

Puja's contribution primarily focused on the **comparative and analytical aspects** of the study, including:

- comparative analysis of evaluation outcomes
- analysis of **query coverage across representation paradigms**
- interpretation of comparative findings
- review and refinement of the manuscript during revision stages

This work connected the computational evaluation with the comparative interpretation of the experimental results.

### Atul Kumar Tripathi

Contributed to:

- development of the comparative evaluation framework
- benchmark construction
- implementation-oriented components
- organization of the experimental comparison

### Niladri Chatterjee

Contributed research:

- supervision
- methodological guidance
- academic direction

> **Contribution note:** These descriptions summarize the collaborators' working roles. The published paper does not contain a formal CRediT-style author-contribution statement.

---

## Key Findings

Within the scope of the experimental benchmark:

### Query complexity affects representation capability

Different KR paradigms support different levels and types of reasoning, with differences becoming more apparent as query complexity increases.

### Classical representations remain useful

Simpler representation mechanisms can effectively support explicitly structured and lower-complexity reasoning tasks.

### Knowledge Graphs achieved complete benchmark coverage

Knowledge Graphs successfully answered **all five benchmark queries Q1–Q5** in the published comparison.

### Reasoning depth provides an additional analytical dimension

The study considers not only whether a query can be answered, but also the inferential structure required to derive the answer.

### Representation influences explainability

Different representations produce different forms of reasoning trace, with graph structures supporting explicit path-based explanations for multi-hop inference.

### Expressiveness has operational costs

More expressive knowledge structures require additional modelling, construction, and verification effort.

---

## Research Significance

The broader research perspective can be expressed as:

```text
How knowledge is represented
            ↓
What relationships can be encoded
            ↓
What reasoning can be performed
            ↓
Which questions can be answered
            ↓
How those answers can be explained
```

This connects the work to research across:

`Knowledge Representation`

`Knowledge Graphs`

`Healthcare Question Answering`

`Semantic Web`

`Explainable AI`

`Machine Learning`

`Structured Knowledge`

`Intelligent Information Systems`

---

## Operational Considerations

The paper discusses practical considerations associated with graph-based knowledge representation.

Knowledge Graph technologies can support the integration of:

- structured patient information
- domain concepts
- semantic relationships
- clinical guidelines
- external knowledge sources

At the same time, constructing a domain-specific Knowledge Graph can require substantial effort involving:

- data preprocessing
- schema alignment
- entity–relation extraction
- knowledge construction
- validation

This creates an important trade-off between richer representation and the effort required to construct and maintain that representation.

---

## Limitations and Scope

The findings should be interpreted within the boundaries of the experimental setup.

### Dataset Size

The benchmark contains only **47 curated cardiovascular patient records**, which limits generalizability.

### Simulated Logic Reasoning

Propositional and FOPL reasoning were simulated through Python conditionals and SQL-style relational queries rather than dedicated logic engines.

Consequently, these implementations should not be interpreted as complete realizations of the full theoretical capabilities of those formalisms.

### Manual Knowledge Construction

Subclass relationships in the ontology and Knowledge Graph were manually curated.

### Comparative Research Scope

The benchmark was designed for comparative evaluation of knowledge-representation paradigms rather than clinical deployment or clinical validation.

### Generalization

Evaluation on larger and more diverse clinical corpora would be required to determine how the observed patterns extend beyond this benchmark.

---

## Future Research Directions

The limitations identified in the study motivate several directions for future work.

### Larger-Scale Evaluation

Extend the comparative evaluation to larger clinical corpora and broader healthcare scenarios.

### Automated Ontology Alignment

Reduce dependence on manually curated semantic relationships through automated or semi-automated ontology alignment.

### Automated Knowledge Graph Construction

Develop more scalable pipelines for constructing graph-based knowledge from structured and unstructured biomedical information.

### Hybrid Neuro-Symbolic Reasoning

Combine symbolic Knowledge Graph reasoning with machine-learning or language-model-based methods.

### Explainable Reasoning Frameworks

Develop standardized methods for validating reasoning traces and inference paths.

### Time-Critical Knowledge-Based Systems

The broader direction suggested by the study is toward knowledge-based systems capable of selecting appropriate representation and reasoning mechanisms according to query complexity and temporal requirements.

---

## Data and Reproducibility

This repository is intended as a **research companion and methodological record** for the published study.

### Included

The repository documents:

- research question
- benchmark design
- exact benchmark queries
- KR paradigms
- implementation approaches
- evaluation dimensions
- reasoning-depth formulation
- published comparative results
- contribution perspective
- methodological limitations
- publication metadata

### Not Included

The repository does not include:

- patient-level records
- personally identifiable information
- restricted clinical material
- the publisher-controlled Springer PDF

### Reproducibility Scope

The repository documents the experimental framework and analytical structure of the research, but should **not be interpreted as a claim of complete end-to-end computational reproducibility**.

This distinction reflects the data and implementation limitations described in the published study.

---

## Repository Guide

| File / Resource | Purpose |
|---|---|
| [`README.md`](README.md) | Research overview, benchmark, results, contribution, and scope |
| [`docs/METHODOLOGY.md`](docs/METHODOLOGY.md) | Detailed research methodology and benchmark design |
| [`docs/EVALUATION_FRAMEWORK.md`](docs/EVALUATION_FRAMEWORK.md) | Evaluation dimensions, query coverage, reasoning depth, and explainability |
| [`docs/CONTRIBUTIONS.md`](docs/CONTRIBUTIONS.md) | Collaborative research contribution perspective |
| [`docs/REPRODUCIBILITY.md`](docs/REPRODUCIBILITY.md) | Data availability, implementation scope, and reproducibility considerations |
| [`analysis/EVALUATION_SCHEMA.csv`](analysis/EVALUATION_SCHEMA.csv) | Structured representation of the published comparative evaluation |
| [`research-pipeline.svg`](research-pipeline.svg) | Visual representation of the research workflow |
| [`CITATION.cff`](CITATION.cff) | Machine-readable citation metadata |
| [`NOTICE.md`](NOTICE.md) | Repository, publication, and data-use notice |

---

## Repository Structure

```text
healthcare-kb-representation-evaluation/
│
├── README.md
├── .gitignore
├── CITATION.cff
├── NOTICE.md
├── research-pipeline.svg
│
├── docs/
│   ├── CONTRIBUTIONS.md
│   ├── EVALUATION_FRAMEWORK.md
│   ├── METHODOLOGY.md
│   └── REPRODUCIBILITY.md
│
└── analysis/
    └── EVALUATION_SCHEMA.csv
```

---

## Publication

### Published Article

**Tripathi, Atul Kumar; Thakre, Puja Minodji; Chatterjee, Niladri.**

**Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms**

*Intelligent Computing: Proceedings of the 2026 Computing Conference, Volume 2*

*Lecture Notes in Networks and Information Systems, Vol. 1950, pp. 38–54.*

Springer, 2026.

**DOI:**  
https://doi.org/10.1007/978-3-032-24807-7_4

---

## Citation

If you use, extend, or reference this research, please cite the published article:

```bibtex
@inproceedings{tripathi2026knowledge,
  author    = {Tripathi, Atul Kumar and Thakre, Puja Minodji and Chatterjee, Niladri},
  title     = {Knowledge Representation for Healthcare Systems:
               A Comparative Analysis of Performance of Different
               Representation Paradigms},
  booktitle = {Intelligent Computing:
               Proceedings of the 2026 Computing Conference},
  series    = {Lecture Notes in Networks and Information Systems},
  volume    = {1950},
  pages     = {38--54},
  year      = {2026},
  publisher = {Springer},
  doi       = {10.1007/978-3-032-24807-7_4}
}
```

---

## Research Links

### Publication

[![Springer DOI](https://img.shields.io/badge/Springer-DOI-2E5AAC?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)

[Read the published article](https://doi.org/10.1007/978-3-032-24807-7_4)

### Google Scholar

[View Puja's Google Scholar Profile](https://scholar.google.com/citations?user=FoOvhlQAAAAJ&hl=en)

### ORCID

[View Puja's ORCID Profile](https://orcid.org/0009-0001-7924-5363)

### Academic Website

_Add academic website when available_

### LinkedIn

[View Puja's LinkedIn Profile](https://www.linkedin.com/in/puja-minodji-thakre/)

---

## Research Keywords

`Knowledge Representation`  
`Knowledge Graphs`  
`Healthcare Question Answering`  
`Healthcare AI`  
`Expert Systems`  
`Explainable AI`  
`Semantic Web`  
`RDF`  
`OWL`  
`SPARQL`  
`Statistical Learning`  
`Machine Learning`  
`Structured Knowledge`  
`Intelligent Information Systems`

---

## Repository Philosophy

This repository follows three principles.

### Scientific Accuracy

The repository preserves the published research faithfully and does not introduce experimental results that are not reported in the paper.

### Research Transparency

The benchmark, implementation scope, contribution boundaries, and methodological limitations are documented explicitly.

### Reproducibility with Appropriate Scope

The repository provides a structured research record while respecting the availability, privacy, and publication constraints associated with the underlying work.

---

## Final Perspective

The central research idea can be summarized as:

```text
Representation
      ↓
Structure
      ↓
Reasoning
      ↓
Query Coverage
      ↓
Explanation
```

The study examines this relationship empirically within a cardiovascular healthcare Question Answering benchmark and provides a comparative perspective on classical and graph-based knowledge-representation approaches.

---

<p align="center">
  <strong>
    Healthcare Knowledge Representation · Reasoning · Query Coverage · Explainability
  </strong>
</p>

<p align="center">
  <em>
    Understanding how the structure of knowledge shapes what an intelligent
    system can answer — and how those answers can be explained.
  </em>
</p>
