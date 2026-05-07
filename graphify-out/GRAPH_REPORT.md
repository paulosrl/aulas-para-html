# Graph Report - .  (2026-05-07)

## Corpus Check
- Corpus is ~32,485 words - fits in a single context window. You may not need a graph.

## Summary
- 29 nodes · 41 edges · 8 communities detected
- Extraction: 41% EXTRACTED · 59% INFERRED · 0% AMBIGUOUS · INFERRED: 24 edges (avg confidence: 0.9)
- Token cost: 28,000 input · 2,370 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Practical Case Studies & Validation|Practical Case Studies & Validation]]
- [[_COMMUNITY_Project Architecture & Deployment|Project Architecture & Deployment]]
- [[_COMMUNITY_Aula 1 Foundational Concepts|Aula 1 Foundational Concepts]]
- [[_COMMUNITY_Aula 2 Intermediate Techniques|Aula 2 Intermediate Techniques]]
- [[_COMMUNITY_Aula 3 Advanced Applications|Aula 3 Advanced Applications]]
- [[_COMMUNITY_Workshop & Pedagogical Framework|Workshop & Pedagogical Framework]]
- [[_COMMUNITY_Knowledge Graph Infrastructure|Knowledge Graph Infrastructure]]
- [[_COMMUNITY_Public Portal & Navigation|Public Portal & Navigation]]

