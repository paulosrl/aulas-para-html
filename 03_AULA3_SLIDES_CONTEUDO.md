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

**Progressão:** Cada técnica constrói sobre a anterior. Ao final, você saberá integrar todas em um fluxo analítico coerente.

---
# TÓPICO 1: Análise Estruturada de Documentos Investigativos

## 📌 A Situação-Problema

Documentos investigativos (depoimentos, laudos, comunicações) chegam com problemas sistemáticos:

- **Desorganizados** — Informações em ordem aleatória
- **Redundantes** — Mesma informação repetida em múltiplas fontes
- **Inconsistentes** — Dados que se contradizem entre documentos
- **Incompletos** — Lacunas de informação

**Resultado:** Converter esse caos em informação estruturada e verificável que suporte análise investigativa.

---

## 🎯 Objetivo

Extrair dados essenciais de documentos desorganizados mantendo:
- ✅ Fidelidade ao documento (sem invenções)
- ✅ Uniformidade na estrutura (mesma resposta independente da fonte)
- ✅ Especialidade analítica (qualidade de especialista)

---

## 🔧 A Solução: Persona + Estruturação + Restrição

Combine 3 elementos estratégicos:

1. **Persona** — Atribua especialidade ao modelo ("Você é analista investigativo...")
2. **Estruturação** — Defina formato exato de resposta (tabela, lista, JSON)
3. **Restrição** — Force literalidade ("Use APENAS o explícito, não infira")

---

## 💡 Por Que Funciona

| Problema | Solução | Resultado |
|----------|---------|-----------|
| Documentos desorganizados | Estruturação força formato | Uniformidade garantida |
| Risco de "melhorias" dos dados | Restrição força literalidade | Fidelidade mantida |
| Qualidade variável | Persona eleva padrão | Análise profissional |

**Na prática:**
- Depoimentos diferentes → **Mesma estrutura de saída**
- Modelo tentado a inferir → **Restrição proíbe**
- Análise genérica → **Persona especializa**

---

## 📋 Componentes da Técnica

### 1. Persona (Especialidade)
```
"Você é um ANALISTA INVESTIGATIVO EXPERIENTE com 15 anos 
em extração de dados de documentos complexos.
Sua função: Estruturar informações fragmentadas em formato 
verificável, mantendo fidelidade absoluta à fonte."
```

**Efeito:** Modelo compreende contexto e eleva rigor analítico.

### 2. Estruturação (Formato)
```
EXTRAIA E ORGANIZE em tabela:
- Dados pessoais (nome, data, local)
- Eventos cronológicos
- Contradições detectadas
- Informação faltante
```

**Efeito:** Resposta uniforme independente do documento.

### 3. Restrição (Literalidade)
```
OBRIGATÓRIO:
- Use APENAS informação explícita
- Se ambíguo, sinalize [AMBÍGUO]
- Se falta dado, sinalize [NÃO MENCIONADO]
- NÃO infira, NÃO deduza, NÃO melhore
```

**Efeito:** Zero alucinações, 100% rastreabilidade.

---

## 🔄 Procedimento (Passo a Passo)

1. **Estabelecer Persona**
   - Defina especialidade (analista, investigador, perito)
   - Indique experiência/autoridade
   - Explique contexto (por que essa expertise importa aqui)

2. **Definir o Que Extrair**
   - Datas, nomes, locais, eventos
   - Contradições, lacunas
   - Relações entre informações

3. **Especificar Formato de Saída**
   - Tabela, lista, JSON, texto estruturado
   - Mesma forma para todos os documentos

4. **Impor Restrições Explícitas**
   - Proíba inferência
   - Marque ambiguidades
   - Sinalize falta de informação

5. **Aplicar ao Documento**
   - Instruções + Documento = Saída estruturada

---

## 📖 Exemplo Prático

### Contexto do Caso
Suposta fraude de R$ 50 mil no Banco Sul. Em 10/03, Sandra Lima abriu uma conta acompanhada por homem não identificado. No dia 20/03, tentativa de transferência em terminal físico causou bloqueio automático.

