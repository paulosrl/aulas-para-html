# Graph Report - .  (2026-05-03)

## Corpus Check
- Corpus is ~31,946 words - fits in a single context window. You may not need a graph.

## Summary
- 49 nodes · 56 edges · 11 communities detected
- Extraction: 55% EXTRACTED · 45% INFERRED · 0% AMBIGUOUS · INFERRED: 25 edges (avg confidence: 0.89)
- Token cost: 37,961 input · 38,040 output

## Community Hubs (Navigation)
- [[_COMMUNITY_Course Notes & Drafts|Course Notes & Drafts]]
- [[_COMMUNITY_Principles & Metacognition|Principles & Metacognition]]
- [[_COMMUNITY_AI Concepts & Foundations|AI Concepts & Foundations]]
- [[_COMMUNITY_Fraud Scenario Investigation|Fraud Scenario Investigation]]
- [[_COMMUNITY_Critical Validation Methods|Critical Validation Methods]]
- [[_COMMUNITY_Timeline & Uncertainty Analysis|Timeline & Uncertainty Analysis]]
- [[_COMMUNITY_Course Materials & Interactive|Course Materials & Interactive]]
- [[_COMMUNITY_Information Extraction Techniques|Information Extraction Techniques]]
- [[_COMMUNITY_Relationship & Link Mapping|Relationship & Link Mapping]]
- [[_COMMUNITY_Aula 3 Content & Slides|Aula 3 Content & Slides]]
- [[_COMMUNITY_Technical Documentation|Technical Documentation]]

## God Nodes (most connected - your core abstractions)
1. `Projeto aulas-engenharia-prompt` - 7 edges
2. `Exercício Prático Intensivo - Aula 3` - 7 edges
3. `Validação Crítica de Respostas Geradas` - 6 edges
4. `Cenário: Operação de Falsificação de Documentação Bancária` - 6 edges
5. `Aula 3 - Slides e Conteúdo Técnico` - 5 edges
6. `Conteúdo Markdown da Prática da Aula 1` - 4 edges
7. `Aula 1 Markdown` - 4 edges
8. `Alucinação em IA` - 3 edges
9. `Rascunho da Aula 3` - 3 edges
10. `Persona + Estruturação com Restrição` - 3 edges

## Surprising Connections (you probably didn't know these)
- `Fluxo Markdown Primeiro` --semantically_similar_to--> `Regra de HTML Único com CSS/JS Embutido`  [INFERRED] [semantically similar]
  README.md → aulas-md/GUIA-APOIO.md
- `Aula 3 - HTML Interactive Content` --references--> `Aula 3 - Slides e Conteúdo Técnico`  [INFERRED]
  html/aula3.html → 03_AULA3_SLIDES_CONTEUDO.md
- `Aula 3 - Prática HTML Interactive Content` --references--> `Exercício Prático Intensivo - Aula 3`  [INFERRED]
  html/aula3-pratica.html → 03_AULA3_EXERCICIOS.md
- `Index - Course Homepage` --references--> `Aula 3 - HTML Interactive Content`  [INFERRED]
  index.html → html/aula3.html
- `Projeto aulas-engenharia-prompt` --references--> `Conteúdo Markdown da Prática da Aula 1`  [EXTRACTED]
  README.md → aulas-md/aula1-pratica.md

## Hyperedges (group relationships)
- **Pipeline Markdown para HTML Offline** — readme_project_overview, guia_apoio_editorial_guide, aula1_aula1_markdown, aula1_aula1_html_page [EXTRACTED 1.00]
- **Fluxo de Validação dos Prompts da Prática** — aula1_pratica_five_prompt_validation_plan, aula1_pratica_scope_control_prompt, aula1_pratica_critical_validation_prompt, aula1_pratica_copy_prompt_function [INFERRED 0.85]
- **Metodologia de Prompt Investigativo** — engenharia_de_prompt_investigativa, engenharia_de_contexto, prompt_investigativo, validacao_humana [INFERRED 0.85]
- **Four Core Prompt Engineering Techniques for Aula 3** — persona_estruturacao, role_prompting_taxonomia, chain_of_thought_certeza, metacognicion_taxonomia_vie [EXTRACTED 1.00]
- **Five Learning Objectives for Investigative Analysis** — extração_informações, mapeamento_vínculos, reconstrução_cronológica, validação_crítica, verificável_inferido_especulativo [EXTRACTED 1.00]
- **Five Practical Tasks Sequence** — tarefa_1_estruturação, tarefa_2_mapeamento, tarefa_3_timeline, tarefa_4_validação, tarefa_5_síntese [EXTRACTED 1.00]

