# Evaluation Framework

## Four evaluation dimensions

### Semantic expressiveness
Measures the ability to represent hierarchical, relational, and contextual medical knowledge.

### Query coverage
Measures how many of the five benchmark query types a paradigm can successfully answer.

### Explainability
Considers the transparency of the reasoning trace, including rule derivations, query results, or graph paths.

### Scalability
Considers extension to larger datasets and increasingly complex reasoning tasks.

## Reasoning depth

The paper treats reasoning depth as the number of intermediate steps required to derive a conclusion. For a knowledge graph `G = (V, E)`, the paper defines:

`RD(q) = min |p|,  p ∈ P(q)`

where `P(q)` is the set of valid reasoning paths supporting query `q` and `|p|` is the path length.

## Comparative interpretation

The published results describe a progression in representational capacity:

- Propositional and rule-based approaches are effective for simpler, explicitly encoded reasoning.
- Relational databases extend structured querying but provide limited semantic representation.
- Frame-based systems add structured relations but remain constrained for deeper multi-relational inference.
- OWL ontologies support subclass-oriented inference but remain comparatively static and context-bound.
- Knowledge Graphs provide the broadest benchmark coverage and support multi-hop, contextual, and path-based reasoning.

For the authoritative query-by-query comparison, consult Table 1 of the published paper.
