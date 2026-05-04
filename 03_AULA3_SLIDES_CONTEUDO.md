# Aula 3 — Slides e Conteúdo Técnico
## Aplicação Prática em Análises Investigativas

**Data:** 04/05/2026  
**Duração:** 110 minutos  
**Público:** Profissionais da área pública (policiais, MP, Judiciário, auditores)

---

## Objetivos de Aprendizado

Ao final desta aula, você será capaz de:

1. ✅ **Extrair informações estruturadas** de documentos desestruturados (depoimentos, laudos, comunicações)
2. ✅ **Mapear relações** entre pessoas, empresas e eventos (reconhecimento de vínculos)
3. ✅ **Reconstruir cronologia** de fatos com identificação de lacunas
4. ✅ **Validar criticamente** respostas geradas por IA antes de usar em análise oficial
5. ✅ **Integrar técnicas** em fluxo analítico coerente

---

## Roadmap de Técnicas de Prompt Nesta Aula

Você aprenderá a **aplicar 4 técnicas de prompt** em contexto prático investigativo:

| Técnica | O Quê | Quando Usar | Tópico |
|---------|-------|-------------|--------|
| **Persona + Estruturação** | Estabelecer especialidade + Definir formato exato | Extrair informações de documentos desestruturados | 1 |
| **Role Prompting + Taxonomia** | Atribuir identidade especializada + Classificar tipos | Mapear vínculos complexos entre pessoas/eventos | 2 |
| **Chain-of-Thought + Marcação de Certeza** | Forçar raciocínio passo-a-passo + Diferenciar [CERTA/APROXIMADA/INCERTA] | Ordenar cronologicamente; identificar lacunas | 3 |
| **Metacognição + Taxonomia V/I/E** | Pedir auto-crítica do modelo + Classificar [VERIFICÁVEL/INFERIDO/ESPECULATIVO] | Validar respostas antes de usar em relatório | 4 |

**Progressão:** Cada técnica constrói sobre a anterior. Ao final, você saberá integrar todas em um fluxo analítico coerente.

---

## TÓPICO 1: Análise de Documentos Investigativos

### Contexto

Documentos investigativos (depoimentos, laudos, comunicações) chegam frequentemente:
- **Desorganizados:** Informações em ordem aleatória
- **Redundantes:** Mesma informação repetida em múltiplas fontes
- **Inconsistentes:** Dados que se contradizem entre documentos
- **Incompletos:** Lacunas de informação

### O Desafio

Converter esse caos em **informação estruturada e verificável** que suporte análise investigativa.

### Técnica de Prompt: Persona + Estruturação com Restrição

**O que é:**
- **Persona/Role Prompting:** Instruir modelo a agir como especialista ("Você é analista investigativo...")
- **Estruturação:** Definir formato exato de resposta (tabela, lista, JSON)
- **Restrição:** Impor limite explícito ("Use APENAS explícito, não infira")

**Como funciona:**
1. Persona guia **tom e profundidade** da resposta
2. Estruturação força **uniformidade** (mesma resposta, independente do documento)
3. Restrição reduz **alucinações** (modelo não inventa o que não está lá)

**Por que funciona para extração:**
- Depoimentos vêm desorganizados → Estruturação cria ordem
- Risco de modelo "melhorar" dados → Restrição força literalidade
- Análise precisa de especialista → Persona eleva qualidade

**Estratégia:**
1. Estabelecer **persona** especializada (analista investigativo)
2. Definir **instruções claras** (o que extrair: datas, nomes, locais)
3. Especificar **formato de saída** (tabela, lista estruturada)
4. Impor **restrições** (use apenas explícito, não infira)

### Exemplo Prático

**Depoimento (desorganizado):**
```
Prestei queixa sobre falsificação de documentos em meu nome. 
Descobri em 15 de janeiro de 2024 que meu CPF foi utilizado para abrir 
uma conta bancária. A documentação foi entregue em 8 de janeiro segundo 
o gerente. Vi que meu RG era falso (assinatura diferente). 
O gerente passa contato de intermediário chamado Sr. José. 
Sr. José disse que Marisa entregou os documentos. 
Marisa mencionou conhecer tabelião em Santos que facilitava falsificação.
```

