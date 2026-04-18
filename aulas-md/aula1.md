# Engenharia de Prompt para Análises Investigativas *Página 1*

**Professor:** Paulo Lima (Datavirtus)
**Objetivo:** Transforme perguntas em insights poderosos.
Exclusivo para agentes da lei.

---

# Agenda da Aula 1 *Página 2*

1.  [cite_start]**Contexto e Motivação:** Por que a IA importa para investigadores. [cite: 14]
2.  [cite_start]**O que são LLMs:** Funcionamento, geração de texto, vieses e alucinações. [cite: 15]
3.  [cite_start]**Fundamentos:** Engenharia de Prompt e Engenharia de Contexto. [cite: 16]
4.  [cite_start]**Erros Comuns:** Como não usar a IA. [cite: 16]
5.  [cite_start]**Anatomia do Prompt Investigativo:** Personas e exemplos práticos. [cite: 17]
6.  [cite_start]**Terminologia:** Termos técnicos essenciais. [cite: 18]
7.  [cite_start]**Panorama de Ferramentas:** Claude, Copilot e Gemini. [cite: 19]
8.  [cite_start]**Uso Responsável:** Sigilo, o que não inserir e boas práticas. [cite: 20]
9.  [cite_start]**Técnicas Aplicadas:** Prompts Zero-shot e Few-shot. [cite: 21]
10. [cite_start]**O Pulo do Gato:** Use a IA a seu favor. [cite: 22]
11. [cite_start]**Exercício Prático.** [cite: 23]

---

# Por que a IA Importa: Três Cenários Reais *Página 3*

| Cenário | Tarefa Investigativa | Ganho de Eficiência |
| :--- | :--- | :--- |
| **Síntese Probatória** | [cite_start]Extrair inconsistências cronológicas em 15 depoimentos. [cite: 26, 27] | [cite_start]De 4-6h manuais para 20 min + validação. [cite: 32, 33] |
| **Vínculos e Padrões** | [cite_start]Encontrar padrão de circulação entre 500 transações e 50 pessoas. [cite: 28, 29] | [cite_start]Estruturação em minutos (substitui análise gráfica longa). [cite: 34, 35] |
| **Reconstrução Temporal** | [cite_start]Criar linha do tempo coerente de relatos confusos. [cite: 30, 31] | [cite_start]Estruturação automática (substitui leitura e anotação manual). [cite: 36, 37] |

---

# IA como Colega, não Decisor *Página 4*

* [cite_start]**Capacidades:** A IA analisa, sintetiza e organiza. [cite: 39, 40, 41]
* [cite_start]**Limitação Crítica:** IA não toma decisões por você. [cite: 42]
* [cite_start]**Responsabilidade:** O juízo e a escolha final são sempre do humano. [cite: 44, 46, 47]
* [cite_start]**Revisão:** IA é um "colega incansável", mas pode errar; revise sempre. [cite: 43, 48, 49]

---

# O que é um LLM e como gera texto? *Página 5*

* [cite_start]**Definição:** *Large Language Model* é uma IA treinada em bilhões de textos para prever a próxima palavra mais provável. [cite: 51, 52]
* [cite_start]**Sem Consciência:** Ele não pensa, não raciocina e não compreende o mundo; funciona por padrões estatísticos e probabilidade. [cite: 53, 54, 55, 56]
* [cite_start]**Contexto:** Enxerga apenas a conversa atual, sem memória de sessões anteriores (salvo se fornecido). [cite: 57, 58]
* [cite_start]**Acesso:** Não possui acesso externo em tempo real, a menos que habilitado. [cite: 61, 62]

---

# O Que Modelos NÃO Sabem *Página 6*

