# Graph Report - .  (2026-05-04)

## Corpus Check
- Corpus is ~34,298 words - fits in a single context window. You may not need a graph.

## Summary
- 34 nodes · 36 edges · 6 communities detected
- Extraction: 75% EXTRACTED · 25% INFERRED · 0% AMBIGUOUS · INFERRED: 9 edges (avg confidence: 0.87)
- Token cost: 4,792 input · 7,482 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Banking Fraud Case Study|Banking Fraud Case Study]]
- [[_COMMUNITY_Advanced Chronological Analysis|Advanced Chronological Analysis]]
- [[_COMMUNITY_Practice Datasets|Practice Datasets]]
- [[_COMMUNITY_Aula 3 Teaching Materials|Aula 3 Teaching Materials]]
- [[_COMMUNITY_Topic Community 4|Topic Community 4]]
- [[_COMMUNITY_Topic Community 5|Topic Community 5]]

## God Nodes (most connected - your core abstractions)
1. `Projeto aulas-engenharia-prompt` - 7 edges
2. `Fraude Bancária - Caso Prático` - 7 edges
3. `Conteúdo Markdown da Prática da Aula 1` - 4 edges
4. `Aula 1 Markdown` - 4 edges
5. `Alucinação em IA` - 3 edges
6. `Rascunho da Aula 3` - 3 edges
7. `Estruturação de Informações` - 3 edges
8. `Mapeamento de Vínculos` - 3 edges
9. `TÓPICO 3: Reconstrução Cronológica de Fatos` - 3 edges
10. `Fluxo Markdown Primeiro` - 2 edges

## Surprising Connections (you probably didn't know these)
- `Caso: Fraude Bancária em Rede (51 dias)` --semantically_similar_to--> `Fraude Bancária - Caso Prático`  [INFERRED] [semantically similar]
  aula 4 - topico 3.md → 03_AULA3_EXERCICIOS.md
- `Fluxo Markdown Primeiro` --semantically_similar_to--> `Regra de HTML Único com CSS/JS Embutido`  [INFERRED] [semantically similar]
  README.md → aulas-md/GUIA-APOIO.md
- `Projeto aulas-engenharia-prompt` --references--> `Conteúdo Markdown da Prática da Aula 1`  [EXTRACTED]
  README.md → aulas-md/aula1-pratica.md
- `Projeto aulas-engenharia-prompt` --references--> `Rascunho da Aula 2`  [EXTRACTED]
  README.md → aulas-md/aula2.md
- `Projeto aulas-engenharia-prompt` --references--> `Rascunho da Aula 4`  [EXTRACTED]
  README.md → aulas-md/aula4.md

## Hyperedges (group relationships)
- **Pipeline Markdown para HTML Offline** — readme_project_overview, guia_apoio_editorial_guide, aula1_aula1_markdown, aula1_aula1_html_page [EXTRACTED 1.00]
- **Fluxo de Validação dos Prompts da Prática** — aula1_pratica_five_prompt_validation_plan, aula1_pratica_scope_control_prompt, aula1_pratica_critical_validation_prompt, aula1_pratica_copy_prompt_function [INFERRED 0.85]
- **Metodologia de Prompt Investigativo** — engenharia_de_prompt_investigativa, engenharia_de_contexto, prompt_investigativo, validacao_humana [INFERRED 0.85]
- **Aula 3 - Integrated Techniques** — aula3_exercicios_estruturacao, aula3_exercicios_mapeamento_vinculos, aula3_exercicios_timeline, aula3_exercicios_validacao_critica [EXTRACTED 1.00]
- **Aula 3 Course Materials** — aula3_slides_persona_estruturacao, aula3_slides_taxonomia_vinculos, aula3_html_slides_content, aula3_pratica_html_exercicio [EXTRACTED 1.00]
- **Case Study Progression** — aula3_exercicios_fraude_bancaria, aula4_caso_fraude_bancaria_rede, dados_topico3_55_eventos [INFERRED 0.85]

## Communities (6 total, 1 thin omitted)

### Community 0 - "Banking Fraud Case Study"
Cohesion: 0.25
Nodes (9): Fraude Bancária - Caso Prático, Reconstrução Cronológica, Validação Crítica, Aula 3 - HTML Presentation, Aula 3 Prática - Exercício Prático Intensivo, Caso: Fraude Bancária em Rede (51 dias), TÓPICO 3: Reconstrução Cronológica de Fatos, Lista de 55 Eventos Desordenados (+1 more)

### Community 1 - "Advanced Chronological Analysis"
Cohesion: 0.36
Nodes (8): Rascunho da Aula 2, Rascunho da Aula 3, Rascunho da Aula 4, Guia de Apoio Editorial e Técnico, Regra de HTML Único com CSS/JS Embutido, Fluxo Markdown Primeiro, HTML Offline Autônomo, Projeto aulas-engenharia-prompt

### Community 2 - "Practice Datasets"
Cohesion: 0.4
Nodes (6): Alucinação em IA, Aula 1 Markdown, Engenharia de Contexto, Engenharia de Prompt para Análises Investigativas, Validação Humana, Vieses dos Dados de Treinamento

### Community 3 - "Aula 3 Teaching Materials"
Cohesion: 0.33
Nodes (6): Estruturação de Informações, Mapeamento de Vínculos, Técnica: Persona + Estruturação + Restrição, Taxonomia de 7 Tipos de Vínculos, Dados de Exemplo - Tópico 1, Dados de Exemplo - 55 Frases com Vínculos

### Community 4 - "Topic Community 4"
Cohesion: 0.5
Nodes (4): Conteúdo Markdown da Prática da Aula 1, Prompt de Validação Crítica, Plano de Validação de 5 Prompts, Prompt de Controle de Escopo Temporal

## Knowledge Gaps
- **14 isolated node(s):** `HTML Offline Autônomo`, `AGENTS.md Graphify Instructions`, `Plano de Validação de 5 Prompts`, `Prompt de Controle de Escopo Temporal`, `Prompt de Validação Crítica` (+9 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Fraude Bancária - Caso Prático` connect `Banking Fraud Case Study` to `Aula 3 Teaching Materials`?**
  _High betweenness centrality (0.132) - this node is a cross-community bridge._
- **Why does `Projeto aulas-engenharia-prompt` connect `Advanced Chronological Analysis` to `Topic Community 4`?**
  _High betweenness centrality (0.083) - this node is a cross-community bridge._
- **Why does `Conteúdo Markdown da Prática da Aula 1` connect `Topic Community 4` to `Advanced Chronological Analysis`?**
  _High betweenness centrality (0.051) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `Alucinação em IA` (e.g. with `Engenharia de Contexto` and `Validação Humana`) actually correct?**
  _`Alucinação em IA` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `HTML Offline Autônomo`, `AGENTS.md Graphify Instructions`, `Plano de Validação de 5 Prompts` to the rest of the system?**
  _14 weakly-connected nodes found - possible documentation gaps or missing edges._