**Prompt de Extração:**
```
Você é analista investigativo especializado em síntese de depoimentos.

Leia o depoimento abaixo e extraia:

1. CRONOLOGIA: [Data] — [Horário se houver] — [Evento]
2. PESSOAS: [Nome] — [Papel/função] — [Evidência]
3. LOCAIS: [Local] — [Tipo] — [Atividade]
4. INCONSISTÊNCIAS E LACUNAS

Use APENAS informações explícitas. Se tiver dúvida, marque [INFERIDO].
```

**Resultado Esperado (Estruturado):**

| DATA | EVENTO | PESSOA(S) | LOCAL |
|------|--------|-----------|-------|
| 8 de janeiro de 2024 | Documentação falsificada entregue | Marisa Oliveira → Banco | Agência Banco XYZ, Itaim |
| 15 de janeiro de 2024 | Vítima descobre fraude | Clara Silva | — |
| [DATA NÃO ESPECIFICADA] | Vítima contata Sr. José | Sr. José da Silva | Telefone |

### Por Que Isso Funciona

| Elemento | Benefício |
|----------|-----------|
| **Persona clara** | Modelo entende especialidade esperada |
| **Instrução explícita** | Sem ambiguidade sobre o que fazer |
| **Formato especificado** | Saída uniforme, fácil de processar |
| **Restrição de domínio** | Reduz alucinações |

### Limitações a Reconhecer

⚠️ **O que NÃO fazer:**
- Não inferir motivação (ex: "Marisa é criminosa profissional" — não está no texto)
- Não deduzir padrões (ex: "Fraude organizada" — sem evidência)
- Não suprimir lacunas (ex: "Tabelião em Santos" — sem nome)

✅ **O que fazer:**
- Marcar [DATA NÃO ESPECIFICADA] quando falta informação
- Marcar [INFERIDO] quando dedução é necessária
- Citar sentença exata para cada conclusão

---

## TÓPICO 2: Reconhecimento de Vínculos

### Contexto

Investigações frequentemente exigem entender **quem conhece quem**, **quem transacionou com quem**, **onde as pessoas estiveram juntas**.

### O Desafio

Em casos complexos com 20–50 pessoas e centenas de interações, a rede fica caótica. Como estruturar para que padrões fiquem visíveis?

### Técnica de Prompt: Role Prompting Especializado + Taxonomia de Vínculos

**O que é:**
- **Role Prompting:** Atribuir "identidade especializada" ao modelo ("Você é analista de inteligência...")
- **Taxonomia:** Classificar cada relação em categoria (INTERMEDIAÇÃO, TRANSAÇÃO, etc.)
- **Força diferenciada:** Marcar DIRETA (explícito) vs INDIRETA (inferida) para controlar certeza
- **Evidência exigida:** Citar fonte exata para cada vínculo (rastreabilidade)

**Como funciona:**
1. Role (especialista) → Resposta técnica, profunda, estruturada
2. Taxonomia → Modelo diferencia tipos de vínculo (não confunde parentesco com transação)
3. Força DIRETA/INDIRETA → Marca certeza vs especulação
4. Evidência → Torna cada afirmação verificável contra fonte

**Por que funciona para reconhecimento de vínculos:**
- Casos complexos com 20+ pessoas ficam caóticos → Taxonomia ordena
- Fácil confundir "coleguismo" com "corrupção" → Especialista mantém rigor
- Investigação precisa saber confiança → Força DIRETA/INDIRETA diferencia
- Relatório exige rastreabilidade → Evidência citada permite validar

