# Graph Report - .  (2026-05-03)

## Corpus Check
- Corpus is ~15,181 words - fits in a single context window. You may not need a graph.

## Summary
- 24 nodes · 31 edges · 4 communities detected
- Extraction: 84% EXTRACTED · 16% INFERRED · 0% AMBIGUOUS · INFERRED: 5 edges (avg confidence: 0.91)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Rascunho Guia Apoio|Rascunho Guia Apoio]]
- [[_COMMUNITY_Prompt Validação Limitações|Prompt Validação Limitações]]
- [[_COMMUNITY_Engenharia Shot Prompting|Engenharia Shot Prompting]]
- [[_COMMUNITY_Página Prática Função|Página Prática Função]]

## God Nodes (most connected - your core abstractions)
1. `Projeto aulas-engenharia-prompt` - 10 edges
2. `Conteúdo Markdown da Aula 1` - 6 edges
3. `Página HTML da Prática da Aula 1` - 5 edges
4. `Página HTML da Aula 1` - 4 edges
5. `Conteúdo Markdown da Prática da Aula 1` - 4 edges
6. `Rascunho da Aula 3` - 3 edges
7. `Página inicial do curso` - 2 edges
8. `Guia de Apoio Editorial e Técnico` - 2 edges
9. `Rascunho da Aula 2` - 2 edges
10. `Rascunho da Aula 4` - 2 edges

## Surprising Connections (you probably didn't know these)
- `Fluxo Markdown Primeiro` --semantically_similar_to--> `Regra de HTML Único com CSS/JS Embutido`  [INFERRED] [semantically similar]
  README.md → aulas-md/GUIA-APOIO.md
- `Projeto aulas-engenharia-prompt` --references--> `Conteúdo Markdown da Aula 1`  [EXTRACTED]
  README.md → aulas-md/aula1.md
- `Projeto aulas-engenharia-prompt` --references--> `Conteúdo Markdown da Prática da Aula 1`  [EXTRACTED]
  README.md → aulas-md/aula1-pratica.md
- `Projeto aulas-engenharia-prompt` --references--> `Rascunho da Aula 2`  [EXTRACTED]
  README.md → aulas-md/aula2.md
- `Projeto aulas-engenharia-prompt` --references--> `Rascunho da Aula 4`  [EXTRACTED]
  README.md → aulas-md/aula4.md

## Hyperedges (group relationships)
- **Pipeline Markdown para HTML Offline** — readme_project_overview, guia_apoio_editorial_guide, aula1_aula1_markdown, aula1_aula1_html_page [EXTRACTED 1.00]
- **Núcleo de Prompting da Aula 1** — aula1_prompt_engineering, aula1_context_engineering, aula1_zero_shot_prompting, aula1_few_shot_prompting, aula1_llm_limitations [EXTRACTED 1.00]
- **Fluxo de Validação dos Prompts da Prática** — aula1_pratica_five_prompt_validation_plan, aula1_pratica_scope_control_prompt, aula1_pratica_critical_validation_prompt, aula1_pratica_copy_prompt_function [INFERRED 0.85]

## Communities (4 total, 0 thin omitted)

### Community 0 - "Rascunho Guia Apoio"
Cohesion: 0.36
Nodes (8): Rascunho da Aula 2, Rascunho da Aula 3, Rascunho da Aula 4, Guia de Apoio Editorial e Técnico, Regra de HTML Único com CSS/JS Embutido, Fluxo Markdown Primeiro, HTML Offline Autônomo, Projeto aulas-engenharia-prompt

### Community 1 - "Prompt Validação Limitações"
Cohesion: 0.33
Nodes (6): Limitações de LLMs, Conteúdo Markdown da Prática da Aula 1, Função copyPrompt, Prompt de Validação Crítica, Plano de Validação de 5 Prompts, Prompt de Controle de Escopo Temporal

### Community 2 - "Engenharia Shot Prompting"
Cohesion: 0.5
Nodes (5): Conteúdo Markdown da Aula 1, Engenharia de Contexto, Few-shot Prompting, Engenharia de Prompt, Zero-shot Prompting

### Community 3 - "Página Prática Função"
Cohesion: 0.5
Nodes (5): Página HTML da Aula 1, Página HTML da Prática da Aula 1, Função toggleTheme (Prática), Função toggleTheme, Página inicial do curso

## Knowledge Gaps
- **6 isolated node(s):** `HTML Offline Autônomo`, `Engenharia de Prompt`, `Engenharia de Contexto`, `Prompt de Controle de Escopo Temporal`, `Função toggleTheme` (+1 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Projeto aulas-engenharia-prompt` connect `Rascunho Guia Apoio` to `Prompt Validação Limitações`, `Engenharia Shot Prompting`, `Página Prática Função`?**
  _High betweenness centrality (0.769) - this node is a cross-community bridge._
- **Why does `Conteúdo Markdown da Aula 1` connect `Engenharia Shot Prompting` to `Rascunho Guia Apoio`, `Prompt Validação Limitações`?**
  _High betweenness centrality (0.374) - this node is a cross-community bridge._
- **Why does `Conteúdo Markdown da Prática da Aula 1` connect `Prompt Validação Limitações` to `Rascunho Guia Apoio`?**
  _High betweenness centrality (0.208) - this node is a cross-community bridge._
- **What connects `HTML Offline Autônomo`, `Engenharia de Prompt`, `Engenharia de Contexto` to the rest of the system?**
  _6 weakly-connected nodes found - possible documentation gaps or missing edges._