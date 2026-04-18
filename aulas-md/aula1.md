# Engenharia de Prompt para Análises Investigativas

**Professor:** Paulo Lima (Datavirtus)
**Objetivo:** Transforme perguntas em insights poderosos.
Exclusivo para agentes da lei.

---

# Agenda da Aula 1

1.  **Contexto e Motivação:** Por que a IA importa para investigadores.
2.  **O que são LLMs:** Funcionamento, geração de texto, vieses e alucinações.
3.  **Fundamentos:** Engenharia de Prompt e Engenharia de Contexto.
4.  **Erros Comuns:** Como não usar a IA.
5.  **Anatomia do Prompt Investigativo:** Personas e exemplos práticos.
6.  **Terminologia:** Termos técnicos essenciais.
7.  **Panorama de Ferramentas:** Claude, Copilot e Gemini.
8.  **Uso Responsável:** Sigilo, o que não inserir e boas práticas.
9.  **Técnicas Aplicadas:** Prompts Zero-shot e Few-shot.
10. **O Pulo do Gato:** Use a IA a seu favor.
11. **Exercício Prático.**

---

# Por que a IA Importa: Três Cenários Reais

| Cenário | Tarefa Investigativa | Ganho de Eficiência |
| :--- | :--- | :--- |
| **Síntese Probatória** | Extrair inconsistências cronológicas em 15 depoimentos. | De 4-6h manuais para 20 min + validação. |
| **Vínculos e Padrões** | Encontrar padrão de circulação entre 500 transações e 50 pessoas. | Estruturação em minutos (substitui análise gráfica longa). |
| **Reconstrução Temporal** | Criar linha do tempo coerente de relatos confusos. | Estruturação automática (substitui leitura e anotação manual). |

---

# IA como Colega, não Decisor

* **Capacidades:** A IA analisa, sintetiza e organiza.
* **Limitação Crítica:** IA não toma decisões por você.
* **Responsabilidade:** O juízo e a escolha final são sempre do humano.
* **Revisão:** IA é um "colega incansável", mas pode errar; revise sempre.

---

# O que é um LLM e como gera texto?

* **Definição:** *Large Language Model* é uma IA treinada em bilhões de textos para prever a próxima palavra mais provável.
* **Sem Consciência:** Ele não pensa, não raciocina e não compreende o mundo; funciona por padrões estatísticos e probabilidade.
* **Contexto:** Enxerga apenas a conversa atual, sem memória de sessões anteriores (salvo se fornecido).
* **Acesso:** Não possui acesso externo em tempo real, a menos que habilitado.

---

# O Que Modelos NÃO Sabem

* **Tempo Real:** Treinados até uma data de corte; desconhecem eventos recentes (podem citar fatos desatualizados).
* **Dados Privados:** Não conhecem seus documentos ou inquéritos a menos que você os forneça no contexto.
* **Alucinação:** Quando incerto, o modelo inventa respostas plausíveis que parecem verídicas (confabulação).

---

# Busca Tradicional vs. IA Generativa

* **Motor de Busca:** Encontra e localiza links/documentos existentes; bom para fontes primárias, mas não conecta pontos.
* **IA Generativa (LLM):** Sintetiza, analisa e gera novas estruturas de texto; raciocina passo a passo, mas pode inventar fatos se não for ancorada.

---

# Vieses nos Dados de Treinamento

* **Herança Cultural:** Modelos herdam preconceitos presentes nos textos da internet.
* **Risco Investigativo:** Perguntas sobre perfis criminais podem gerar respostas com vieses de gênero, classe ou origem.
* **Implicação:** Analise sempre os resultados de forma crítica.

---

# Alucinações: O Risco de Respostas Falsas

* **O que é:** Geração de afirmações factualmente incorretas com aparência de coerência e confiança.
* **Manifestações:** Datas, nomes, leis e jurisprudências inventadas; conclusões sem suporte documental.
* **Como Detectar:**
    * Confronte sempre com o material original.
    * Peça citações exatas de trechos dos documentos.
    * Nunca aceite referências jurídicas sem verificação independente.

---

# O Fator Humano e Limitações Técnicas