**Estratégia:**
1. **Role prompting:** "Você é analista de inteligência especializado em redes criminosas"
2. **Tipo de vínculo:** INTERMEDIAÇÃO / TRANSAÇÃO / COMUNICAÇÃO / PARENTESCO / COLEGUISMO
3. **Força do vínculo:** DIRETA (explícito) vs INDIRETA (inferida)
4. **Evidência:** Cite exatamente onde encontrou a informação

### Exemplo Prático

**Dados (desorganizados):**
```
Sr. Carlos é gerente do Banco XYZ.
Sr. José intermediou abertura de conta envolvendo Marisa.
Marisa é amiga de infância da esposa do tabelião em Santos.
Sr. Carlos recebeu Marisa na agência em 30/12/2023.
```

**Prompt de Mapeamento:**
```
Você é analista de inteligência especializado em mapeamento de redes.

INSTRUÇÃO: Para CADA frase abaixo, identifique TODAS as pessoas mencionadas e o tipo de vínculo EXPLÍCITO entre elas.

PASSO 1: Processe cada frase sequencialmente
PASSO 2: Extraia vínculos DIRETOS (ditos explicitamente) ANTES de inferências
PASSO 3: Use a estrutura exata abaixo

ESTRUTURA OBRIGATÓRIA para cada vínculo:
[Pessoa A] ↔ [TIPO] ↔ [Pessoa B]
Força: DIRETA / INDIRETA
Evidência: [citação exata da frase]

TIPOS DE VÍNCULO (use EXATAMENTE um destes):
- COLEGUISMO = trabalho/relação profissional
- INTERMEDIAÇÃO = mediação/facilitação de negócio
- TRANSAÇÃO = troca/recebimento presencial
- COMUNICAÇÃO = ligação/contato verbal
- PARENTESCO = família/laço pessoal
- ACOMPANHAMENTO = presença juntas
- FACILITAÇÃO ILÍCITA = facilita crime

IMPORTANTES:
✅ Foque em vínculos DIRETOS primeiro
✅ Marque [PESSOA NÃO IDENTIFICADA] se alguém não tiver nome
❌ Não invente pessoas ou vínculos que não existam
```

**Resultado Esperado (Rede):**

```
1. Sr. Carlos ↔ COLEGUISMO ↔ Sr. José da Silva
   Força: DIRETA
   Evidência: "trabalha com Sr. José da Silva há 10 anos"

2. Sr. José da Silva ↔ INTERMEDIAÇÃO ↔ Marisa Oliveira
   Força: DIRETA
   Evidência: "Sr. José intermediou a abertura de conta que envolveu Marisa Oliveira"

3. Sr. Carlos ↔ TRANSAÇÃO ↔ Marisa Oliveira
   Força: DIRETA (presencial)
   Evidência: "Sr. Carlos recebeu Marisa na agência em 30/12/2023"

4. Marisa Oliveira ↔ PARENTESCO ↔ Esposa do Tabelião
   Força: INDIRETA [VÍNCULO INFERIDO]
   Evidência: "Marisa é amiga de infância da esposa do tabelião"

5. Marisa Oliveira ↔ ACOMPANHAMENTO ↔ [PESSOA NÃO IDENTIFICADA]
   Força: DIRETA
   Evidência: "Marisa estava acompanhada de uma pessoa não identificada"

6. Tabelião em Santos ↔ FACILITAÇÃO ILÍCITA ↔ (atividade de falsificação)
   Força: DIRETA
   Evidência: "facilitava falsificação de documentos"
```

### Visualização Conceitual

```
    Sr. Carlos
        ↓ (coleguismo)
    Sr. José ←→ Marisa
        ↓              ↓
   [Intermediação]  [Amiga de infância]
                        ↓
                  Esposa do Tabelião
                        ↓
                    Tabelião em Santos
                   (falsificação)
```

### Por Que Isso Funciona

| Elemento | Benefício |
|----------|-----------|
| **Tipos explícitos** | Diferencia coleguismo de transação de parentesco |
| **Força (DIRETA/INDIRETA)** | Marca certeza vs. hipótese |
| **Evidência citada** | Verificável contra fonte original |
| **Lacunas marcadas** | Indica onde investigação deve aprofundar |