**Problemas documentados:**
- Conflito de horários: gerente relata 14h, TI registra 16h30
- Falhas de registro: câmeras não funcionaram, vigilante perdeu anotações
- Ausência de comando: gerente estava em viagem, homem saiu apressado após travamento

---

### Prompt Aplicado (Com Persona + Estruturação + Restrição)

```
Você é um ANALISTA DE FRAUDES BANCÁRIAS com experiência em 
reconstrução de cronologias e detecção de inconsistências.

EXTRAIA do documento abaixo:

TABELA 1: Dados Essenciais
- Nome da vítima: [valor ou NÃO MENCIONADO]
- Data da conta: [valor ou NÃO MENCIONADO]
- Valor em risco: [valor ou NÃO MENCIONADO]
- Acompanhante: [valor ou NÃO MENCIONADO]

TABELA 2: Cronologia de Eventos
| Data | Hora | Evento | Fonte | Confiabilidade |
|------|------|--------|-------|---|

TABELA 3: Contradições Detectadas
- [CONTRADIÇÃO]: Horário do bloqueio
  * Fonte 1 (Gerente): 14h
  * Fonte 2 (TI): 16h30
  * Status: CONFLITANTE

TABELA 4: Informação Faltante
- Identidade do acompanhante: [NÃO MENCIONADO]
- Horários exatos de movimentação: [PERDIDO - vigilante perdeu anotações]
- Evidência de câmeras: [FALHA - câmeras não funcionaram]

REGRA OBRIGATÓRIA:
Use APENAS o explícito. Se ambíguo, sinalize [AMBÍGUO].
Se falta dados, sinalize [NÃO MENCIONADO].
NÃO infira, NÃO deduza.
```

---

### Resultado Esperado

**SAÍDA ESTRUTURADA:**

| Aspecto | Informação | Status |
|---------|-----------|--------|
| Vítima | Sandra Lima | CONFIRMADO |
| Data abertura | 10/03 | CONFIRMADO |
| Valor | R$ 50 mil | CONFIRMADO |
| Tentativa | 20/03, terminal físico | CONFIRMADO |
| Acompanhante | Homem não identificado | [AMBÍGUO - descrição insuficiente] |

**Contradições:**
- ⚠️ **Horário do bloqueio**: Gerente (14h) vs TI (16h30) — CONFLITANTE

**Lacunas Críticas:**
- ❌ Identidade do acompanhante
- ❌ Câmeras (não funcionaram)
- ❌ Anotações do vigilante (perdidas)

**Análise:**
"Existem 3 falhas de registro que comprometem cronologia exata. Contradição de horário sugere falta de sincronização entre sistemas. Recomenda-se: verificar logs de TI, recuperar registros de câmera de outras fontes, entrevistar gerente e TI sobre discrepância."

---

## ✅ Por Que Este Fluxo Funciona

1. **Persona** eleva rigor → Analista não "melhora" dados
2. **Estruturação** força uniformidade → Mesma resposta para qualquer documento
3. **Restrição** garante rastreabilidade → Sabe-se de onde veio cada dado
4. **Exemplo prático** conecta teoria à realidade → Aluno vê aplicação imediata

---

## 🎓 Aprendizado para o Aluno

Ao final, o aluno entende:
- ✅ Como organizar informação caótica sem inventar dados
- ✅ Como evitar alucinações (modelo genérico vs especializado)
- ✅ Como estruturar resposta para auditoria e verificação
- ✅ Como usar persona + restrição em casos reais


# TÓPICO 2: Reconhecimento de Vínculos em Redes

---

## 📌 A Situação-Problema

Investigações frequentemente exigem entender: **quem conhece quem, quem transacionou com quem, onde as pessoas estiveram juntas.**

