# Graph Report - aulas-engenharia-prompt  (2026-05-07)

## Corpus Check
- 1 files · ~33,701 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 32 nodes · 33 edges · 8 communities detected
- Extraction: 82% EXTRACTED · 18% INFERRED · 0% AMBIGUOUS · INFERRED: 6 edges (avg confidence: 0.77)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `cacc0f02`
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

## God Nodes (most connected - your core abstractions)
1. `main()` - 6 edges
2. `carregar_dados()` - 4 edges
3. `preparar_dados()` - 4 edges
4. `buscar_melhor_k()` - 4 edges
5. `avaliar_modelo()` - 4 edges
6. `mostrar_resultados()` - 4 edges
7. `Bank Fraud Case Study (Lesson 3 Practical)` - 4 edges
8. `Structured Data Extraction Technique` - 3 edges
9. `Chronological Reconstruction Technique (Topic 3)` - 3 edges
10. `Index HTML Landing Page` - 2 edges

## Surprising Connections (you probably didn't know these)
- `Bank Fraud Case Study (Lesson 3 Practical)` --semantically_similar_to--> `Coordinated Fraud Network Case Study`  [INFERRED] [semantically similar]
  03_AULA3_EXERCICIOS.md → aula 4 - topico 3.md
- `Structured Didactic Pattern for Lessons` --rationale_for--> `Structured Data Extraction Technique`  [INFERRED]
  README.md → 03_AULA3_EXERCICIOS.md
- `Structured Data Extraction Technique` --conceptually_related_to--> `Chronological Reconstruction Technique (Topic 3)`  [INFERRED]
  03_AULA3_EXERCICIOS.md → aula 4 - topico 3.md
- `GitHub Pages Publication Workflow` --rationale_for--> `Index HTML Landing Page`  [INFERRED]
  README.md → index.html
- `Prompt Template and Structural Pattern` --rationale_for--> `Index HTML Landing Page`  [INFERRED]
  README.md → index.html

## Hyperedges (group relationships)
- **Lesson 3 Integrated Investigation Techniques** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula3_exercicios_validation [EXTRACTED 1.00]
- **Progressive Prompting Methodology** — aula3_exercicios_structured_data, aula3_exercicios_mapping, aula4_chain_of_thought, aula4_chronological_reconstruction [INFERRED 0.80]

## Communities (8 total, 2 thin omitted)

### Community 0 - "Community 0"
Cohesion: 0.28
Nodes (8): buscar_melhor_k(), carregar_dados(), main(), CLASSIFICADOR KNN - VERSAO DIDATICA (SEM VALIDACAO CRUZADA)  ORDEM DE ENSINO DES, Carrega o CSV e remove linhas com valores ausentes., Carrega o CSV remoto e remove linhas incompletas.      `dropna()` elimina regist, Testa valores de K e retorna o melhor pela acurácia média., Seleciona o melhor numero de vizinhos (K).      Usa validacao cruzada K-Fold par

### Community 1 - "Community 1"
Cohesion: 0.29
Nodes (8): Relationship Mapping Technique, Structured Data Extraction Technique, Critical Validation Task, Bank Fraud Case Study (Lesson 3 Practical), Chain-of-Thought Prompting with Certainty Marking, Chronological Reconstruction Technique (Topic 3), Coordinated Fraud Network Case Study, Structured Didactic Pattern for Lessons

### Community 2 - "Community 2"
Cohesion: 0.67
Nodes (3): preparar_dados(), Separa X e y, codificando colunas categóricas quando necessário., Prepara as entradas do modelo.      - X: todas as colunas de atributos (features

### Community 3 - "Community 3"
Cohesion: 0.67
Nodes (3): avaliar_modelo(), Gera previsões por validação cruzada e calcula métricas principais., Avalia o modelo final com o K selecionado.      Retorna:     - previsoes de clas

### Community 4 - "Community 4"
Cohesion: 0.67
Nodes (3): mostrar_resultados(), Mostra o resumo final no terminal e o grafico da matriz de confusao., Exibe resumo textual e gráfico da matriz de confusão.

### Community 5 - "Community 5"
Cohesion: 0.67
Nodes (3): Index HTML Landing Page, GitHub Pages Publication Workflow, Prompt Template and Structural Pattern

## Knowledge Gaps
- **20 isolated node(s):** `CLASSIFICADOR KNN - VERSAO DIDATICA (SEM VALIDACAO CRUZADA)  ORDEM DE ENSINO DES`, `Carrega o CSV remoto e remove linhas incompletas.      `dropna()` elimina regist`, `Prepara as entradas do modelo.      - X: todas as colunas de atributos (features`, `Seleciona o melhor numero de vizinhos (K).      Usa validacao cruzada K-Fold par`, `Avalia o modelo final com o K selecionado.      Retorna:     - previsoes de clas` (+15 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `main()` connect `Community 0` to `Community 2`, `Community 3`, `Community 4`?**
  _High betweenness centrality (0.097) - this node is a cross-community bridge._
- **Why does `preparar_dados()` connect `Community 2` to `Community 0`?**
  _High betweenness centrality (0.067) - this node is a cross-community bridge._
- **What connects `CLASSIFICADOR KNN - VERSAO DIDATICA (SEM VALIDACAO CRUZADA)  ORDEM DE ENSINO DES`, `Carrega o CSV remoto e remove linhas incompletas.      `dropna()` elimina regist`, `Prepara as entradas do modelo.      - X: todas as colunas de atributos (features` to the rest of the system?**
  _20 weakly-connected nodes found - possible documentation gaps or missing edges._