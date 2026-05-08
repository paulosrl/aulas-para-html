# Graph Report - aulas-engenharia-prompt  (2026-05-07)

## Corpus Check
- 1 files · ~39,205 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 53 nodes · 106 edges · 10 communities detected
- Extraction: 77% EXTRACTED · 23% INFERRED · 0% AMBIGUOUS · INFERRED: 24 edges (avg confidence: 0.9)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `d43edf1e`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- [[_COMMUNITY_Community 0|Community 0]]
- [[_COMMUNITY_Community 1|Community 1]]
- [[_COMMUNITY_Community 2|Community 2]]
- [[_COMMUNITY_Community 3|Community 3]]
- [[_COMMUNITY_Community 4|Community 4]]
- [[_COMMUNITY_Community 5|Community 5]]
- [[_COMMUNITY_Community 6|Community 6]]
- [[_COMMUNITY_Community 7|Community 7]]
- [[_COMMUNITY_Community 8|Community 8]]
- [[_COMMUNITY_Community 9|Community 9]]

## God Nodes (most connected - your core abstractions)
1. `parse_markdown()` - 11 edges
2. `main()` - 11 edges
3. `clean_md_title()` - 10 edges
4. `aulas-engenharia-prompt Project` - 8 edges
5. `Aula 2: Advanced Prompt Engineering Techniques` - 8 edges
6. `Aula 3: Aplicação Prática em Análises Investigativas` - 8 edges
7. `strip_leading_number()` - 7 edges
8. `pick_icon()` - 7 edges
9. `render_cards()` - 7 edges
10. `Aula 1: Engenharia de Prompt para Análises Investigativas` - 7 edges

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

## Communities (10 total, 2 thin omitted)

### Community 0 - "Community 0"
Cohesion: 0.35
Nodes (9): apply_global_page_rules(), esc(), inline_md(), main(), normalize_data_uri(), parse_args(), render_menu_from_labels(), render_topics_menu() (+1 more)

### Community 1 - "Community 1"
Cohesion: 0.46
Nodes (8): assign_unique_icons(), clean_md_title(), parse_menu_md(), pick_icon(), pick_item_icon(), render_cards(), render_menu(), strip_leading_number()

### Community 2 - "Community 2"
Cohesion: 0.32
Nodes (8): Aula 1: Engenharia de Prompt para Análises Investigativas, Aula 2: Advanced Prompt Engineering Techniques, Aula 2 Prática: Practical Exercises, Copy to Clipboard Function, CSS Variables Theme System, Exemplo de Dados Tópico 1: Bank Fraud Investigation, Exemplo de Dados Tópico 2: Multi-person Fraud Network, Prompt ID Naming Convention

### Community 3 - "Community 3"
Cohesion: 0.33
Nodes (7): Relationship Mapping Technique, Structured Data Extraction Technique, Critical Validation Task, Bank Fraud Case Study (Lesson 3 Practical), Chain-of-Thought Prompting with Certainty Marking, Chronological Reconstruction Technique (Topic 3), Coordinated Fraud Network Case Study

### Community 4 - "Community 4"
Cohesion: 0.4
Nodes (5): Card, classify_critical_paragraph(), is_strategic_paragraph(), parse_markdown(), split_key_value_item()

### Community 5 - "Community 5"
Cohesion: 0.6
Nodes (5): Developer Guide for Claude Code, GitHub Pages Automatic Deployment, HTML as Source of Truth Design Principle, Offline-First Architecture Constraint, aulas-engenharia-prompt Project

### Community 6 - "Community 6"
Cohesion: 0.5
Nodes (4): Aula 3: Aplicação Prática em Análises Investigativas, Aula 3 Prática: Practical Exercises, Exemplo de Dados Tópico 3: Chronological Events Timeline, Dark Mode Toggle Implementation

### Community 7 - "Community 7"
Cohesion: 0.67
Nodes (3): Pedagogical Lesson Structure Pattern, Inteligência Artificial aplicada ao Tribunal do Júri - MPPA Workshop, Workshop Tópico 1: AI in Jury Trial Analysis

## Knowledge Gaps
- **9 isolated node(s):** `Relationship Mapping Technique`, `Critical Validation Task`, `Graphify Knowledge Graph Documentation`, `Chain-of-Thought Prompting with Certainty Marking`, `Index HTML Landing Page` (+4 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `aulas-engenharia-prompt Project` connect `Community 5` to `Community 2`, `Community 6`?**
  _High betweenness centrality (0.038) - this node is a cross-community bridge._
- **Why does `Pedagogical Lesson Structure Pattern` connect `Community 7` to `Community 2`, `Community 5`, `Community 6`?**
  _High betweenness centrality (0.035) - this node is a cross-community bridge._
- **Why does `Aula 2: Advanced Prompt Engineering Techniques` connect `Community 2` to `Community 5`, `Community 6`, `Community 7`?**
  _High betweenness centrality (0.029) - this node is a cross-community bridge._
- **Are the 7 inferred relationships involving `Aula 2: Advanced Prompt Engineering Techniques` (e.g. with `Pedagogical Lesson Structure Pattern` and `Aula 2 Prática: Practical Exercises`) actually correct?**
  _`Aula 2: Advanced Prompt Engineering Techniques` has 7 INFERRED edges - model-reasoned connections that need verification._
- **What connects `Relationship Mapping Technique`, `Critical Validation Task`, `Graphify Knowledge Graph Documentation` to the rest of the system?**
  _9 weakly-connected nodes found - possible documentation gaps or missing edges._