### Limitações

⚠️ **Não inferir criminosidade:**
- "José é corrupto" — não está dito
- "Marisa é especialista em falsificação" — apenas intermediou uma vez
- "Rede internacional de falsificação" — pura especulação

✅ **Marcar como INFERIDO:**
- Relações que são dedução lógica mas não explícitas
- Força INDIRETA para conexões via terceiros

---

## TÓPICO 3: Reconstrução Cronológica de Fatos

### Contexto

Investigações dependem de **entender ordem dos eventos**. Problemas comuns:
- Informações chegam fora de ordem
- Há períodos sem dados (lacunas)
- Datas conflitam entre fontes
- Sequência temporal revela causalidade

### O Desafio

Com 15–20 eventos e datas parciais, como reconstituir timeline que revele padrão?

### Técnica de Prompt: Chain-of-Thought + Marcação de Nível de Certeza

**O que é:**
- **Chain-of-Thought (CoT):** Forçar modelo a raciocinar em etapas ("Primeiro, identifique; depois, ordene; depois, valide")
- **Marcação de Certeza:** Diferenciar [DATA CERTA] / [DATA APROXIMADA] / [DATA INCERTA]
- **Validação de Consistência:** Pedir ao modelo que questione se sequência faz sentido

**Como funciona:**
1. CoT (passo-a-passo) → Reduz erros de "pulo de lógica"; modelo tem que explicar raciocínio
2. Marcação de certeza → Documenta confiança em cada data (não força certeza artificial)
3. Validação → Modelo detecta contradições internas antes de entregar resposta

**Por que funciona para reconstrução cronológica:**
- Eventos chegam fora de ordem → CoT força organização sistemática
- Fácil confundir "sequência" com "causalidade" → Marcação de certeza protege contra conclusões falsas
- Relatórios exigem transparência → Lacunas marcadas mostram exatamente onde investigação tem gaps
- Datas conflitantes causam confusão → Validação de consistência detecta contradições

**Estratégia:**
1. **Identificar todas as datas** mencionadas (passo 1 do CoT)
2. **Ordenar do mais antigo** para mais recente (passo 2)
3. **Marcar lacunas** (períodos sem informação) (passo 3)
4. **Validar consistência** (se A ocorreu antes de B, dedução X faz sentido?) (passo 4)
5. **Nível de certeza** por data: [DATA CERTA] vs [DATA APROXIMADA] vs [DATA INCERTA] (passo 5)

### Exemplo Prático

**Eventos (fora de ordem):**
```
- Vítima foi para delegacia e prestou queixa
- Conta bancária foi aberta
- Marisa entregou documentação falsificada
- Vítima recebeu ligação de Sr. José confirmando intermediação
- Vítima abriu conta e descobriu uso indevido
- Vítima pediu cópias dos documentos ao gerente

Datas mencionadas:
- 30 de dezembro de 2023 (documentação entregue)
- 2 de janeiro de 2024 (vítima descobriu)
- Depois de 2 de janeiro (ligação Sr. José)
- Algum momento inicial (vítima foi para delegacia)
```

**Prompt de Reconstrução:**
```
Você é analista de cronologia especializado em investigação.

Você recebeu eventos FORA DE ORDEM. Sua tarefa:

1. ORDENAR cronologicamente (antigo → recente)
2. MARCAR períodos sem informação: [LACUNA: X dias]
3. VALIDAR consistência (algo não faz sentido?)
4. INDICAR certeza:
   - [DATA CERTA] = explicitamente mencionada
   - [DATA APROXIMADA] = inferida de contexto
   - [DATA INCERTA] = ambígua
```

**Resultado Esperado (Timeline):**