Em casos complexos com 20–50 pessoas e centenas de interações, a rede fica caótica:
- Impossível visualizar padrões manualmente
- Fácil confundir tipos de vínculo (parentesco ≠ transação ≠ corrupção)
- Sem rastreabilidade, é impossível validar afirmações

**Resultado:** Como estruturar para que padrões fiquem visíveis e verificáveis?

---

## 🎯 Objetivo

Mapear relacionamentos entre pessoas em formato estruturado (CSV) que permita:
- ✅ Visualização em software de análise de redes (i2 Analysts Notebook)
- ✅ Diferenciação clara de tipos de vínculo
- ✅ Rastreabilidade total (cada vínculo citado com evidência)
- ✅ Detecção de lacunas (onde investigação deve aprofundar)

---

## 🔧 A Solução: Taxonomia + Força + Rastreabilidade

Combine 3 elementos estratégicos:

1. **Taxonomia de Vínculos** — Classificar cada relação em categoria pré-definida
2. **Força Diferenciada** — Marcar DIRETA (explícito) vs INDIRETA (intermediária)
3. **Rastreabilidade** — Citar fonte exata para cada vínculo

---

## 💡 Por Que Funciona

Três mecanismos trabalham juntos para resolver o caos investigativo:

**1. Taxonomia ordena o caos**
- Redes com muitos envolvidos geram centenas de relações
- 7 categorias pré-definidas eliminam ambiguidade
- Mesma estrutura funciona para qualquer caso

**2. Força diferencia confiança**
- DIRETA = afirmação está literalmente no texto
- INDIRETA = requer lógica dentro da mesma frase
- Investigador sabe o que é certo vs. provável

**3. Rastreabilidade torna verificável**
- Cada vínculo cita sua fonte exata
- Saída é auditável (não há "eu achei que...")
- Qualquer pessoa pode conferir contra original

**Resultado na prática:**
- Dados desordenados → **CSV estruturado**
- Ambiguidades → **Marcadas com clareza**
- Afirmações → **Sempre com origem**
- Rede complexa → **Visualizável em i2 ou software similar**

---

## 📋 Componentes da Técnica

### 1. Taxonomia de Vínculos (7 Tipos)

Cada vínculo cabe em **exatamente uma** categoria:

- **COLEGUISMO** — Relação profissional/trabalho
  - Exemplo: "trabalha com", "supervisionava", "assessora de"
  
- **INTERMEDIAÇÃO** — Mediação/facilitação de negócio
  - Exemplo: "intermediou abertura de conta", "facilitou contato"
  
- **TRANSAÇÃO** — Troca, pagamento, entrega
  - Exemplo: "recebeu documentos", "transferência de dinheiro"
  
- **COMUNICAÇÃO** — Contato direto (ligação, conversa, mensagem)
  - Exemplo: "ligou para", "enviou WhatsApp", "recebeu orientação"
  
- **PARENTESCO** — Família ou laço pessoal
  - Exemplo: "amiga de infância", "esposa", "primo"
  
- **ACOMPANHAMENTO** — Presença conjunta, encontro
  - Exemplo: "estiveram juntos", "frequentam mesmo local", "fizeram viagem"
  
- **FACILITAÇÃO ILÍCITA** — Envolvimento em ato criminoso
  - Exemplo: "falsificou documento", "ocultou evidência", "ajudou fraude"

**Regra:** Use exatamente um tipo por vínculo. Se ambíguo, marque como INDIRETA.

### 2. Força (Certeza do Vínculo)

- **DIRETA** — Vínculo está literalmente expresso entre as pessoas na frase
  - Exemplo: "João trabalha com Maria" (COLEGUISMO DIRETA)
  
- **INDIRETA** — Vínculo é textual mas depende de relação intermediária explícita na mesma frase
  - Exemplo: "João intermediou contato com Maria" (vínculo entre João e intermediário é claro, mas entre João e Maria é inferência da mesma frase)

**Regra:** Não use inferências externas à frase. Se precisar sair da frase, é especulação.

