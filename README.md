# Healthcare Knowledge Representation: Comparative Evaluation

[![Published](https://img.shields.io/badge/Published-Springer%202026-2E5AAC?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)
[![DOI](https://img.shields.io/badge/DOI-10.1007%2F978--3--032--24807--7__4-2E8B57?style=flat-square)](https://doi.org/10.1007/978-3-032-24807-7_4)
[![Domain](https://img.shields.io/badge/Domain-Healthcare%20AI-6C757D?style=flat-square)](#)
[![Focus](https://img.shields.io/badge/Focus-Knowledge%20Representation%20%7C%20Knowledge%20Graphs-D97706?style=flat-square)](#)

> **Research companion to a comparative empirical study of knowledge-representation paradigms for healthcare question answering.**

<p align="center">
  <img src="research-pipeline.svg" alt="Research Pipeline" width="900">
</p>

<p align="center">
  <em>
  From representation to reasoning: evaluating how the structure of knowledge
  shapes the questions an intelligent system can answer.
  </em>
</p>

---

## Research Snapshot

| | |
|---|---|
| **Domain** | Healthcare Question Answering |
| **Research Theme** | Knowledge Representation and Reasoning |
| **Benchmark** | 47 curated cardiovascular patient records |
| **Clinical Queries** | 5 progressively complex benchmark queries |
| **KR Paradigms** | 7 representation approaches |
| **Evaluation Dimensions** | Semantic expressiveness · Query coverage · Explainability · Scalability |
| **Core Reasoning Measure** | Reasoning depth |
| **Publication** | Springer, 2026 |

---

## Overview

Healthcare Question Answering Systems (QAS) require more than the retrieval of isolated facts. Clinical questions may involve logical conditions, quantified statements, relationships among patient attributes, interacting comorbidities, treatment guidance, and contextual information.

This research investigates how the choice of **Knowledge Representation (KR)** paradigm influences the reasoning capability and answer quality of healthcare expert systems.

The study examines seven representation paradigms within a common evaluation framework:

**Propositional Logic · First-Order Predicate Logic · Rule-Based Systems · Relational Databases · Frame-Based Models · Ontologies · Knowledge Graphs**

The comparison is grounded in a curated cardiovascular benchmark containing **47 patient records** and **five clinical queries (Q1–Q5)** designed to progress from simple Boolean reasoning toward quantified, relational, multi-relational, and contextual reasoning.

The research was published in the proceedings of the **2026 Computing Conference** by Springer.

### Publication

**Tripathi, Atul Kumar; Thakre, Puja Minodji; Chatterjee, Niladri.**

*Knowledge Representation for Healthcare Systems: A Comparative Analysis of Performance of Different Representation Paradigms*

*Intelligent Computing: Proceedings of the 2026 Computing Conference, Volume 2*

Lecture Notes in Networks and Information Systems, Vol. 1950, pp. 38–54, Springer, 2026.

**DOI:** [10.1007/978-3-032-24807-7_4](https://doi.org/10.1007/978-3-032-24807-7_4)

---

## Research Question

> **How does the choice of knowledge representation technique influence the reasoning performance and answer quality of expert systems in the healthcare domain?**

The study addresses this question by evaluating multiple knowledge-representation paradigms under a common representation framework and progressively more demanding clinical queries.

---

## Research Perspective

The central idea of the study is that **the way knowledge is represented influences the kinds of reasoning an intelligent system can perform**.

Rather than evaluating a representation technique on a single task, the study uses a sequence of queries with increasing reasoning complexity.

This creates a progression from:

**Boolean → Quantified → Relational → Multi-relational → Contextual**

The framework therefore focuses on the relationship between:

**Representation → Query Complexity → Reasoning Capability → Explainability**

---

## What Was Compared?

The study evaluates the following knowledge-representation paradigms.

| Paradigm | Representation idea |
|---|---|
| **Propositional Logic** | Atomic propositions and logical conditions |
| **First-Order Predicate Logic (FOPL)** | Variables, predicates, relationships, and quantification |
| **Rule-Based Systems** | Explicit IF–THEN rules and inference |
| **Relational Databases** | Structured tabular representation queried through SQL |
| **Frame-Based Models** | Entities represented using slot–filler structures |
| **Ontologies** | Formal concepts, hierarchies, and semantic relationships |
| **Knowledge Graphs** | Interconnected entities and relations represented as a graph |

A common cardiovascular knowledge schema was used to support the comparative analysis.

---

## Evaluation Framework

The study considers four major evaluation dimensions:

| Dimension | What it examines |
|---|---|
| **Semantic Expressiveness** | Ability to represent hierarchical, relational, and contextual knowledge |
| **Query Coverage** | Which benchmark queries can be answered successfully |
| **Explainability** | Transparency of the reasoning process and availability of interpretable traces |
| **Scalability** | Ability to accommodate larger datasets and increasingly complex reasoning tasks |

### Reasoning Depth

Reasoning depth measures the number of inferential steps required to derive an answer.

For graph-based reasoning, the paper defines reasoning depth as the minimum path length among all valid reasoning paths supporting a query:

<p align="center">
  <strong><code>RD(q) = min<sub>p ∈ P(q)</sub> |p|</code></strong>
</p>

where:

- `P(q)` denotes the set of valid reasoning paths supporting query `q`
- `|p|` denotes the length of reasoning path `p`

A direct fact retrieval therefore corresponds to shallow reasoning, while an answer requiring several connected inferential steps corresponds to deeper reasoning.

For example, if a valid reasoning chain follows:

```text
A → B → C → D