* [cite_start]**Tempo Real:** Treinados até uma data de corte; desconhecem eventos recentes (podem citar fatos desatualizados). [cite: 65, 66, 67]
* [cite_start]**Dados Privados:** Não conhecem seus documentos ou inquéritos a menos que você os forneça no contexto. [cite: 68, 69, 70]
* [cite_start]**Alucinação:** Quando incerto, o modelo inventa respostas plausíveis que parecem verídicas (confabulação). [cite: 71, 72, 73]

---

# Busca Tradicional vs. IA Generativa *Página 7*

* [cite_start]**Motor de Busca:** Encontra e localiza links/documentos existentes; bom para fontes primárias, mas não conecta pontos. [cite: 76, 77, 78, 79, 80, 81]
* [cite_start]**IA Generativa (LLM):** Sintetiza, analisa e gera novas estruturas de texto; raciocina passo a passo, mas pode inventar fatos se não for ancorada. [cite: 83, 84, 85, 87, 88, 90]

---

# Vieses nos Dados de Treinamento *Página 8*

* [cite_start]**Herança Cultural:** Modelos herdam preconceitos presentes nos textos da internet. [cite: 93, 94]
* [cite_start]**Risco Investigativo:** Perguntas sobre perfis criminais podem gerar respostas com vieses de gênero, classe ou origem. [cite: 97, 98, 99]
* [cite_start]**Implicação:** Analise sempre os resultados de forma crítica. [cite: 100, 101]

---

# Alucinações: O Risco de Respostas Falsas *Página 9*

* [cite_start]**O que é:** Geração de afirmações factualmente incorretas com aparência de coerência e confiança. [cite: 105, 106]
* [cite_start]**Manifestações:** Datas, nomes, leis e jurisprudências inventadas; conclusões sem suporte documental. [cite: 114, 115, 116]
* **Como Detectar:**
    * [cite_start]Confronte sempre com o material original. [cite: 118]
    * [cite_start]Peça citações exatas de trechos dos documentos. [cite: 119]
    * [cite_start]Nunca aceite referências jurídicas sem verificação independente. [cite: 120, 121, 122]

---

# O Fator Humano e Limitações Técnicas *Página 10*

* [cite_start]**Risco da Desatualização:** Nunca confie em datas automáticas; verifique legislação e precedentes recentes. [cite: 130, 131, 132, 133]
* [cite_start]**Risco da Alucinação:** Valide citações de artigos e cheque duplamente cálculos e prazos legais gerados. [cite: 135, 136, 138]
* [cite_start]**Papel Humano:** A IA rascunha, o humano valida. [cite: 126]

---

# Fundamentos de Engenharia de Prompt *Página 11*

* [cite_start]**Conceito:** Processo interativo de desenvolver e refinar instruções para obter resultados precisos. [cite: 140, 143]
* [cite_start]**Analogia do Maestro:** Você ajusta os "instrumentos" (instruções) para alcançar a harmonia (resultado ideal). [cite: 144]
* [cite_start]**Exemplo de Refinamento:** De "Resuma este inquérito" para "Foque o resumo nas provas que apontam as qualificadoras do homicídio". [cite: 146, 149, 150]

---

# Anatomia de um Prompt de Qualidade *Página 12*

* [cite_start]**Definição:** Um comando estruturado que inclui contexto, objetivo e restrições (não é uma pergunta casual). [cite: 153, 154]
* [cite_start]**Prompt Ruim:** "Analisa esse documento" (vago, sem formato). [cite: 156, 157, 158]
* [cite_start]**Prompt Bom:** "Releia o depoimento e extraia: (1) cronologia, (2) inconsistências, (3) informações faltantes. Cite a sentença exata." [cite: 159, 160, 161]

---

# Engenharia de Contexto: Elementos Chave *Página 13*

1.  [cite_start]**Persona:** Atribuir um papel à IA. [cite: 165]
2.  [cite_start]**Background:** Fornecer o cenário. [cite: 166]
3.  [cite_start]**Curadoria:** Recortar apenas as informações relevantes e remover ruídos. [cite: 168, 170, 172, 174]
4.  [cite_start]**Exemplos:** Mostrar o que se espera. [cite: 169]
5.  [cite_start]**Estrutura e Restrições:** Definir formato e o que não fazer. [cite: 175, 176]