```
[DATA CERTA] 30 de dezembro de 2023
→ Marisa Oliveira entrega documentação falsificada ao Banco XYZ

[LACUNA: 3 dias]

[DATA CERTA] 2 de janeiro de 2024
→ Vítima toma conhecimento de abertura fraudulenta
→ Vítima pede cópias dos documentos ao gerente

[LACUNA: data não especificada]

[DATA APROXIMADA] Dias/semana após 2 de janeiro
→ Vítima recebe ligação de Sr. José confirmando intermediação

[LACUNA: data não especificada, presumível logo após descoberta]

[DATA INCERTA] Data não mencionada
→ Vítima comparece a delegacia de polícia para prestação de queixa

ANÁLISE DE CONSISTÊNCIA:
✅ Sequência faz sentido: Falsificação (30/12) → Descoberta (2/1) → Investigação (após)
⚠️ LACUNA CRÍTICA: Quando vítima foi à delegacia? Dias após descoberta? Semanas?
⚠️ LACUNA: Como gerente Sr. Carlos contatou vítima para confirmar fraude?
```

### Por Que Isso Funciona

| Elemento | Benefício |
|----------|-----------|
| **Ordem cronológica clara** | Revela causalidade |
| **Lacunas marcadas** | Indica onde investigação tem gaps |
| **Certeza indicada** | Diferencia fato de inferência |
| **Validação de consistência** | Detecta contradições |

### Limitações

⚠️ **Não confundir sequência com causalidade:**
- Só porque A ocorreu antes de B não significa A causou B
- Marque [SEQUÊNCIA INFERIDA] quando causalidade é dedução

✅ **Marcar incertezas:**
- Datas aproximadas recebem [DATA APROXIMADA]
- Lacunas recebem [LACUNA: X dias]

---

## TÓPICO 4: Validação Crítica de Respostas Geradas

### Contexto

IA pode:
- ✅ **Reproduzir informações explícitas** (VERIFICÁVEL)
- ⚠️ **Deduzir logicamente** (INFERIDO) — pode estar correto ou não
- ❌ **Inventar** (ESPECULATIVO/ALUCINAÇÃO) — sempre problema em investigação

### O Desafio

Você recebeu uma resposta de IA. Como saber se é segura usar em relatório oficial?

### Técnica de Prompt: Metacognição (Self-Critique) + Taxonomia de Confiabilidade

**O que é:**
- **Metacognição:** Pedir ao modelo que **questione sua própria resposta** (modelo critica modelo)
- **Taxonomia V/I/E:** Classificar cada afirmação em VERIFICÁVEL / INFERIDO / ESPECULATIVO
- **Confiança diferenciada:** Marcar ALTA / MÉDIA / BAIXA para cada afirmação
- **Rastreamento de certeza:** Documentar exatamente por que confia ou não em cada conclusão

**Como funciona:**
1. Metacognição → Modelo não apenas responde, mas questiona suas próprias conclusões
2. Taxonomia V/I/E → Diferencia fatos verificáveis de especulações (reduz alucinações)
3. Confiança → Marca risco de cada afirmação para próximo analista decidir usar ou não
4. Rastreamento → Transparência: "Por que é ESPECULATIVO? Porque X não está nos dados"

**Por que funciona para validação crítica:**
- IA frequentemente alucina sem avisar → Metacognição força auto-crítica
- Difícil distinguir VERIFICÁVEL de ESPECULATIVO visualmente → Taxonomia explícita protege
- Relatórios oficiais exigem rastreabilidade → Confiança documentada prova rigor
- Segurança investigativa exige desconfiança saudável → Modelo critica a si mesmo

**Estratégia:**
1. Executa análise normalmente
2. **Questiona cada afirmação** contra documento original
3. **Classifica por tipo:**
   - ✅ VERIFICÁVEL = explícito no documento
   - ⚠️ INFERIDO = dedução lógica, mas não explícito
   - ❌ ESPECULATIVO = além dos dados, possível alucinação
4. **Atribui confiança:**
   - ALTA = suportado por evidência clara
   - MÉDIA = lógica válida mas indireta
   - BAIXA = muita incerteza ou dependência de premissas frágeis

