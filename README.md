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

## Table of Contents

- [Research Snapshot](#research-snapshot)
- [Overview](#overview)
- [Research Question](#research-question)
- [Motivation](#motivation)
- [What Was Compared?](#what-was-compared)
- [Evaluation Framework](#evaluation-framework)
- [Reasoning Depth](#reasoning-depth)
- [Research Pipeline](#research-pipeline)
- [Benchmark Design](#benchmark-design)
- [Progressive Query Complexity](#progressive-query-complexity)
- [Implementation](#implementation)
- [Comparative Results](#comparative-results)
- [Reasoning and Explainability](#reasoning-and-explainability)
- [Why Query Coverage Matters](#why-query-coverage-matters)
- [Research Contribution](#research-contribution)
- [Key Findings](#key-findings)
- [Research Significance](#research-significance)
- [Limitations and Scope](#limitations-and-scope)
- [Future Research Directions](#future-research-directions)
- [Data and Reproducibility](#data-and-reproducibility)
- [Repository Guide](#repository-guide)
- [Repository Structure](#repository-structure)
- [Publication](#publication)
- [Citation](#citation)
- [Research Links](#research-links)
- [Repository Philosophy](#repository-philosophy)

---

## Research Snapshot

| | |
|---|---|
| **Research Area** | Knowledge Representation & Reasoning |
| **Application Domain** | Healthcare Question Answering |
| **Benchmark** | 47 curated cardiovascular patient records |
| **Benchmark Queries** | 5 progressively complex clinical queries |
| **KR Paradigms** | 7 representation approaches |
| **Evaluation Dimensions** | Semantic expressiveness · Query coverage · Explainability · Scalability |
| **Core Analytical Measure** | Reasoning depth |
| **Implementation** | Python · SQLite · JSON · RDF · OWL · RDFLib · OWL-RL · SPARQL |
| **Publication Venue** | Springer |
| **Publication Year** | 2026 |
| **Repository Role** | Research companion and methodological record |

---

## Overview

Healthcare Question Answering Systems (QAS) require more than retrieving isolated facts. Clinical questions may involve logical conditions, quantified statements, relationships among patient attributes, interacting comorbidities, treatment guidance, and contextual information.

This research investigates how the choice of **Knowledge Representation (KR)** paradigm influences the reasoning capability of healthcare expert systems and their ability to answer increasingly complex questions.

The study compares multiple KR paradigms under a common evaluation framework:

**Propositional Logic · First-Order Predicate Logic · Rule-Based Systems · Relational Databases · Frame-Based Models · Ontologies · Knowledge Graphs**

A curated cardiovascular benchmark containing **47 patient records** was used together with **five benchmark clinical queries (Q1–Q5)** designed to increase progressively in reasoning complexity.

The work was published in the proceedings of the **2026 Computing Conference** by Springer.

### Publication

**Tripathi, Atul Kumar; Thakre, Puja Minodji; Chatterjee, Niladri.**

*Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms*

*Intelligent Computing: Proceedings of the 2026 Computing Conference, Volume 2*

Lecture Notes in Networks and Information Systems, Vol. 1950, pp. 38–54, Springer, 2026.

**DOI:** [10.1007/978-3-032-24807-7_4](https://doi.org/10.1007/978-3-032-24807-7_4)

---

## Research Question

> **How does the choice of knowledge representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

The study approaches this question by constructing a common evaluation setting in which different representation paradigms are exposed to the same domain knowledge and a sequence of increasingly complex clinical queries.

The emphasis is therefore not simply on storing healthcare information, but on examining the relationship between:

```text
Knowledge Representation
          ↓
Encoded Relationships
          ↓
Reasoning Capability
          ↓
Query Coverage
          ↓
Explainability
```

---

## Motivation

Knowledge representation is a fundamental component of intelligent systems.

Different representations provide different ways of expressing:

- facts
- relationships
- logical constraints
- hierarchies
- contextual information
- inferential connections

A representation that is sufficient for a simple Boolean question may not naturally support a query involving multiple entities, several interacting relationships, or information that must be connected with external context.

The research therefore explores the **expressive and reasoning boundaries** of different KR paradigms using a progressively more demanding benchmark.

The broader motivation is to understand how representational structure affects the types of reasoning an intelligent system can perform.

---

## What Was Compared?

The study considers seven knowledge-representation paradigms.

| Paradigm | Representation Principle | Role in the Study |
|---|---|---|
| **Propositional Logic** | Atomic propositions and logical connectives | Simple Boolean reasoning |
| **First-Order Predicate Logic (FOPL)** | Predicates, variables, relations, and quantification | Relational and quantified reasoning |
| **Rule-Based Systems** | Explicit IF–THEN rules and inference | Structured rule-driven reasoning |
| **Relational Databases** | Tabular representation accessed through SQL | Structured relational querying |
| **Frame-Based Models** | Slot–filler representation of entities | Structured entity and attribute reasoning |
| **Ontologies** | Concepts, hierarchies, constraints, and semantics | Semantic and subclass-based inference |
| **Knowledge Graphs** | Entities and relations represented as connected graph structures | Multi-hop and contextual reasoning |

A common cardiovascular schema was used across the implementations to support a more consistent comparative evaluation.

---

## Evaluation Framework

The study evaluates the representation paradigms across four major dimensions.

| Dimension | What it examines |
|---|---|
| **Semantic Expressiveness** | Ability to represent hierarchical, relational, and contextual knowledge |
| **Query Coverage** | Number and type of benchmark queries that can be successfully answered |
| **Explainability** | Transparency of reasoning and availability of interpretable traces |
| **Scalability** | Ability to accommodate larger datasets and increasingly complex reasoning tasks |

### Semantic Expressiveness

Semantic expressiveness concerns the ability of a representation to capture increasingly rich forms of medical knowledge, including relationships, hierarchical concepts, and contextual constraints.

For example, a query involving age thresholds, hypertension, and cardiovascular risk may require more than the storage of isolated attribute values.

---

### Query Coverage

Query coverage measures whether a representation paradigm can successfully answer a given benchmark query.

The benchmark contains five queries:

```text
Q1 → Boolean
Q2 → Universal / Quantified
Q3 → Relational
Q4 → Multi-relational
Q5 → Contextual
```

The measure therefore captures the practical relationship between representation capability and query complexity.

---

### Explainability

Explainability concerns how transparently a system can show why a particular answer was obtained.

Depending on the representation, an explanation may take the form of:

- an explicit rule trace
- a patient list obtained from an SQL query
- a slot-based traversal
- inferred semantic triples
- a graph path connecting entities and relations

---

### Scalability

Scalability concerns the ability to extend a representation toward larger datasets and increasingly complex reasoning tasks.

The paper discusses scalability as an important consideration, while the main published comparative results focus on **query coverage, reasoning depth, and explainability**.

---

## Reasoning Depth

Reasoning depth measures the number of inferential steps required to derive an answer from available facts.

For symbolic systems, reasoning depth can correspond to the minimal chain of rules required for a derivation.

For graph-based reasoning, the paper defines reasoning depth using the minimum valid inference-path length:

<p align="center">
  <strong><code>RD(q) = min<sub>p ∈ P(q)</sub> |p|</code></strong>
</p>

where:

- `P(q)` is the set of valid reasoning paths supporting query `q`
- `|p|` is the length of path `p`

For example:

```text
A → B → C → D
```

contains three relational steps and therefore has a path length of 3.

This provides a compact way of characterizing the inferential complexity of a query.

### Interpretation

```text
Low reasoning depth
        ↓
Direct or shallow inference

Higher reasoning depth
        ↓
Multiple connected inference steps
        ↓
Multi-hop reasoning
```

The paper uses reasoning depth as a conceptual and quantitative measure for comparing inferential complexity, particularly in graph-based reasoning.

---

## Research Pipeline

<p align="center">
  <img src="research-pipeline.svg" alt="Research Pipeline" width="900">
</p>

The research pipeline consists conceptually of:

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

The cardiovascular knowledge was aligned across the different representations so that the comparison focused on the representational and reasoning properties of the paradigms.

---

## Benchmark Design

The benchmark uses **47 curated cardiovascular patient records**.

The study formulates five benchmark queries specifically to stress increasingly complex forms of reasoning.

Rather than evaluating all systems against a single simple query, the benchmark was designed as a progression from explicit logical conditions toward contextual and multi-relational questions.

This creates a controlled framework for examining the expressive boundaries of different representation paradigms.

---

## Benchmark Queries

### Q1 — Boolean

> **“Is a patient at risk of heart disease if chest pain is present and smoking history is negative?”**

**Reasoning category:** Boolean reasoning

This query primarily requires combining explicit conditions.

---

### Q2 — Universal

> **“Are all patients over 60 years old with hypertension at elevated risk of cardiovascular disease?”**

**Reasoning category:** Universal / quantified reasoning

This query introduces a broader condition over a group of patients and requires reasoning beyond an individual Boolean fact.

---

### Q3 — Relational

> **“What are the cardiovascular risks for patients with both diabetes and obesity?”**

**Reasoning category:** Relational reasoning

This query requires relationships among multiple patient attributes.

---

### Q4 — Multi-relational

> **“Which treatment guidelines are applicable for diabetic patients with left ventricular hypertrophy and a history of atrial fibrillation?”**

**Reasoning category:** Multi-relational reasoning

This query requires connecting multiple clinical conditions with patient history and treatment guidance.

---

### Q5 — Contextual

> **“Suggest interventions for patients with comorbidities similar to those reported in recent literature.”**

**Reasoning category:** Contextual reasoning

This query extends beyond the directly encoded patient facts and requires integration of heterogeneous contextual knowledge.

---

## Progressive Query Complexity

The five queries were intentionally structured as:

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

This progression allows the study to investigate not only whether a system can answer a question, but also how representation capability changes as the reasoning requirements become more demanding.

---

## Implementation

Lightweight expert-system prototypes were implemented using open-source tools.

All implementations shared a common schema aligned with the cardiovascular knowledge domain.

| KR Paradigm | Implementation Approach |
|---|---|
| **Propositional Logic** | Python logical conditions |
| **First-Order Predicate Logic** | Relational-query simulation using SQLite |
| **Rule-Based Systems** | Python rule execution |
| **Relational Databases** | SQLite / SQL queries |
| **Frame-Based Models** | Slot–filler JSON structures |
| **Ontologies** | RDF / OWL using RDFLib and OWL-RL |
| **Knowledge Graphs** | RDF triple stores with SPARQL queries |

### Implementation Philosophy

The prototypes were intentionally lightweight.

The objective was not to create production-grade clinical systems, but to establish a common experimental environment in which the representational and reasoning capabilities of the different paradigms could be compared.

---

## Comparative Results

### Published Query-Coverage Results

The following reproduces the comparative coverage reported in the published paper.

| Paradigm | Q1 | Q2 | Q3 | Q4 | Q5 | Explainability | Reasoning Depth |
|---|:---:|:---:|:---:|:---:|:---:|---|:---:|
| **Propositional Logic** | ✓ | – | – | – | – | Rule-based trace | 1 |
| **Rule-Based Systems** | ✓ | ✓ | – | – | – | Rule-based trace with patient list | 1 |
| **Relational Database** | ✓ | ✓ | ✓ | – | – | Direct SQL query results | 1 |
| **Frames** | ✓ | ✓ | ✓ | – | – | Graph traversal with slot-based reasoning | 1–2 |
| **Ontology (OWL)** | ✓ | ✓ | ✓ | ✓ | – | Inferred triples via SPARQL | 1–2 |
| **Knowledge Graph** | ✓ | ✓ | ✓ | ✓ | ✓ | Path-based traces with multi-hop reasoning | 3 |

---

## Important Note on FOPL

The paper discusses **First-Order Predicate Logic (FOPL)** as one of the seven investigated KR paradigms.

However, the published comparative table contains **six rows** and does not provide a separate Q1–Q5 result row for FOPL.

This repository intentionally preserves the published result table rather than introducing an inferred or reconstructed FOPL result.

This distinction is important for reproducibility and scientific accuracy.

---

## Performance Across Queries

The published results show a clear progression in coverage as the query requirements become more complex.

### Propositional Logic

Propositional Logic supports the simplest Boolean benchmark query.

Its representation is comparatively direct but does not naturally capture richer relationships among entities.

### Rule-Based Systems

Rule-based systems extend the reasoning capability through explicitly encoded rules.

The published comparison reports coverage for Q1 and Q2.

### Relational Databases

Relational databases extend the analysis to structured relational queries.

They support Q1–Q3 in the published comparison but provide limited semantic and hierarchical reasoning.

### Frame-Based Models

Frame-based representations introduce structured entity descriptions through slot–filler representations.

They support Q1–Q3 in the published comparison but remain limited for more demanding multi-relational reasoning.

### Ontologies

Ontologies introduce formal semantics, concepts, hierarchies, and subclass-based inference.

The published comparison reports coverage through Q4.

### Knowledge Graphs

Knowledge Graphs achieved coverage across **all five benchmark queries Q1–Q5** in the published comparison.

The paper associates this with capabilities including:

- multi-hop reasoning
- contextual integration
- path-based explanation
- connections among heterogeneous entities and relations

---

## Reasoning and Explainability

An important aspect of the study is not only whether a system produces an answer, but also how that answer can be explained.

The published analysis distinguishes among several forms of reasoning trace.

| Representation | Example Explanation |
|---|---|
| **Propositional Logic** | Rule-based trace |
| **Rule-Based Systems** | Rules and derived patient lists |
| **Relational Database** | Direct SQL query results |
| **Frames** | Slot-based graph traversal |
| **Ontology** | Inferred semantic triples |
| **Knowledge Graph** | Path-based multi-hop reasoning |

Knowledge Graphs make reasoning paths explicit through connected nodes and relations.

This makes them particularly suitable for queries requiring several linked inference steps.

---

## Why Query Coverage Matters

A system may store information effectively yet still be unable to answer a particular class of question.

This study therefore treats **query coverage** as a central component of comparative analysis.

The benchmark progressively increases the reasoning requirement:

```text
Boolean
   ↓
Quantified
   ↓
Relational
   ↓
Multi-relational
   ↓
Contextual
```

This design makes it possible to identify the points where different representation paradigms become less capable of supporting the required reasoning.

---

## Research Contribution

This project was conducted as collaborative research by three researchers.

### Puja Minodji Thakre

Puja's work focused primarily on the **comparative and analytical aspects** of the study.

Her contribution included:

- comparative analysis of evaluation outcomes
- analysis of **query coverage across representation paradigms**
- interpretation of comparative findings
- review and refinement of the manuscript during revision stages

Her role therefore connects the computational evaluation with the comparative interpretation of the experimental results.

---

### Atul Kumar Tripathi

Atul contributed to:

- development of the comparative evaluation framework
- benchmark construction
- implementation-oriented components
- organization of the experimental comparison

---

### Niladri Chatterjee

Contributed:

- research supervision
- methodological guidance
- academic direction

> **Contribution note:** These descriptions summarize the collaborators' working roles. The published paper does not contain a formal CRediT-style author-contribution statement.

---

## Key Findings

Within the scope of the experimental benchmark, the study demonstrates several important patterns.

### 1. Query complexity affects representation capability

Different KR paradigms support different levels and types of reasoning.

The difference becomes increasingly visible as the queries move from Boolean conditions toward multi-relational and contextual reasoning.

### 2. Classical representations remain useful

Simpler paradigms provide effective mechanisms for explicitly structured reasoning tasks.

Their limitations become more apparent when queries require richer relationships or deeper inferential chains.

### 3. Knowledge Graphs achieved complete benchmark coverage

Knowledge Graphs successfully answered **Q1–Q5** in the published comparative evaluation.

### 4. Reasoning depth provides an additional analytical dimension

The study does not consider only whether a query can be answered.

It also considers the inferential distance involved in deriving an answer.

### 5. Explainability is closely related to representation

Different representation structures naturally produce different forms of reasoning trace.

Graph-based representations make multi-hop relationships explicit through connected paths.

### 6. Greater expressiveness comes with additional requirements

More expressive knowledge structures require additional modelling, construction, and verification effort.

The paper therefore emphasizes that representational richness should be considered together with computational and operational considerations.

---

## Research Significance

The broader significance of this research lies in the relationship between **representation and reasoning**.

The central conceptual chain is:

```text
How knowledge is represented
            ↓
What relationships can be encoded
            ↓
What reasoning can be performed
            ↓
Which questions can be answered
            ↓
How the answer can be explained
```

This makes the work relevant to research at the intersection of:

`Knowledge Representation`

`Knowledge Graphs`

`Healthcare Question Answering`

`Semantic Web`

`Explainable AI`

`Machine Learning`

`Structured Knowledge`

`Intelligent Information Systems`

---

## Discussion Perspective

The results suggest a progression from simpler, explicitly encoded representations toward graph-based structures capable of connecting heterogeneous information.

The study therefore places particular emphasis on Knowledge Graphs because of their combination of:

- semantic relationships
- graph connectivity
- multi-hop inference
- contextual integration
- path-based explanations

At the same time, the research does not eliminate the usefulness of simpler representation paradigms.

Different representation mechanisms exhibit different trade-offs between expressive capability, interpretability, computational requirements, and modelling effort.

---

## Operational Considerations

Knowledge Graphs and related graph technologies can integrate:

- structured patient information
- semantic relationships
- domain concepts
- clinical guidelines
- external knowledge sources

The paper also notes that building a domain-specific Knowledge Graph remains resource-intensive because it requires activities such as:

- data preprocessing
- schema alignment
- entity–relation extraction
- knowledge construction
- validation

This creates an important research trade-off between representational richness and construction complexity.

---

## Limitations and Scope

The findings should be interpreted within the boundaries of the experimental setup.

### 1. Dataset Size

The benchmark contains **47 curated cardiovascular patient records**.

This relatively small benchmark limits the generalizability of the findings.

### 2. Simulated Logic Reasoning

Propositional and FOPL reasoning were simulated using Python conditionals and SQL-style relational queries rather than dedicated logic engines.

Therefore, the experimental implementations do not represent the full theoretical capabilities of those formalisms.

### 3. Manual Knowledge Construction

Subclass relationships in the ontology and Knowledge Graph were manually curated.

This introduces an additional source of modelling dependence.

### 4. Comparative Rather Than Clinical Evaluation

The benchmark was designed for a **comparative knowledge-representation study**.

It should not be interpreted as a clinical validation study or as evidence of deployment in real-world clinical decision-making.

### 5. Generalization

Broader evaluation on larger and more diverse clinical corpora would be required to assess how the observed patterns extend beyond the experimental benchmark.

---

## Future Research Directions

The limitations of the current study motivate several directions for further research.

### Larger-Scale Evaluation

Evaluate Knowledge Representation paradigms on larger clinical datasets and broader healthcare scenarios.

### Automated Ontology Alignment

Reduce dependence on manually curated semantic relationships through automated or semi-automated ontology alignment.

### Automated Knowledge Graph Construction

Develop more scalable pipelines for transforming structured and unstructured biomedical information into graph-based knowledge.

### Hybrid Neuro-Symbolic Reasoning

Combine symbolic Knowledge Graph reasoning with machine-learning or language-model-based methods.

### Explainable Reasoning Frameworks

Develop standardized approaches for validating reasoning traces and inference paths.

### Time-Critical Knowledge-Based Systems

The broader research direction suggested by the paper is toward systems that can select appropriate knowledge structures and reasoning mechanisms according to the complexity and temporal demands of a query.

---

## Data and Reproducibility

This repository is designed as a **research companion and methodological record**.

### Included

The repository documents:

- the research question
- benchmark structure
- exact benchmark queries
- KR paradigms
- implementation approaches
- evaluation dimensions
- reasoning-depth definition
- published comparative results
- research contribution
- methodological limitations
- publication metadata

### Not Included

The repository does not contain:

- patient-level records
- personally identifiable information
- restricted clinical material
- the publisher-controlled Springer PDF

The repository therefore provides a transparent description of the research framework without redistributing restricted or unavailable research material.

### Reproducibility Scope

The repository should be interpreted as a **methodological and analytical companion** rather than a claim of complete end-to-end computational reproducibility.

This distinction is intentional and reflects the limitations described in the published work.

---

## Repository Guide

| File / Resource | Purpose |
|---|---|
| [`README.md`](README.md) | Complete overview of the research, methodology, benchmark, results, and scope |
| [`docs/METHODOLOGY.md`](docs/METHODOLOGY.md) | Detailed research methodology and benchmark design |
| [`docs/EVALUATION_FRAMEWORK.md`](docs/EVALUATION_FRAMEWORK.md) | Evaluation dimensions, query coverage, reasoning depth, and explainability |
| [`docs/CONTRIBUTIONS.md`](docs/CONTRIBUTIONS.md) | Collaborative research contribution perspective |
| [`docs/REPRODUCIBILITY.md`](docs/REPRODUCIBILITY.md) | Data availability, implementation scope, and reproducibility considerations |
| [`analysis/EVALUATION_SCHEMA.csv`](analysis/EVALUATION_SCHEMA.csv) | Structured representation of the published comparative evaluation |
| [`research-pipeline.svg`](research-pipeline.svg) | Visual representation of the research workflow |
| [`CITATION.cff`](CITATION.cff) | Machine-readable citation metadata |
| [`NOTICE.md`](NOTICE.md) | Repository and publication/data-use notice |

---

## Repository Structure

```text
healthcare-kb-representation-evaluation/
│
├── README.md
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

If you use, extend, or reference the research, please cite the published article:

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

[![DOI](https://img.shields.io/badge/Springer-DOI-2E5AAC?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)

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
`Healthcare AI`  
`Healthcare Question Answering`  
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

This repository follows three principles:

### Scientific Accuracy

The repository describes the published research faithfully and avoids introducing experimental results that are not reported in the paper.

### Research Transparency

Methodological choices, benchmark design, contribution boundaries, and limitations are documented explicitly.

### Reproducibility with Appropriate Scope

The repository provides the research framework and analytical structure while respecting the availability, privacy, and publication constraints associated with the underlying work.

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

The study examines this chain empirically within a cardiovascular healthcare question-answering benchmark and provides a comparative perspective on classical and graph-based knowledge representation.

---

<p align="center">
  <strong>Healthcare Knowledge Representation · Reasoning · Query Coverage · Explainability</strong>
</p>

<p align="center">
  <em>
    From representation to reasoning: understanding how the structure of knowledge
    shapes what an intelligent system can answer and explain.
  </em>
</p>