---

# O Papel do Contexto na IA *Página 14*

* [cite_start]**Definição:** Tudo o que é fornecido no momento (pergunta, histórico, arquivos, instruções). [cite: 177, 179, 180, 181, 182, 183]
* [cite_start]**Importância:** A IA só trabalha com o que está na "janela"; nada é presumido. [cite: 184, 185]
* [cite_start]**Exemplo Prático:** Sem contexto, "Diligência urgente" pode ser interpretado literalmente (veículo/presteza); com contexto jurídico, é interpretado como coleta de provas. [cite: 194, 200, 202]

---

# Dinâmica da Janela de Contexto *Página 15*

* [cite_start]**Janela de Entrada:** Composta por prompts, textos colados, anexos e histórico. [cite: 206, 207, 208, 209]
* [cite_start]**Processamento:** O modelo lê o bloco inteiro de uma vez. [cite: 211]
* **Saída:** A resposta gerada depende da qualidade da entrada. [cite_start]Se a denúncia for genérica, o erro costuma estar na entrada. [cite: 213, 214]

---

# Regras de Ouro para Janelas de Contexto *Página 16*

* [cite_start]**Fragmentação:** Não faça upload de arquivos com centenas de páginas; fragmente em blocos temáticos. [cite: 218, 219]
* **Capacidade:** Exemplificado com Claude Sonnet 4.6 (200k tokens). [cite_start]O risco de alucinação aumenta conforme a janela é preenchida (ex: acima de 75.5% de uso). [cite: 223, 226, 228]
* [cite_start]**Ação:** Analise por sessões separadas para arquivos volumosos. [cite: 222]

---

# Memória da IA: Agora vs. Sempre *Página 17*

* **Na Mesa (Janela de Contexto):** Temporária, finita e zera a cada nova conversa. [cite_start]A IA só "vê" o que está sobre esta mesa. [cite: 244, 247, 250, 251]
* [cite_start]**No Treinamento (Memória Estática):** Conhecimento congelado até a data de corte. [cite: 245, 257]
* [cite_start]**RAG (Memória Dinâmica):** Busca seletiva em bases oficiais quando solicitada. [cite: 258]
* [cite_start]**Insight:** Sem contexto na "mesa", a IA inventa fatos para preencher lacunas. [cite: 260]

---

# Matriz de Transformação: Do Risco à Precisão *Página 18*

* **Contexto Fraco (Risco):** "Analise este inquérito e me diga se devo oferecer denúncia." [cite_start]Resulta em resposta genérica e alto risco de alucinação. [cite: 263, 264, 270]
* [cite_start]**Contexto Engenheirado (Precisão):** Define **Persona** (Promotor), **Dados** (IP em anexo), **Tarefa** (resumir fatos/indícios), **Restrições** (exclusivamente nos anexos) e **Formato** (seções numeradas). [cite: 265, 266, 267, 268]

---

# Como não usar a IA: Três Pilares Faltantes *Página 19*

1.  [cite_start]**Sem Hipótese:** Não use a IA sem uma pergunta de pesquisa definida. [cite: 275, 276, 277]
2.  [cite_start]**Sem Curadoria:** Não aceite respostas sem análise crítica e validação jurídica. [cite: 278, 279]
3.  [cite_start]**Sem Direção:** Defina o objetivo final (resumir, analisar contradições ou redigir) antes do comando. [cite: 281, 282]

---

# Erro 1: Persona Inflada e Calibragem *Página 20*

* **Armadilha (Ruído):** Usar adjetivos exagerados ("melhor jurista do universo", "PhD em Harvard"). [cite_start]Gera respostas arrogantes ou imprecisas. [cite: 284, 287, 290, 291, 292]
* [cite_start]**Calibragem (Especialista):** Atribuir papel técnico e direto ("Promotor especializado em direito penal"). [cite: 289, 294, 295, 296]