## God Nodes (most connected - your core abstractions)
1. `aulas-engenharia-prompt Project` - 8 edges
2. `Aula 2: Advanced Prompt Engineering Techniques` - 8 edges
3. `Aula 3: Aplicação Prática em Análises Investigativas` - 8 edges
4. `Aula 1: Engenharia de Prompt para Análises Investigativas` - 7 edges
5. `Pedagogical Lesson Structure Pattern` - 5 edges
6. `Bank Fraud Case Study (Lesson 3 Practical)` - 4 edges
7. `Developer Guide for Claude Code` - 4 edges
8. `Chronological Reconstruction Technique (Topic 3)` - 3 edges
9. `Dark Mode Toggle Implementation` - 3 edges
10. `Copy to Clipboard Function` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Bank Fraud Case Study (Lesson 3 Practical)` --semantically_similar_to--> `Coordinated Fraud Network Case Study`  [INFERRED] [semantically similar]
  03_AULA3_EXERCICIOS.md → aula 4 - topico 3.md
- `aulas-engenharia-prompt Project` --references--> `Aula 2 Prática: Practical Exercises`  [EXTRACTED]
  README.md → html/aula2-pratica.html
- `aulas-engenharia-prompt Project` --references--> `Aula 3 Prática: Practical Exercises`  [EXTRACTED]
  README.md → html/aula3-pratica.html
- `Aula 1: Engenharia de Prompt para Análises Investigativas` --conceptually_related_to--> `Pedagogical Lesson Structure Pattern`  [INFERRED]
  html/aula1.html → CLAUDE.md
- `Aula 2: Advanced Prompt Engineering Techniques` --conceptually_related_to--> `Pedagogical Lesson Structure Pattern`  [INFERRED]
  html/aula2.html → CLAUDE.md

## Hyperedges (group relationships)
- **Lesson 3 Integrated Investigation Techniques** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula3_exercicios_validation [EXTRACTED 1.00]
- **Progressive Prompting Methodology** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula4_chain_of_thought, aula4_chronological_reconstruction [INFERRED 0.80]
- **Lesson Content Ecosystem** — aula1_html, aula2_html, aula2_pratica_html, aula3_html, aula3_pratica_html [EXTRACTED 1.00]
- **Shared Frontend Features Across Lessons** — aula1_html, aula2_html, aula3_html, dark_mode_toggle_feature, copy_to_clipboard_feature, css_variables_theme [INFERRED 0.95]
- **Example Data Resources for Lessons** — dados_topico1_md, dados_topico2_md, dados_topico3_md [INFERRED 0.85]

## Communities (8 total, 2 thin omitted)

### Community 0 - "Practical Case Studies & Validation"
Cohesion: 0.33
Nodes (7): Relationship Mapping Technique, Structured Data Extraction Technique, Critical Validation Task, Bank Fraud Case Study (Lesson 3 Practical), Chain-of-Thought Prompting with Certainty Marking, Chronological Reconstruction Technique (Topic 3), Coordinated Fraud Network Case Study

### Community 1 - "Project Architecture & Deployment"
Cohesion: 0.6
Nodes (5): Developer Guide for Claude Code, GitHub Pages Automatic Deployment, HTML as Source of Truth Design Principle, Offline-First Architecture Constraint, aulas-engenharia-prompt Project

### Community 2 - "Aula 1 Foundational Concepts"
Cohesion: 0.5
Nodes (4): Aula 1: Engenharia de Prompt para Análises Investigativas, Copy to Clipboard Function, Exemplo de Dados Tópico 1: Bank Fraud Investigation, Prompt ID Naming Convention

### Community 3 - "Aula 2 Intermediate Techniques"
Cohesion: 0.5
Nodes (4): Aula 2: Advanced Prompt Engineering Techniques, Aula 2 Prática: Practical Exercises, Exemplo de Dados Tópico 2: Multi-person Fraud Network, Dark Mode Toggle Implementation

### Community 4 - "Aula 3 Advanced Applications"
Cohesion: 0.5
Nodes (4): Aula 3: Aplicação Prática em Análises Investigativas, Aula 3 Prática: Practical Exercises, CSS Variables Theme System, Exemplo de Dados Tópico 3: Chronological Events Timeline

### Community 5 - "Workshop & Pedagogical Framework"
Cohesion: 0.67
Nodes (3): Pedagogical Lesson Structure Pattern, Inteligência Artificial aplicada ao Tribunal do Júri - MPPA Workshop, Workshop Tópico 1: AI in Jury Trial Analysis

## Knowledge Gaps
- **9 isolated node(s):** `Relationship Mapping Technique`, `Critical Validation Task`, `Graphify Knowledge Graph Documentation`, `Chain-of-Thought Prompting with Certainty Marking`, `Index HTML Landing Page` (+4 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `aulas-engenharia-prompt Project` connect `Project Architecture & Deployment` to `Aula 1 Foundational Concepts`, `Aula 2 Intermediate Techniques`, `Aula 3 Advanced Applications`?**
  _High betweenness centrality (0.132) - this node is a cross-community bridge._
- **Why does `Pedagogical Lesson Structure Pattern` connect `Workshop & Pedagogical Framework` to `Project Architecture & Deployment`, `Aula 1 Foundational Concepts`, `Aula 2 Intermediate Techniques`, `Aula 3 Advanced Applications`?**
  _High betweenness centrality (0.123) - this node is a cross-community bridge._
- **Why does `Aula 2: Advanced Prompt Engineering Techniques` connect `Aula 2 Intermediate Techniques` to `Project Architecture & Deployment`, `Aula 1 Foundational Concepts`, `Aula 3 Advanced Applications`, `Workshop & Pedagogical Framework`?**
  _High betweenness centrality (0.103) - this node is a cross-community bridge._
- **Are the 7 inferred relationships involving `Aula 2: Advanced Prompt Engineering Techniques` (e.g. with `Pedagogical Lesson Structure Pattern` and `Aula 2 Prática: Practical Exercises`) actually correct?**
  _`Aula 2: Advanced Prompt Engineering Techniques` has 7 INFERRED edges - model-reasoned connections that need verification._
- **Are the 7 inferred relationships involving `Aula 3: Aplicação Prática em Análises Investigativas` (e.g. with `Pedagogical Lesson Structure Pattern` and `Aula 3 Prática: Practical Exercises`) actually correct?**
  _`Aula 3: Aplicação Prática em Análises Investigativas` has 7 INFERRED edges - model-reasoned connections that need verification._
- **Are the 6 inferred relationships involving `Aula 1: Engenharia de Prompt para Análises Investigativas` (e.g. with `Pedagogical Lesson Structure Pattern` and `Exemplo de Dados Tópico 1: Bank Fraud Investigation`) actually correct?**
  _`Aula 1: Engenharia de Prompt para Análises Investigativas` has 6 INFERRED edges - model-reasoned connections that need verification._
- **Are the 4 inferred relationships involving `Pedagogical Lesson Structure Pattern` (e.g. with `Aula 1: Engenharia de Prompt para Análises Investigativas` and `Aula 2: Advanced Prompt Engineering Techniques`) actually correct?**
  _`Pedagogical Lesson Structure Pattern` has 4 INFERRED edges - model-reasoned connections that need verification._