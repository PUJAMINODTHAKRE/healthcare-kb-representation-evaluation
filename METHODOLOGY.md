# Methodology

## Study design

The study compares seven knowledge-representation paradigms for healthcare question answering within a shared evaluation framework. The objective is to examine how representational choices affect expressiveness, query coverage, reasoning depth, explainability, and scalability.

## Clinical benchmark

The published work uses 47 anonymized cardiovascular patient records and five benchmark clinical queries. The queries increase in complexity from Boolean reasoning through universal, relational, multi-relational, and contextual reasoning.

## Representation paradigms

1. Propositional Logic
2. First-Order Predicate Logic (FOPL)
3. Rule-Based Systems
4. Relational Databases
5. Frame-Based Systems
6. Ontologies (OWL)
7. Knowledge Graphs (KGs)

## Implementation mapping

| Paradigm | Implementation reported in paper |
|---|---|
| Propositional Logic | Python |
| Rule-Based Systems | Python |
| First-Order Predicate Logic | Simulated through relational queries in SQLite |
| Relational Database | SQL-style relational querying |
| Frame-Based Systems | Slot–filler JSON structures |
| Ontologies | RDF/OWL with RDFLib and OWL-RL |
| Knowledge Graphs | RDF triple stores with SPARQL |

The implementations share a common cardiovascular knowledge schema to reduce representational bias.

## Evaluation sequence

The benchmark is intentionally progressive:

`Boolean → Universal → Relational → Multi-relational → Contextual`

The design makes it possible to observe where each representation remains effective and where additional semantic or relational structure becomes necessary.