* **Risco da Desatualização:** Nunca confie em datas automáticas; verifique legislação e precedentes recentes.
* **Risco da Alucinação:** Valide citações de artigos e cheque duplamente cálculos e prazos legais gerados.
* **Papel Humano:** A IA rascunha, o humano valida.

---

# Fundamentos de Engenharia de Prompt

* **Conceito:** Processo interativo de desenvolver e refinar instruções para obter resultados precisos.
* **Analogia do Maestro:** Você ajusta os "instrumentos" (instruções) para alcançar a harmonia (resultado ideal).
* **Exemplo de Refinamento:** De "Resuma este inquérito" para "Foque o resumo nas provas que apontam as qualificadoras do homicídio".

---

# Anatomia de um Prompt de Qualidade

* **Definição:** Um comando estruturado que inclui contexto, objetivo e restrições (não é uma pergunta casual).
* **Prompt Ruim:** "Analisa esse documento" (vago, sem formato).
* **Prompt Bom:** "Releia o depoimento e extraia: (1) cronologia, (2) inconsistências, (3) informações faltantes. Cite a sentença exata."

---

# Engenharia de Contexto: Elementos Chave

1.  **Persona:** Atribuir um papel à IA.
2.  **Background:** Fornecer o cenário.
3.  **Curadoria:** Recortar apenas as informações relevantes e remover ruídos.
4.  **Exemplos:** Mostrar o que se espera.
5.  **Estrutura e Restrições:** Definir formato e o que não fazer.

---

# O Papel do Contexto na IA

* **Definição:** Tudo o que é fornecido no momento (pergunta, histórico, arquivos, instruções).
* **Importância:** A IA só trabalha com o que está na "janela"; nada é presumido.
* **Exemplo Prático:** Sem contexto, "Diligência urgente" pode ser interpretado literalmente (veículo/presteza); com contexto jurídico, é interpretado como coleta de provas.

---

# Dinâmica da Janela de Contexto

* **Janela de Entrada:** Composta por prompts, textos colados, anexos e histórico.
* **Processamento:** O modelo lê o bloco inteiro de uma vez.
* **Saída:** A resposta gerada depende da qualidade da entrada. Se a denúncia for genérica, o erro costuma estar na entrada.

---

# Regras de Ouro para Janelas de Contexto

* **Fragmentação:** Não faça upload de arquivos com centenas de páginas; fragmente em blocos temáticos.
* **Capacidade:** Exemplificado com Claude Sonnet 4.6 (200k tokens). O risco de alucinação aumenta conforme a janela é preenchida (ex: acima de 75.5% de uso).
* **Ação:** Analise por sessões separadas para arquivos volumosos.

---

# Memória da IA: Agora vs. Sempre

* **Na Mesa (Janela de Contexto):** Temporária, finita e zera a cada nova conversa. A IA só "vê" o que está sobre esta mesa.
* **No Treinamento (Memória Estática):** Conhecimento congelado até a data de corte.
* **RAG (Memória Dinâmica):** Busca seletiva em bases oficiais quando solicitada.
* **Insight:** Sem contexto na "mesa", a IA inventa fatos para preencher lacunas.

---

# Matriz de Transformação: Do Risco à Precisão

* **Contexto Fraco (Risco):** "Analise este inquérito e me diga se devo oferecer denúncia." Resulta em resposta genérica e alto risco de alucinação.
* **Contexto Engenheirado (Precisão):** Define **Persona** (Promotor), **Dados** (IP em anexo), **Tarefa** (resumir fatos/indícios), **Restrições** (exclusivamente nos anexos) e **Formato** (seções numeradas).

---

# Como não usar a IA: Três Pilares Faltantes

1.  **Sem Hipótese:** Não use a IA sem uma pergunta de pesquisa definida.
2.  **Sem Curadoria:** Não aceite respostas sem análise crítica e validação jurídica.
3.  **Sem Direção:** Defina o objetivo final (resumir, analisar contradições ou redigir) antes do comando.

---

# Erro 1: Persona Inflada e Calibragem

* **Armadilha (Ruído):** Usar adjetivos exagerados ("melhor jurista do universo", "PhD em Harvard"). Gera respostas arrogantes ou imprecisas.
* **Calibragem (Especialista):** Atribuir papel técnico e direto ("Promotor especializado em direito penal").

---