### Exemplo Prático

**Resposta de IA (com erros intencionais):**
```
CRONOLOGIA:
- 30/12/2023: Marisa Oliveira, agindo como agente de esquema criminoso 
  profissional, entregou documentação falsificada ao Banco XYZ
- 2/1/2024: Vítima descobriu fraude e acionou Polícia Federal
- 5/1/2024: Investigação foi aberta pela PF com prioridade máxima
- 10/1/2024: Marisa Oliveira foi presa em operação conjunta

PESSOAS:
- Marisa Oliveira: Criminosa profissional
- Sr. José da Silva: Corrupto que facilitava esquema (recebendo propina)
- Sr. Carlos: Gerente conivente que permitiu fraude
```

**Validação Crítica:**
```
Você é supervisor de qualidade de análise investigativa.

Leia esta resposta que foi gerada por IA e o DOCUMENTO ORIGINAL.

Para CADA afirmação:
✅ VERIFICÁVEL = explícito no documento
⚠️ INFERIDO = dedução válida, não explícita
❌ ESPECULATIVO = além dos dados (possível alucinação)

Depois: CONFIANÇA alta/média/baixa
```

**Resultado de Validação:**

| Afirmação | Status | Confiança | Justificativa |
|-----------|--------|-----------|---|
| "30/12 Marisa entregou documento" | ✅ VERIFICÁVEL | ALTA | Explícito em depoimento |
| "Marisa = criminosa **profissional**" | ❌ ESPECULATIVO | BAIXA | Apenas intermediou 1 vez; "profissional" é invenção |
| "2/1 vítima acionou **Polícia Federal**" | ❌ ESPECULATIVO | MUITO BAIXA | Depoimento diz "prestei queixa" em delegacia, não PF; data confirmada mas órgão inventado |
| "5/1 investigação aberta pela PF" | ❌ ESPECULATIVO | NENHUMA | Data completamente inventada |
| "10/1 Marisa foi presa" | ❌ ESPECULATIVO | NENHUMA | Sem qualquer menção a prisão |
| "José = corrupto recebendo propina" | ❌ ESPECULATIVO | BAIXA | "Intermediador" é correto; "corrupto" e "propina" são invenções |
| "Carlos = gerente conivente" | ⚠️ INFERIDO | MÉDIA | Carlos recebeu documentação, mas depoimento não diz se sabia ser falsa |

### Conclusão da Validação

🚨 **ALUCINAÇÕES DETECTADAS:**
- Datas inventadas (5/1, 10/1)
- Órgão inverso (PF vs delegacia local)
- Eventos não mencionados (prisão)
- Escalação absurda (intermediador → criminosa profissional)

✅ **USAR APENAS:**
- Datas e nomes VERIFICÁVEIS
- Papéis básicos (intermediador, entregador)

❌ **REMOVER:**
- Todas as inferências sobre motivação/criminosidade
- Todas as datas não suportadas
- Qualquer escalação sem evidência

### Por Que Isso Funciona

| Elemento | Benefício |
|----------|-----------|
| **Metacognição** | Força modelo a questionar a si mesmo |
| **Classificação (V/I/E)** | Diferencia certeza de especulação |
| **Confiança indicada** | Marca risco de cada afirmação |
| **Proteção contra alucinação** | Previne conclusões prematuras em relatório oficial |

### Limitações

⚠️ **Modelo pode errar na validação também:**
- Às vezes marca VERIFICÁVEL quando está INFERIDO
- Use como **primeira passagem**; sempre revise manualmente contra documento original

✅ **Usar como procedimento em investigação:**
- Toda resposta de IA recebe validação crítica antes de uso
- Documentar: O que foi verificado? O que falta investigar?

---

## TÓPICO 5: Integração — Exercício Prático Intensivo

### Objetivo

Aplicar **TODAS as 4 técnicas em sequência** em cenário realista.