## Communities (11 total, 2 thin omitted)

### Community 0 - "Course Notes & Drafts"
Cohesion: 0.36
Nodes (8): Rascunho da Aula 2, Rascunho da Aula 3, Rascunho da Aula 4, Guia de Apoio Editorial e Técnico, Regra de HTML Único com CSS/JS Embutido, Fluxo Markdown Primeiro, HTML Offline Autônomo, Projeto aulas-engenharia-prompt

### Community 1 - "Principles & Metacognition"
Cohesion: 0.25
Nodes (8): Metacognição + Taxonomia V/I/E, Princípio: Documentar é responsabilidade, Princípio: IA é ferramenta de apoio, nunca substituta, Princípio: Incerteza é honestidade, Princípio: Verificabilidade é critério essencial, Tarefa 4 - Validação Crítica, Validação Crítica de Respostas Geradas, Classificação V/I/E (Verificável/Inferido/Especulativo)

### Community 2 - "AI Concepts & Foundations"
Cohesion: 0.4
Nodes (6): Alucinação em IA, Aula 1 Markdown, Engenharia de Contexto, Engenharia de Prompt para Análises Investigativas, Validação Humana, Vieses dos Dados de Treinamento

### Community 3 - "Fraud Scenario Investigation"
Cohesion: 0.53
Nodes (6): Banco Credito Legal - Agência Pinheiros, Clara Silva - Vítima de Fraude, Cenário: Operação de Falsificação de Documentação Bancária, Maria Silva - Possível Vítima Adicional, Patricia Mendes - Intermediária Fraudulenta, Rafael Torres - Gerente Bancário

### Community 4 - "Critical Validation Methods"
Cohesion: 0.5
Nodes (4): Conteúdo Markdown da Prática da Aula 1, Prompt de Validação Crítica, Plano de Validação de 5 Prompts, Prompt de Controle de Escopo Temporal

### Community 5 - "Timeline & Uncertainty Analysis"
Cohesion: 0.5
Nodes (4): Chain-of-Thought + Marcação de Nível de Certeza, Princípio: Lacunas são informação, Reconstrução Cronológica de Fatos, Tarefa 3 - Timeline Cronológica

### Community 6 - "Course Materials & Interactive"
Cohesion: 0.5
Nodes (4): Exercício Prático Intensivo - Aula 3, Aula 3 - Prática HTML Interactive Content, Index - Course Homepage, Tarefa 5 - Síntese em Relatório

### Community 7 - "Information Extraction Techniques"
Cohesion: 0.67
Nodes (3): Extração de Informações Estruturadas, Persona + Estruturação com Restrição, Tarefa 1 - Estruturação e Extração

### Community 8 - "Relationship & Link Mapping"
Cohesion: 0.67
Nodes (3): Mapeamento de Relações entre Pessoas/Eventos, Role Prompting Especializado + Taxonomia de Vínculos, Tarefa 2 - Mapeamento de Vínculos

## Knowledge Gaps
- **18 isolated node(s):** `HTML Offline Autônomo`, `AGENTS.md Graphify Instructions`, `Plano de Validação de 5 Prompts`, `Prompt de Controle de Escopo Temporal`, `Prompt de Validação Crítica` (+13 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Exercício Prático Intensivo - Aula 3` connect `Course Materials & Interactive` to `Principles & Metacognition`, `Fraud Scenario Investigation`, `Timeline & Uncertainty Analysis`, `Information Extraction Techniques`, `Relationship & Link Mapping`?**
  _High betweenness centrality (0.185) - this node is a cross-community bridge._
- **Why does `Metacognição + Taxonomia V/I/E` connect `Principles & Metacognition` to `Aula 3 Content & Slides`?**
  _High betweenness centrality (0.129) - this node is a cross-community bridge._
- **Are the 5 inferred relationships involving `Validação Crítica de Respostas Geradas` (e.g. with `Metacognição + Taxonomia V/I/E` and `Princípio: IA é ferramenta de apoio, nunca substituta`) actually correct?**
  _`Validação Crítica de Respostas Geradas` has 5 INFERRED edges - model-reasoned connections that need verification._
- **What connects `HTML Offline Autônomo`, `AGENTS.md Graphify Instructions`, `Plano de Validação de 5 Prompts` to the rest of the system?**
  _18 weakly-connected nodes found - possible documentation gaps or missing edges._