# Erro 2: Objetivo Genérico

* **Vago:** "Analise este documento e me diga o que acha." Resulta em resumos óbvios sem utilidade tática.
* **Específico:** "Analise criticamente esta denúncia verificando os requisitos do art. 41 do CPP..." Ativa o conhecimento jurídico específico e gera respostas focadas.

---

# Erro 3: Misturar Análise com Escrita

* **O Caos:** Pedir análise jurídica e redação final rebuscada no mesmo prompt.
* **O Fluxo Correto:**
    * **Passo 1 (Processamento):** Analisar aspectos jurídicos e precedentes.
    * **Passo 2 (Formatação):** Redigir a manifestação com base na análise anterior.

---

# Erro 4: Comandos Negativos sem Direção

* **O Bloqueio:** "Não faça texto longo", "Não use palavras difíceis". A IA foca nos termos negativos e pode se confundir.
* **A Direção (Afirmativo):** "Seja conciso", "Use linguagem clara", "Cite apenas jurisprudência aplicável". Mapeia o caminho esperado de forma eficaz.

---

# Erro 5: Excesso de Instruções (Trade-off)

* **Princípio:** Quanto mais instruções simultâneas (o "Mega-Prompt"), menor a qualidade da execução individual.
* **A Correção:** Limite-se a **5 a 7 instruções principais** hierarquizadas. Se precisar de mais, fragmente em vários prompts consecutivos.

---

# Gestão do Foco Cognitivo

Os 5 erros principais (personas infladas, objetivos genéricos, excesso de instruções, comandos negativos e mistura de tarefas) resultam no **desperdício da janela de contexto** e diluição do poder computacional.
**Insight:** Engenharia de prompt é administrar o foco da máquina para economizar seu tempo.

---

# Anatomia do Prompt Investigativo

| Elemento | Descrição | Exemplo |
| :--- | :--- | :--- |
| **01 Papel** | Quem a IA deve ser? | Analista de inteligência em crimes financeiros. |
| **02 Contexto** | Qual o cenário? | Analisando extratos de investigação de corrupção. |
| **03 Instrução** | O que deve fazer? | Identificar movimentações atípicas e padrões. |
| **04 Formato** | Como entregar? | Tabela: Data \| Valor \| Beneficiário \| Motivo. |
| **05 Restrições** | O que não fazer? | Use apenas dados fornecidos; sem suposições. |

---

# Personas Investigativas

* **Delegado de Polícia:** Viés estratégico; foco em Direito Penal/Processual e fundamentação jurídica.
* **Investigador:** Viés probatório; foco em coleta de provas, diligências e quebra de contradições.
* **Agente de Inteligência:** Viés analítico; foco em interpretação de dados obscuros e redes criminais.

---

# Exemplo Prático de Prompt: Agente de Inteligência

> "Aja como um analista de inteligência especializado em crimes financeiros **[PAPEL]**. Estou analisando extratos bancários de uma investigação de corrupção envolvendo múltiplos laranjas **[CONTEXTO]**. Identifique movimentações atípicas, agrupe por beneficiário e sinalize padrões suspeitos **[INSTRUÇÃO]**. Responda em uma tabela com as colunas: Data, Valor, Beneficiário, Motivo de suspeita **[FORMATO]**. Use apenas os dados fornecidos no texto anexo. Não faça suposições além do texto **[RESTRIÇÕES]**."

---

# Terminologias Técnicas Essenciais

* **Token:** Fragmento de texto; modelos processam tudo em tokens. O limite define quanto a IA lê por vez.
* **Janela de Contexto:** Capacidade de leitura simultânea (ex: 4k a 200k tokens).
* **Temperature:** Controla a criatividade. Baixa ($0.0-0.3$) para precisão; alta ($0.7-1.0$) para variedade.
* **Hallucination (Alucinação):** Invenção de fatos que não existem nos dados fornecidos.

---

# Panorama das Ferramentas (Verificado em 18/04/2026)

| Ferramenta | Pontos Fortes | Ideal Para |
| :--- | :--- | :--- |
| **Claude (Anthropic)** | Contexto até 1M tokens; alta precisão em raciocínio analítico. | Análise aprofundada de documentos complexos. |
| **Copilot (Microsoft)** | Integrado ao M365 (Word, Teams); conformidade governamental. | Fluxo de trabalho em ambiente Microsoft. |
| **Gemini (Google)** | Integrado ao Google Workspace; multimodal (áudio nativo). | Ambiente Google e análise multimodal. |