### Técnicas Usadas em Cada Etapa

| Etapa | Técnica | Por Quê |
|-------|---------|---------|
| **1. Extração** | Persona + Estruturação + Restrição | Torna caos em ordem; reduz alucinações |
| **2. Vínculos** | Role Prompting + Taxonomia + Marcação de Força | Diferencia tipos de vínculo; marca certeza |
| **3. Cronologia** | Chain-of-Thought + Marcação de Certeza + Validação | Força raciocínio passo-a-passo; detecta inconsistências |
| **4. Validação** | Metacognição + Taxonomia V/I/E + Confiança | Modelo questiona a si mesmo; detecta alucinações |

### Fluxo Integrado

```
[1. EXTRAÇÃO]
    Persona + Estruturação + Restrição
    ↓
Estruturar informações de múltiplos documentos
    ↓
[2. MAPEAMENTO DE VÍNCULOS]
    Role Prompting + Taxonomia + Força
    ↓
Conectar pessoas/empresas/eventos
    ↓
[3. RECONSTRUÇÃO CRONOLÓGICA]
    Chain-of-Thought + Nível de Certeza + Validação
    ↓
Ordenar fatos, identificar lacunas
    ↓
[4. VALIDAÇÃO CRÍTICA]
    Metacognição + Taxonomia V/I/E + Confiança
    ↓
Questionar cada conclusão antes de relatório
    ↓
[PRODUTO FINAL]
    ↓
Relatório analítico estruturado e verificado
```

### Exemplo de Caso Integrado

**Cenário:** Operação de falsificação de documentação bancária

**Dataset fornecido:**
- Depoimento de vítima (Clara Silva)
- Depoimento de gerente bancário (Rafael Torres)
- Registros de movimentação bancária (saques + transferência)
- Boletim de ocorrência (Maria Silva — possível vítima adicional)

**Tarefa (em dupla — 18 min):**
1. Estruturar informações (5 min)
2. Mapear vínculos (5 min)
3. Reconstituir timeline (4 min)
4. Validar criticamente (2 min)
5. Redigir síntese (2 min)

### Síntese Esperada

```
RELATÓRIO ANALÍTICO — OPERAÇÃO DE FALSIFICAÇÃO

Entre 8 e 15 de janeiro de 2024, pessoa identificada como Patricia Mendes 
utilizou documentação (incluindo procuração presumivelmente falsificada) para 
abrir conta bancária em nome de Clara Silva no Banco Credito Legal, São Paulo, 
realizando saques sucessivos totalizando R$ 3.700 antes de ser bloqueada.

Investigação inicial indica possível padrão similar envolvendo vítima adicional 
(Maria Silva) com roubo de documentos em mesma região.

PRÓXIMOS PASSOS:
1. Localizar Patricia Mendes
2. Investigar vínculo entre Clara e Maria Silva
3. Análise CCTV de ATMs utilizados
4. Rastreamento de origem de procuração falsificada
```

### Competências Integradas

| Competência | Técnica Usada |
|-------------|---------------|
| Saber o que é importante | EXTRAÇÃO (filtra o relevante) |
| Entender relações | MAPEAMENTO (conecta pessoas/eventos) |
| Ver padrão temporal | CRONOLOGIA (ordem revela causalidade) |
| Não confiar cegamente | VALIDAÇÃO (questiona antes de concluir) |

---

## Resumo: Os 4 Pilares

| Pilar | Pergunta | Técnica | Benefício |
|-------|----------|---------|-----------|
| **1. Extração** | O QUÊ aconteceu? | Estruturação + Persona | Informação clara, verificável |
| **2. Vínculos** | QUEM estava envolvido? | Mapeamento de rede | Relações visíveis, padrões |
| **3. Cronologia** | QUANDO aconteceu? | Timeline ordenada | Sequência → causalidade |
| **4. Validação** | POSSO confiar? | Metacognição | Segurança antes de relatório |

---