### 3. Rastreabilidade (Evidência Citada)

Cada vínculo deve citar a evidência exata — a citação literal da frase original.

**Exemplo:**
- ❌ "João trabalha com Maria" (genérico)
- ✅ "recebeu pessoalmente os documentos falsificados" (citação exata)

---

## 🔄 Procedimento (Passo a Passo)

1. **Atribua Persona Especializada**
   - "Você é analista de inteligência especializado em mapeamento de redes"
   - Define rigor e precisão esperados

2. **Processe Frase por Frase**
   - Cada frase = uma ou mais linhas CSV
   - Ordem importa para rastreabilidade

3. **Extraia Vínculos DIRETOS Primeiro**
   - Antes de qualquer inferência
   - Explícitos apenas

4. **Classifique em Taxonomia**
   - Exatamente um tipo por vínculo
   - Se não se encaixa, marque [SEM VÍNCULO]

5. **Marque Força (DIRETA/INDIRETA)**
   - Literal vs depende de intermediário

6. **Cite Evidência Literal**
   - Citação exata da frase original

7. **Gere CSV**
   - Formato estruturado, validado, sem comentários

---

## 📖 Exemplo Prático Completo

### Passo 1: Prepare os Dados

**Arquivo de dados:**

**Formato:** Múltiplas frases numeradas descrevendo um caso com muitos envolvidos  
**Contexto:** Rede investigativa com vínculos complexos e múltiplos tipos de relação

```
Frase 1: Roberto Mendes é sócio da instituição financeira desde 2018 e trabalha 
diretamente com o gerente de operações Carlos Henrique.

Frase 2: Carlos Henrique intermediou a abertura de contas em nome de terceiros 
entre janeiro e março de 2024.

Frase 3: Patricia Gonçalves, assessora de Carlos, recebeu pessoalmente documentos 
de um courier identificado como João da Silva em 15/02/2024.

[... continue com as frases seguintes descrevendo outros vínculos ...]
```

### Passo 2: Aplique o Prompt

**Prompt:** 

```
Você é um ANALISTA DE INTELIGÊNCIA especializado em mapeamento de redes.

INSTRUÇÃO:
Para CADA frase no arquivo anexado abaixo, identifique TODAS as pessoas 
e TODOS os vínculos EXPLÍCITOS.

PASSO 1: Processe cada frase sequencialmente.
PASSO 2: Extraia vínculos DIRETOS antes de qualquer inferência.
PASSO 3: Não invente pessoas, vínculos, datas ou relações.
PASSO 4: Pessoas sem nome completo: use [PESSOA NÃO IDENTIFICADA]
PASSO 5: Se sem vínculo interpessoal explícito, registre [SEM VÍNCULO]

TIPOS DE VÍNCULO (use exatamente um):
- COLEGUISMO (trabalho/relação profissional)
- INTERMEDIAÇÃO (mediação/facilitação)
- TRANSAÇÃO (troca, pagamento, entrega)
- COMUNICAÇÃO (ligação, conversa, mensagem)
- PARENTESCO (família ou laço pessoal)
- ACOMPANHAMENTO (presença conjunta)
- FACILITAÇÃO ILÍCITA (envolvimento em ato criminoso)

FORÇA:
- DIRETA = vínculo está expresso literalmente
- INDIRETA = depende de relação intermediária explícita na mesma frase

FORMATO OBRIGATÓRIO (CSV):
Frase,Pessoa A,Tipo,Pessoa B,Força,Evidência

ARQUIVO ANEXADO:
[Cole o arquivo TESTE_TOPICO2_DADOS_VINCULOS.md aqui]

EXECUTAR.
```

### Passo 3: Execute

**No Claude Code ou Claude Chat:**
```bash
cole prompt + anexe arquivo de dados
```

### Passo 4: Resultado Esperado

O modelo retorna CSV estruturado e verificável:

```csv
"Frase","Pessoa A","Tipo","Pessoa B","Força","Evidência"
"1","Roberto Mendes","COLEGUISMO","Carlos Henrique","DIRETA","trabalha diretamente com o gerente de operações Carlos Henrique"
"2","Carlos Henrique","INTERMEDIAÇÃO","[PESSOA NÃO IDENTIFICADA]","DIRETA","intermediou a abertura de contas em nome de terceiros"
"3","Patricia Gonçalves","COLEGUISMO","Carlos Henrique","DIRETA","Patricia Gonçalves, assessora de Carlos"
"3","Patricia Gonçalves","TRANSAÇÃO","João da Silva","DIRETA","recebeu pessoalmente documentos de um courier identificado como ""João da Silva"""
[... mais linhas seguindo o mesmo padrão ...]
```

**Características do output:**
- Cada linha representa um vínculo verificável
- Força (DIRETA/INDIRETA) diferencia certeza de inferência
- Evidência permite rastreamento direto à fonte original
- Lacunas marcadas ([PESSOA NÃO IDENTIFICADA]) indicam onde investigação deve aprofundar

---

## 📊 Análise do Resultado

### Rede Identificada

Exemplo de padrão revelado:

```
Roberto Mendes ────┐
                   ├──→ Carlos Henrique ←──┬──→ Patricia Gonçalves
                   │                       │
                   │                    [INTERMEDIAÇÃO]
                   │                       
                   │
                   └──→ João da Silva ←──┬──→ Marisa Oliveira
                                         │
                                      [COLEGUISMO]
```

### Indicadores Críticos

- Carlos é elo central (posição estratégica)
- Intermediou operações ilícitas
- Patricia (assessora) participou da execução operacional
- João integrado ao esquema como executor

### Lacunas Críticas

- Quem são os terceiros cujos nomes foram utilizados
- Quem realizou falsificação de documentos
- Relação entre Marisa e Carlos (não explícita)
- Origem e destino dos recursos financeiros

### Próximas Investigações

1. Identificar terceiros cujos dados foram usados
2. Rastrear cadeia de falsificação documental
3. Verificar possível vínculo entre operadores indiretos (Marisa/Carlos)
4. Mapear fluxo de recursos entre envolvidos

---

## ✅ Por Que Este Método Funciona

| Elemento | Benefício |
|----------|-----------|
| **Tipos explícitos (7 categorias)** | Diferencia coleguismo de transação de parentesco |
| **Força (DIRETA/INDIRETA)** | Marca certeza vs. hipótese |
| **Evidência citada** | Verificável contra frase original |
| **Lacunas marcadas** | Indica onde investigação deve aprofundar |
| **Formato CSV** | Importável em software (i2, Palantir, etc.) |
| **Sem comentários** | Saída limpa, estruturada, auditável |

---

## ⚠️ Limitações Importantes

**NÃO inferir criminosidade:**
- ❌ "José é corrupto" — não está dito
- ❌ "Marisa é especialista em falsificação" — apenas intermediou uma vez
- ❌ "Rede internacional de falsificação" — pura especulação

**Marcar como INDIRETA:**
- Relações que são deduções lógicas mas não explícitas
- Se precisa sair da frase para conectar, é inferência externa (proibida)

**Exemplo de erro comum:**
- ✅ CORRETO: "João trabalha com Maria" (COLEGUISMO DIRETA)
- ❌ ERRADO: "João talvez conspire com Maria" (não está dito, especulação)

---

## 🎓 Aprendizado para o Aluno

Ao final, o aluno entende:
- ✅ Como estruturar redes complexas mantendo fidelidade aos dados
- ✅ Como diferenciar fatos explícitos de inferências
- ✅ Como gerar output auditável e verificável
- ✅ Como exportar para análise em software especializado
- ✅ Como identificar lacunas e orientar investigação futura

**Resultado prático:** Dados caóticos transformados em CSV estruturado, importável em i2 Analysts Notebook ou software de grafos, revelando padrões e indicando próximas ações investigativas.
---