---

# Erro 2: Objetivo Genérico *Página 21*

* **Vago:** "Analise este documento e me diga o que acha." [cite_start]Resulta em resumos óbvios sem utilidade tática. [cite: 297, 299, 300, 301]
* [cite_start]**Específico:** "Analise criticamente esta denúncia verificando os requisitos do art. 41 do CPP..." Ativa o conhecimento jurídico específico e gera respostas focadas. [cite: 303, 304, 307, 308]

---

# Erro 3: Misturar Análise com Escrita *Página 22*

* [cite_start]**O Caos:** Pedir análise jurídica e redação final rebuscada no mesmo prompt. [cite: 309, 312, 315]
* **O Fluxo Correto:**
    * [cite_start]**Passo 1 (Processamento):** Analisar aspectos jurídicos e precedentes. [cite: 313, 314]
    * [cite_start]**Passo 2 (Formatação):** Redigir a manifestação com base na análise anterior. [cite: 316, 317]

---

# Erro 4: Comandos Negativos sem Direção *Página 23*

* **O Bloqueio:** "Não faça texto longo", "Não use palavras difíceis". [cite_start]A IA foca nos termos negativos e pode se confundir. [cite: 319, 321, 325, 326, 328]
* **A Direção (Afirmativo):** "Seja conciso", "Use linguagem clara", "Cite apenas jurisprudência aplicável". [cite_start]Mapeia o caminho esperado de forma eficaz. [cite: 324, 329, 330, 331]

---

# Erro 5: Excesso de Instruções (Trade-off) *Página 24*

* [cite_start]**Princípio:** Quanto mais instruções simultâneas (o "Mega-Prompt"), menor a qualidade da execução individual. [cite: 333, 334, 356]
* **A Correção:** Limite-se a **5 a 7 instruções principais** hierarquizadas. [cite_start]Se precisar de mais, fragmente em vários prompts consecutivos. [cite: 351, 352, 355]

---

# Gestão do Foco Cognitivo *Página 25*

[cite_start]Os 5 erros principais (personas infladas, objetivos genéricos, excesso de instruções, comandos negativos e mistura de tarefas) resultam no **desperdício da janela de contexto** e diluição do poder computacional. [cite: 357, 359, 360, 362, 364]
[cite_start]**Insight:** Engenharia de prompt é administrar o foco da máquina para economizar seu tempo. [cite: 365, 366]

---

# Anatomia do Prompt Investigativo *Página 26*

| Elemento | Descrição | Exemplo |
| :--- | :--- | :--- |
| **01 Papel** | Quem a IA deve ser? | [cite_start]Analista de inteligência em crimes financeiros. [cite: 376, 377] |
| **02 Contexto** | Qual o cenário? | [cite_start]Analisando extratos de investigação de corrupção. [cite: 378, 381, 382] |
| **03 Instrução** | O que deve fazer? | [cite_start]Identificar movimentações atípicas e padrões. [cite: 379, 383] |
| **04 Formato** | Como entregar? | Tabela: Data \| Valor \| Beneficiário \| [cite_start]Motivo. [cite: 384] |
| **05 Restrições** | O que não fazer? | [cite_start]Use apenas dados fornecidos; sem suposições. [cite: 385, 386] |

---

# Personas Investigativas *Página 27*

* [cite_start]**Delegado de Polícia:** Viés estratégico; foco em Direito Penal/Processual e fundamentação jurídica. [cite: 389]
* [cite_start]**Investigador:** Viés probatório; foco em coleta de provas, diligências e quebra de contradições. [cite: 390]
* [cite_start]**Agente de Inteligência:** Viés analítico; foco em interpretação de dados obscuros e redes criminais. [cite: 391]

---

# Exemplo Prático de Prompt: Agente de Inteligência *Página 28*

