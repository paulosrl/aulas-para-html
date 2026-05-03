# Graph Report - .  (2026-05-03)

## Corpus Check
- Corpus is ~16,283 words - fits in a single context window. You may not need a graph.

## Summary
- 27 nodes · 38 edges · 5 communities detected
- Extraction: 82% EXTRACTED · 16% INFERRED · 3% AMBIGUOUS · INFERRED: 6 edges (avg confidence: 0.9)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Rascunho Guia Apoio|Rascunho Guia Apoio]]
- [[_COMMUNITY_Shot Prompting Alucinação|Shot Prompting Alucinação]]
- [[_COMMUNITY_Engenharia Markdown Contexto|Engenharia Markdown Contexto]]
- [[_COMMUNITY_Prompt Validação Conteúdo|Prompt Validação Conteúdo]]
- [[_COMMUNITY_Agents Graphify Instructions|Agents Graphify Instructions]]

## God Nodes (most connected - your core abstractions)
1. `Aula 2 HTML` - 8 edges
2. `Projeto aulas-engenharia-prompt` - 7 edges
3. `Prática Aula 1 HTML` - 7 edges
4. `Aula 1 Markdown` - 6 edges
5. `Conteúdo Markdown da Prática da Aula 1` - 4 edges
6. `Aula 1 HTML` - 4 edges
7. `Alucinação em IA` - 4 edges
8. `Rascunho da Aula 3` - 3 edges
9. `Course Index Page` - 3 edges
10. `Zero-shot Prompting` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Fluxo Markdown Primeiro` --semantically_similar_to--> `Regra de HTML Único com CSS/JS Embutido`  [INFERRED] [semantically similar]
  README.md → aulas-md/GUIA-APOIO.md
- `Aula 1 Markdown` --semantically_similar_to--> `Aula 1 HTML`  [INFERRED] [semantically similar]
  aulas-md/aula1.md → html/aula1.html
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

## Communities (5 total, 1 thin omitted)

### Community 0 - "Rascunho Guia Apoio"
Cohesion: 0.36
Nodes (8): Rascunho da Aula 2, Rascunho da Aula 3, Rascunho da Aula 4, Guia de Apoio Editorial e Técnico, Regra de HTML Único com CSS/JS Embutido, Fluxo Markdown Primeiro, HTML Offline Autônomo, Projeto aulas-engenharia-prompt

### Community 1 - "Shot Prompting Alucinação"
Cohesion: 0.43
Nodes (8): Alucinação em IA, Prática Aula 1 HTML, Aula 2 HTML, Few-shot Prompting, Prompt Investigativo Estruturado, Sigilo e Anonimização de Dados, Validação Humana, Zero-shot Prompting

### Community 2 - "Engenharia Markdown Contexto"
Cohesion: 0.4
Nodes (6): Aula 1 HTML, Aula 1 Markdown, Engenharia de Contexto, Engenharia de Prompt para Análises Investigativas, Course Index Page, Vieses dos Dados de Treinamento

### Community 3 - "Prompt Validação Conteúdo"
Cohesion: 0.5
Nodes (4): Conteúdo Markdown da Prática da Aula 1, Prompt de Validação Crítica, Plano de Validação de 5 Prompts, Prompt de Controle de Escopo Temporal

## Ambiguous Edges - Review These
- `Prática Aula 1 HTML` → `Prompt Investigativo Estruturado`  [AMBIGUOUS]
  html/aula1-pratica-html.html · relation: conceptually_related_to

## Knowledge Gaps
- **7 isolated node(s):** `HTML Offline Autônomo`, `Plano de Validação de 5 Prompts`, `Prompt de Controle de Escopo Temporal`, `Prompt de Validação Crítica`, `AGENTS.md Graphify Instructions` (+2 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `Prática Aula 1 HTML` and `Prompt Investigativo Estruturado`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **Why does `Projeto aulas-engenharia-prompt` connect `Rascunho Guia Apoio` to `Prompt Validação Conteúdo`?**
  _High betweenness centrality (0.135) - this node is a cross-community bridge._
- **Why does `Aula 2 HTML` connect `Shot Prompting Alucinação` to `Engenharia Markdown Contexto`?**
  _High betweenness centrality (0.097) - this node is a cross-community bridge._
- **Why does `Conteúdo Markdown da Prática da Aula 1` connect `Prompt Validação Conteúdo` to `Rascunho Guia Apoio`?**
  _High betweenness centrality (0.083) - this node is a cross-community bridge._
- **What connects `HTML Offline Autônomo`, `Plano de Validação de 5 Prompts`, `Prompt de Controle de Escopo Temporal` to the rest of the system?**
  _7 weakly-connected nodes found - possible documentation gaps or missing edges._