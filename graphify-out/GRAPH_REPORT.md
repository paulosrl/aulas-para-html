# Graph Report - .  (2026-05-05)

## Corpus Check
- Corpus is ~27,017 words - fits in a single context window. You may not need a graph.

## Summary
- 14 nodes · 11 edges · 6 communities detected
- Extraction: 45% EXTRACTED · 55% INFERRED · 0% AMBIGUOUS · INFERRED: 6 edges (avg confidence: 0.77)
- Token cost: 15,000 input · 28,667 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Advanced Investigation Techniques|Advanced Investigation Techniques]]
- [[_COMMUNITY_HTML & Publication Infrastructure|HTML & Publication Infrastructure]]
- [[_COMMUNITY_Lesson 3 Practical Exercises|Lesson 3 Practical Exercises]]
- [[_COMMUNITY_Architectural Principles|Architectural Principles]]
- [[_COMMUNITY_Data Extraction & Teaching Methods|Data Extraction & Teaching Methods]]
- [[_COMMUNITY_Documentation & Tools|Documentation & Tools]]

## God Nodes (most connected - your core abstractions)
1. `Bank Fraud Case Study (Lesson 3 Practical)` - 4 edges
2. `Structured Data Extraction Technique` - 3 edges
3. `Chronological Reconstruction Technique (Topic 3)` - 3 edges
4. `Index HTML Landing Page` - 2 edges
5. `Coordinated Fraud Network Case Study` - 2 edges
6. `HTML as Source of Truth Principle` - 1 edges
7. `Offline-First Architecture` - 1 edges
8. `Structured Didactic Pattern for Lessons` - 1 edges
9. `Relationship Mapping Technique` - 1 edges
10. `Chain-of-Thought Prompting with Certainty Marking` - 1 edges

## Surprising Connections (you probably didn't know these)
- `Bank Fraud Case Study (Lesson 3 Practical)` --semantically_similar_to--> `Coordinated Fraud Network Case Study`  [INFERRED] [semantically similar]
  03_AULA3_EXERCICIOS.md → aula 4 - topico 3.md
- `Structured Data Extraction Technique` --conceptually_related_to--> `Chronological Reconstruction Technique (Topic 3)`  [INFERRED]
  03_AULA3_EXERCICIOS.md → aula 4 - topico 3.md
- `Structured Didactic Pattern for Lessons` --rationale_for--> `Structured Data Extraction Technique`  [INFERRED]
  README.md → 03_AULA3_EXERCICIOS.md
- `GitHub Pages Publication Workflow` --rationale_for--> `Index HTML Landing Page`  [INFERRED]
  README.md → index.html
- `Prompt Template and Structural Pattern` --rationale_for--> `Index HTML Landing Page`  [INFERRED]
  README.md → index.html

## Hyperedges (group relationships)
- **Lesson 3 Integrated Investigation Techniques** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula3_exercicios_validation [EXTRACTED 1.00]
- **Progressive Prompting Methodology** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula4_chain_of_thought, aula4_chronological_reconstruction [INFERRED 0.80]

## Communities (6 total, 3 thin omitted)

### Community 0 - "Advanced Investigation Techniques"
Cohesion: 0.67
Nodes (3): Chain-of-Thought Prompting with Certainty Marking, Chronological Reconstruction Technique (Topic 3), Coordinated Fraud Network Case Study

### Community 1 - "HTML & Publication Infrastructure"
Cohesion: 0.67
Nodes (3): Index HTML Landing Page, GitHub Pages Publication Workflow, Prompt Template and Structural Pattern

### Community 2 - "Lesson 3 Practical Exercises"
Cohesion: 0.67
Nodes (3): Relationship Mapping Technique, Critical Validation Task, Bank Fraud Case Study (Lesson 3 Practical)

## Knowledge Gaps
- **9 isolated node(s):** `HTML as Source of Truth Principle`, `Offline-First Architecture`, `Structured Didactic Pattern for Lessons`, `Relationship Mapping Technique`, `Chain-of-Thought Prompting with Certainty Marking` (+4 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **3 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Bank Fraud Case Study (Lesson 3 Practical)` connect `Lesson 3 Practical Exercises` to `Advanced Investigation Techniques`, `Data Extraction & Teaching Methods`?**
  _High betweenness centrality (0.154) - this node is a cross-community bridge._
- **Why does `Structured Data Extraction Technique` connect `Data Extraction & Teaching Methods` to `Advanced Investigation Techniques`, `Lesson 3 Practical Exercises`?**
  _High betweenness centrality (0.115) - this node is a cross-community bridge._
- **Why does `Chronological Reconstruction Technique (Topic 3)` connect `Advanced Investigation Techniques` to `Data Extraction & Teaching Methods`?**
  _High betweenness centrality (0.090) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `Structured Data Extraction Technique` (e.g. with `Structured Didactic Pattern for Lessons` and `Chronological Reconstruction Technique (Topic 3)`) actually correct?**
  _`Structured Data Extraction Technique` has 2 INFERRED edges - model-reasoned connections that need verification._
- **Are the 2 inferred relationships involving `Index HTML Landing Page` (e.g. with `GitHub Pages Publication Workflow` and `Prompt Template and Structural Pattern`) actually correct?**
  _`Index HTML Landing Page` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `HTML as Source of Truth Principle`, `Offline-First Architecture`, `Structured Didactic Pattern for Lessons` to the rest of the system?**
  _9 weakly-connected nodes found - possible documentation gaps or missing edges._