> [cite_start]"Aja como um analista de inteligência especializado em crimes financeiros **[PAPEL]**. Estou analisando extratos bancários de uma investigação de corrupção envolvendo múltiplos laranjas **[CONTEXTO]**. Identifique movimentações atípicas, agrupe por beneficiário e sinalize padrões suspeitos **[INSTRUÇÃO]**. Responda em uma tabela com as colunas: Data, Valor, Beneficiário, Motivo de suspeita **[FORMATO]**. Use apenas os dados fornecidos no texto anexo. Não faça suposições além do texto **[RESTRIÇÕES]**." [cite: 395, 396, 397, 398, 399]

---

# Terminologias Técnicas Essenciais *Página 29*

* **Token:** Fragmento de texto; modelos processam tudo em tokens. [cite_start]O limite define quanto a IA lê por vez. [cite: 402, 404, 405]
* [cite_start]**Janela de Contexto:** Capacidade de leitura simultânea (ex: 4k a 200k tokens). [cite: 406, 407]
* **Temperature:** Controla a criatividade. [cite_start]Baixa ($0.0-0.3$) para precisão; alta ($0.7-1.0$) para variedade. [cite: 408, 409]
* [cite_start]**Hallucination (Alucinação):** Invenção de fatos que não existem nos dados fornecidos. [cite: 410, 411]

---

# Panorama das Ferramentas (Verificado em 11/04/2026) *Página 30*

| Ferramenta | Pontos Fortes | Ideal Para |
| :--- | :--- | :--- |
| **Claude (Anthropic)** | [cite_start]Contexto até 1M tokens; alta precisão em raciocínio analítico. [cite: 414, 419, 420] | [cite_start]Análise aprofundada de documentos complexos. [cite: 447] |
| **Copilot (Microsoft)** | [cite_start]Integrado ao M365 (Word, Teams); conformidade governamental. [cite: 426, 430, 431] | [cite_start]Fluxo de trabalho em ambiente Microsoft. [cite: 448] |
| **Gemini (Google)** | [cite_start]Integrado ao Google Workspace; multimodal (áudio nativo). [cite: 436, 441, 442] | [cite_start]Ambiente Google e análise multimodal. [cite: 449] |

---

# O que NÃO inserir nos Prompts *Página 31*

* [cite_start]Nomes reais de investigados, vítimas ou testemunhas. [cite: 453]
* [cite_start]Números de inquéritos ou documentos sigilosos. [cite: 453]
* [cite_start]Dados de interceptações telefônicas ou telemáticas. [cite: 456]
* [cite_start]Informações de informantes ou colaboradores. [cite: 456]
* [cite_start]Dados pessoais sensíveis (CPF, endereço, financeiro real). [cite: 456]

---

# Boas Práticas de Uso e Sigilo *Página 32*

* [cite_start]**Anonimize os Dados:** Use pseudônimos como "Pessoa A" ou "Empresa X". [cite: 461, 462]
* [cite_start]**Versões Genéricas:** Descreva padrões de comportamento em vez de fatos identificáveis. [cite: 463, 464]
* [cite_start]**LGPD (Art. 7°):** Garanta base legal para o tratamento de dados pessoais. [cite: 465, 466]
* [cite_start]**Protocolo Institucional:** A IA nunca substitui as regras de sigilo da corporação. [cite: 467, 468]

---

# Privacidade e Segurança de Dados *Página 33*

[cite_start]Plataformas abertas podem armazenar dados inseridos. [cite: 471]
**Recomendações:**
* [cite_start]Prefira IA local ou nuvens certificadas pelo órgão. [cite: 474]
* [cite_start]Se não for possível, realize obrigatoriamente a anonimização dos dados originais antes da submissão. [cite: 474, 475]

---

# Zero-shot vs. Few-shot Prompting *Página 34*

[cite_start]Modelos de aprendizado por instrução (Zero-shot) ou por exemplos (Few-shot) para refinar a saída. [cite: 478, 482, 488]