## Erros Comuns a Evitar

### ❌ Erro 1: Confiar cegamente em resposta de IA

```
❌ ERRADO:
IA gera análise → Você copia para relatório oficial

✅ CORRETO:
IA gera análise → Você valida criticamente → Você refina → Você aprova
```

### ❌ Erro 2: Inferir além dos dados

```
❌ ERRADO:
"Pessoa recebeu ligação" → "Pessoa é corrupta" (inferência sem evidência)

✅ CORRETO:
"Pessoa recebeu ligação" → [FATO VERIFICÁVEL]
"Dedução: Pessoa pode estar envolvida" → [INFERIDO — requer investigação]
```

### ❌ Erro 3: Esquecer lacunas

```
❌ ERRADO:
Timeline com 10 eventos → Parece sequência completa → Confiança falsa

✅ CORRETO:
Timeline com 10 eventos + [LACUNAS: X dias sem informação]
→ Indica onde investigação tem gaps
```

### ❌ Erro 4: Não documentar processo

```
❌ ERRADO:
"Resultado: Pessoa X é criminosa" (sem rastrear onde veio informação)

✅ CORRETO:
"Análise indica: Pessoa X pode estar envolvida em:
 ✅ [VERIFICÁVEL] Intermediação de conta
 ⚠️ [INFERIDO] Relacionamento com falsificador
 ❌ [ESPECULATIVO] Recebimento de propina (requer investigação)"
```

---

## Princípios Aplicáveis a Toda Análise Investigativa com IA

1. **IA é ferramenta de apoio, nunca substituta**
   - Seu julgamento técnico/jurídico permanece em primeiro lugar
   - IA acelera processamento, você valida conclusões

2. **Verificabilidade é critério essencial**
   - Toda afirmação deve citar origem (sentença exata, documento)
   - Se não pode verificar contra fonte, marque como [INFERIDO] ou [ESPECULATIVO]

3. **Lacunas são informação**
   - Não suprima datas faltantes ou pessoas não nomeadas
   - Lacunas indicam próximos passos investigativos

4. **Incerteza é honestidade**
   - Marque [INFERIDO] quando deduz
   - Marque [INCERTO] quando há ambiguidade
   - Nunca force certeza onde não há suporte

5. **Documentar é responsabilidade**
   - Quem decidiu que X era relevante?
   - Qual evidência suporta conclusão Y?
   - Quais premissas foram usadas para dedução Z?

---

## Conexão com Próximas Aulas

**Aula 4 (11/11):** Fluxos Analíticos, Integração e Responsabilidade

Aula 3 domina **técnicas isoladamente**.  
Aula 4 ensina:
- **Encadear prompts** (prompt chaining) para fluxos complexos
- **Ética e responsabilidade** (quando NÃO usar IA)
- **Conformidade institucional** (LGPD, sigilo processual)
- **Auditoria de prompts** (rastrear decisões de IA)

---

## Glossário — Termos-Chave (para referência rápida)

| Termo | Definição |
|-------|-----------|
| **Alucinação** | Informação inventada pelo modelo que não existe nos dados |
| **Verificável** | Informação explícita no documento original |
| **Inferido** | Dedução lógica a partir de dados, mas não explícita |
| **Especulativo** | Informação além dos dados; risco de alucinação |
| **Persona/Role Prompting** | Instruir modelo a agir como especialista (ex: "Você é perito criminal") |
| **Chain-of-Thought** | Forçar modelo a raciocinar passo-a-passo antes de responder |
| **Restrição de Domínio** | Delimitar escopo (ex: "Considere APENAS período de X a Y") |
| **Metacognição** | Pedir ao modelo que questione sua própria resposta |
| **Token** | Fragmento de texto (palavra ou sub-palavra) que modelo processa |
| **Context Window** | Quantidade total de texto que modelo consegue processar por vez |

---

**Última atualização:** 03/05/2026  
**Material de referência:** Para alunos antes/durante/após Aula 3