---

# O que NÃO inserir nos Prompts

* Nomes reais de investigados, vítimas ou testemunhas.
* Números de inquéritos ou documentos sigilosos.
* Dados de interceptações telefônicas ou telemáticas.
* Informações de informantes ou colaboradores.
* Dados pessoais sensíveis (CPF, endereço, financeiro real).

---

# Boas Práticas de Uso e Sigilo

* **Anonimize os Dados:** Use pseudônimos como "Pessoa A" ou "Empresa X".
* **Versões Genéricas:** Descreva padrões de comportamento em vez de fatos identificáveis.
* **LGPD (Art. 7°):** Garanta base legal para o tratamento de dados pessoais.
* **Protocolo Institucional:** A IA nunca substitui as regras de sigilo da corporação.

---

# Privacidade e Segurança de Dados

Plataformas abertas podem armazenar dados inseridos.
**Recomendações:**
* Prefira IA local ou nuvens certificadas pelo órgão.
* Se não for possível, realize obrigatoriamente a anonimização dos dados originais antes da submissão.

---

# Zero-shot vs. Few-shot Prompting

Modelos de aprendizado por instrução (Zero-shot) ou por exemplos (Few-shot) para refinar a saída.

---

# Zero-shot Prompting

* **Definição:** Instrução direta sem exemplos. O modelo tenta realizar a tarefa de primeira.
* **Quando Usar:** Tarefas simples (extrair datas), domínios bem conhecidos ou como primeira tentativa de refinação.

---

# Demonstração: Zero-shot em Ação

**Exemplo de Prompt:**
> "Você é um analista investigativo. Leia o depoimento abaixo e extraia uma lista numerada de TODAS as datas, horários e locais mencionados. Para cada item, cite a sentença exata do texto."

---

# Few-shot Prompting

* **Definição:** Fornecer 1 a 3 exemplos de entrada/saída corretos para o modelo aprender o padrão.
* **Quando Usar:** Quando o formato (ex: seções fixas) importa, quando a IA erra sistematicamente ou quando o padrão é difícil de explicar apenas com palavras.

---

# Demonstração: Few-shot em Ação

**Exemplo de Prompt:**
> "Extraia datas e locais. Use este formato:
> EXEMPLO 1: Entrada: 'Fui à casa do João em 5 de março' -> Saída: LOCAL: casa do João, DATA: 5 de março.
> EXEMPLO 2: ...
> Agora extraia do depoimento: [Texto do depoimento]"

---

# Exercício Prático: Conflito de Depoimentos

**Cenário:** 3 depoimentos (Pessoas A, B e C) com contradições.
**Tarefa:** Construir um prompt estruturado contendo:
1.  **Papel**
2.  **Contexto**
3.  **Instrução** (Cronologia, Pessoas, Locais)
4.  **Formato**
5.  **Restrições**

---

# Metaprompting: O Pulo do Gato

* **Conceito:** Usar a IA para desenhar seus próprios comandos.
* **A Dica de Ouro:** A IA atua como assistente na construção das instruções que ela mesma executará.
* **Exemplo:** "Quero analisar um processo de 400 páginas. Me ajude a criar o melhor prompt possível para identificar provas de autoria..."

---

# Síntese Estratégica: A Partitura Perfeita

* **Iteração:** Itere em etapas (não ajuste tudo de uma vez).
* **Linguagem:** Use termos afirmativos e diretos.
* **Divisão:** Separe a análise profunda da redação final.
* **Validação:** Rigor máximo com leis, prazos e precedentes.

---

# Evolução do Usuário: Complexidade e Valor

1.  **Iniciantes (Gerar Respostas):** "Resuma os depoimentos."
2.  **Intermediários (Refinar Raciocínio):** "Identifique contradições nos depoimentos."
3.  **Avançados (Novas Perguntas):** "Quais teses defensivas o réu usará? Formule perguntas para desconstruí-las."

---

# Encerramento

**Dúvidas?**
Engenharia de Prompt para Análises Investigativas.