---

# Zero-shot Prompting *Página 35*

* **Definição:** Instrução direta sem exemplos. [cite_start]O modelo tenta realizar a tarefa de primeira. [cite: 501, 503]
* [cite_start]**Quando Usar:** Tarefas simples (extrair datas), domínios bem conhecidos ou como primeira tentativa de refinação. [cite: 504, 505, 507, 509]

---

# Demonstração: Zero-shot em Ação *Página 36*

**Exemplo de Prompt:**
> [cite_start]"Você é um analista investigativo. Leia o depoimento abaixo e extraia uma lista numerada de TODAS as datas, horários e locais mencionados. Para cada item, cite a sentença exata do texto." [cite: 515, 516, 517, 518]

---

# Few-shot Prompting *Página 37*

* [cite_start]**Definição:** Fornecer 1 a 3 exemplos de entrada/saída corretos para o modelo aprender o padrão. [cite: 524, 526]
* [cite_start]**Quando Usar:** Quando o formato (ex: seções fixas) importa, quando a IA erra sistematicamente ou quando o padrão é difícil de explicar apenas com palavras. [cite: 527, 528, 530, 532]

---

# Demonstração: Few-shot em Ação *Página 38*

**Exemplo de Prompt:**
> "Extraia datas e locais. Use este formato:
> EXEMPLO 1: Entrada: 'Fui à casa do João em 5 de março' -> Saída: LOCAL: casa do João, DATA: 5 de março.
> EXEMPLO 2: ...
> [cite_start]Agora extraia do depoimento: [Texto do depoimento]" [cite: 536, 537, 538, 542, 546]

---

# Exercício Prático: Conflito de Depoimentos *Página 39*

[cite_start]**Cenário:** 3 depoimentos (Pessoas A, B e C) com contradições. [cite: 549, 550]
**Tarefa:** Construir um prompt estruturado contendo:
1.  [cite_start]**Papel** [cite: 554]
2.  [cite_start]**Contexto** [cite: 556]
3.  [cite_start]**Instrução** (Cronologia, Pessoas, Locais) [cite: 552, 558]
4.  [cite_start]**Formato** [cite: 560]
5.  [cite_start]**Restrições** [cite: 562]

---

# Metaprompting: O Pulo do Gato *Página 40*

* [cite_start]**Conceito:** Usar a IA para desenhar seus próprios comandos. [cite: 566, 567]
* [cite_start]**A Dica de Ouro:** A IA atua como assistente na construção das instruções que ela mesma executará. [cite: 570, 571]
* [cite_start]**Exemplo:** "Quero analisar um processo de 400 páginas. Me ajude a criar o melhor prompt possível para identificar provas de autoria..." [cite: 573]

---

# Síntese Estratégica: A Partitura Perfeita *Página 41*

* [cite_start]**Iteração:** Itere em etapas (não ajuste tudo de uma vez). [cite: 579]
* [cite_start]**Linguagem:** Use termos afirmativos e diretos. [cite: 582]
* [cite_start]**Divisão:** Separe a análise profunda da redação final. [cite: 581]
* [cite_start]**Validação:** Rigor máximo com leis, prazos e precedentes. [cite: 583]

---

# Evolução do Usuário: Complexidade e Valor *Página 42*

1.  [cite_start]**Iniciantes (Gerar Respostas):** "Resuma os depoimentos." [cite: 587, 588]
2.  [cite_start]**Intermediários (Refinar Raciocínio):** "Identifique contradições nos depoimentos." [cite: 589, 590]
3.  [cite_start]**Avançados (Novas Perguntas):** "Quais teses defensivas o réu usará? Formule perguntas para desconstruí-las." [cite: 591, 592, 593]

---

# Encerramento *Página 43*

[cite_start]**Dúvidas?** [cite: 596]
Engenharia de Prompt para Análises Investigativas.