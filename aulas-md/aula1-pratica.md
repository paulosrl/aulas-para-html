# Plano de Validação dos 5 Prompts – Aula 1
## Execução Manual e Checklist de Resultados

**Data:** 18/04/2026  
**Status:** Pronto para teste manual  
**Objetivo:** Validar cada prompt antes da apresentação ao vivo (20/04)

---

## ROTEIRO DE EXECUÇÃO

Copie cada prompt abaixo para Claude (chat.claude.com) ou ChatGPT, execute, e compare o resultado com o **Resultado Esperado** documentado. Marque ✅ se o resultado corresponde ou ⚠️ se há desvios.

---

## PROMPT 1: Zero-shot Básico – Extração de Datas e Locais

### Instruções de Teste
1. Copie o prompt completo abaixo
2. Cole em Claude/ChatGPT
3. Pressione Enter
4. Compare a resposta com a seção **Resultado Esperado**

### Prompt Completo (Copiar-Colar)

```
Você é um analista investigativo especializado em fraudes.

Leia o depoimento abaixo e extraia uma lista numerada com TODAS as datas, horários e locais mencionados.

Para cada item, incluir:
1. Data/horário/local encontrado
2. Sentença exata do texto original

---DEPOIMENTO---
Eu estava em casa no dia 10 de abril, por volta das 19 horas, quando recebi uma ligação do meu colega João. Ele disse que tinha visto o suspeito saindo do banco às 18:30. Eu fui até a delegacia no dia 11, de manhã, e prestei depoimento. Depois, em 15 de abril, recebi outra ligação, dessa vez de um inspetor, que disse ter mais uma informação. Fomos nos encontrar no café da Avenida Paulista às 15 horas.
---FIM---
```

### Checklist de Resultado

A resposta esperada deve conter **pelo menos** os 6 itens abaixo:

- [ ] **10 de abril, 19 horas** (casa) — Sentença citada corretamente
- [ ] **18:30** (banco) — Sentença citada corretamente  
- [ ] **11 de abril** (delegacia) — Sentença citada corretamente
- [ ] **15 de abril, 15 horas** (café da Avenida Paulista) — Sentença citada corretamente
- [ ] **Local: delegacia** — Mencionado com data
- [ ] **Local: café da Avenida Paulista** — Mencionado com horário

### Avaliação

| Critério | Status | Notas |
|----------|--------|-------|
| Extrai todas as 6 informações? | [ ] Sim / [ ] Não | |
| Cita sentença exata (não parafraseia)? | [ ] Sim / [ ] Não | |
| Usa formato estruturado (lista numerada)? | [ ] Sim / [ ] Não | |
| **APROVADO?** | [ ] ✅ Sim / [ ] ⚠️ Com ressalvas | |

---

## PROMPT 2: Few-shot com Exemplos – Formatação de Cronologia

### Instruções de Teste

1. Copie o prompt completo abaixo
2. Cole em Claude/ChatGPT
3. Pressione Enter
4. **Importante:** Compare este resultado com o resultado do PROMPT 1
   - Qual é mais estruturado?
   - Qual segue melhor o padrão?

### Prompt Completo (Copiar-Colar)

```
Você é um analista investigativo especializado em reconstrução de eventos.

Extraia a cronologia de eventos de um depoimento. Use EXATAMENTE este formato:

---EXEMPLOS---

EXEMPLO 1:
Entrada: "Fui para a casa do João em 5 de março. Lá ele me mostrou uns documentos. Depois fomos ao banco às 14h."
Saída:
- 5 de março, horário não especificado: ir para casa do João
- 5 de março, 14 horas: ir ao banco

EXEMPLO 2:
Entrada: "O suspeito ligou para mim no dia 2 de janeiro. Eu não atendi. No dia 3, ele ligou novamente."
Saída:
- 2 de janeiro: suspeito ligou
- 3 de janeiro: suspeito ligou novamente

---FIM DOS EXEMPLOS---

Agora extraia do depoimento abaixo, USANDO O MESMO FORMATO:

---DEPOIMENTO---
Eu estava em casa no dia 10 de abril, por volta das 19 horas, quando recebi uma ligação do meu colega João. Ele disse que tinha visto o suspeito saindo do banco às 18:30. Eu fui até a delegacia no dia 11, de manhã, e prestei depoimento. Depois, em 15 de abril, recebi outra ligação, dessa vez de um inspetor, que disse ter mais uma informação. Fomos nos encontrar no café da Avenida Paulista às 15 horas.
---FIM---
```

### Resultado Esperado

Resposta estruturada seguindo exatamente o padrão dos exemplos:

```
- 10 de abril, 19 horas: recebi ligação do colega João
- 10 de abril, 18:30 (relatado por João): suspeito saindo do banco
- 11 de abril, manhã: fui à delegacia e prestei depoimento
- 15 de abril: recebi ligação do inspetor
- 15 de abril, 15 horas: encontro no café da Avenida Paulista
```

### Avaliação Comparativa (PROMPT 1 vs PROMPT 2)

| Aspecto | PROMPT 1 (Zero-shot) | PROMPT 2 (Few-shot) | Qual é melhor? |
|---------|-----|-----|---|
| **Consistência de formato** | [ ] | [ ] | [ ] PROMPT 2 |
| **Segue padrão fornecido** | [ ] | [ ] | [ ] PROMPT 2 |
| **Menos variações** | [ ] | [ ] | [ ] PROMPT 2 |
| **Estrutura temporal clara** | [ ] | [ ] | [ ] PROMPT 2 |

**Conclusão esperada:** Few-shot (PROMPT 2) deve ser significativamente mais estruturado que Zero-shot (PROMPT 1).

---

## PROMPT 3: Role Prompting – Perito Criminal Analisando Fraude

### Instruções de Teste

1. Copie o prompt completo abaixo
2. Cole em Claude/ChatGPT
3. Pressione Enter
4. **Avalie o tom e profundidade:** A resposta parece vir de um especialista com 15 anos de experiência?

### Prompt Completo (Copiar-Colar)

```
Você é um perito criminal especializado em análise de fraudes imobiliárias. 
Você tem 15 anos de experiência investigando documentos falsificados.

Leia o relato de vítima abaixo e responda:
1. Quais são os SINAIS DE ALERTA de falsificação que você identifica?
2. Em que SEQUÊNCIA os eventos ocorreram?
3. Que EVIDÊNCIAS FÍSICAS você procuraria?

Responda como especialista (técnico, objetivo, citando referências de sua experiência).

---RELATO---
Prestei queixa sobre falsificação de documentos. No dia 2 de janeiro de 2024, descobri que meu CPF foi usado para abrir uma conta bancária num banco no Itaim. O gerente confirmou que a documentação foi entregue no dia 30 de dezembro de 2023. Pedi que ele me mostrasse cópias. Vi que o RG era meu, mas a assinatura e a foto eram diferentes. O gerente passou o contato de um colega dele, o Sr. José, que teria intermediado. Quando entrei em contato, Sr. José disse que uma tal Marisa teria entregue os documentos. Marisa teria dito que conhecia um tabelião em Santos que facilitava a falsificação.
---FIM---
```

### Checklist de Avaliação

- [ ] **Sinais de alerta:** Identifica anomalias (assinatura diferente, foto diferente, cadeia de intermediários)?
- [ ] **Sequência:** Reconstrói ordem cronológica dos eventos?
- [ ] **Evidências:** Sugere CCTV, registros bancários, contatos para investigação?
- [ ] **Tom especialista:** Resposta é técnica, não genérica?
- [ ] **Referências:** Cita padrões de fraude conhecidos ou comportamentos criminosos?

### Avaliação

| Critério | Presença | Qualidade |
|----------|----------|-----------|
| 3 seções claramente separadas | [ ] | |
| Análise técnica (não genérica) | [ ] | |
| Sugestões de evidências físicas | [ ] | |
| **APROVADO?** | [ ] Sim | |

---

## PROMPT 4: Controle de Escopo – Analisando Apenas Um Período

### Instruções de Teste

1. Este prompt é **teórico** — não há dados anexados
2. O objetivo é testar se o modelo **respeita restrições de escopo**
3. Para testar na prática, use dados reais (ex: múltiplas transações de diferentes datas)

### Dados de Teste (Use este exemplo)

```
---DADOS---
Janeiro 2024:
- 5/1: João transfere R$500 para Marisa
- 10/1: Marisa abre conta bancária com documentos falsos
- 20/1: Transferência de R$2000 (fora de escopo)

Abril 2024:
- 1/4: Transação suspeita de R$1000
- 10/4: Nova transferência de R$500 entre João e Marisa
- 15/4: Investigador recebe denúncia anônima
- 20/4: Transferência adicional (fora de escopo)

Junho 2024:
- 5/6: Conta encerrada
---FIM---
```

### Prompt Completo (Copiar-Colar)

```
Você é analista de fraudes.

Analise APENAS eventos que ocorreram entre 1º e 15 de abril de 2024.
Não considere eventos anteriores ou posteriores.

Para este período, extraia:
1. Transações suspeitas
2. Pessoas envolvidas
3. Possíveis motivos

Se um evento não pode ser datado neste período, indique [FORA DO ESCOPO].

---DADOS---
Janeiro 2024:
- 5/1: João transfere R$500 para Marisa
- 10/1: Marisa abre conta bancária com documentos falsos
- 20/1: Transferência de R$2000 (fora de escopo)

Abril 2024:
- 1/4: Transação suspeita de R$1000
- 10/4: Nova transferência de R$500 entre João e Marisa
- 15/4: Investigador recebe denúncia anônima
- 20/4: Transferência adicional (fora de escopo)

Junho 2024:
- 5/6: Conta encerrada
---FIM---
```

### Resultado Esperado

Modelo deve:
- ✅ Incluir eventos 1º–15 de abril (3 eventos)
- ✅ Ignorar eventos de janeiro e junho
- ✅ Marcar transação de 20/4 como [FORA DO ESCOPO]

### Avaliação

| Critério | Status |
|----------|--------|
| Inclui APENAS eventos 1º–15 de abril? | [ ] Sim / [ ] Não |
| Marca eventos fora de escopo? | [ ] Sim / [ ] Não |
| Modelo não especula além do período? | [ ] Sim / [ ] Não |
| **APROVADO?** | [ ] Sim |

---

## PROMPT 5: Validação Crítica – Checklist de Confiabilidade

### Instruções de Teste

1. Este é o prompt mais importante — testa capacidade de **auto-crítica**
2. Copie o prompt abaixo
3. Compare: o modelo consegue detectar alucinações?

### Prompt Completo (Copiar-Colar)

```
Você é analista investigativo com responsabilidade de validação crítica.

Leia esta resposta de análise e marque cada afirmação como:
✅ VERIFICÁVEL (está explicitamente no texto fornecido)
⚠️ INFERIDA (dedução lógica, mas não explícita)
❌ ESPECULATIVA (além dos dados)

Depois, apontar qual nível de confiança você tem em cada afirmação (ALTA/MÉDIA/BAIXA).

---RESPOSTA DO ANALISTA ANTERIOR---
"O suspeito saiu do banco às 18:30 com dinheiro em mãos e depois transferiu o dinheiro para uma conta no exterior."
---FIM---

DEPOIMENTO ORIGINAL:
"Ele disse que tinha visto o suspeito saindo do banco às 18:30."
```

### Resultado Esperado

```
✅ VERIFICÁVEL: "Suspeito saiu do banco às 18:30"
   Justificativa: Explícito no depoimento
   Confiança: ALTA

❌ ESPECULATIVA: "Com dinheiro em mãos"
   Justificativa: Não mencionado no depoimento
   Confiança: BAIXA

❌ ESPECULATIVA: "Transferiu para conta no exterior"
   Justificativa: Pura invenção. Não há informação sobre transferências.
   Confiança: MUITO BAIXA (alucinação detectada)
```

### Avaliação Crítica

| Afirmação | Classificação Esperada | Classificação Real | Match? |
|-----------|------------------------|-------------------|--------|
| "Saiu do banco às 18:30" | ✅ VERIFICÁVEL | [ ] | [ ] ✅ |
| "Com dinheiro em mãos" | ❌ ESPECULATIVA | [ ] | [ ] ✅ |
| "Transferiu para exterior" | ❌ ESPECULATIVA | [ ] | [ ] ✅ |

**Sucesso esperado:** Modelo marca todas as 3 afirmações corretamente.

---

## RESUMO EXECUTIVO

| # | Prompt | Objetivo | Prioridade | Status |
|---|--------|----------|-----------|--------|
| 1 | Zero-shot | Baseline sem exemplos | 🔴 Alta | [ ] Testado |
| 2 | Few-shot | Comparar com #1 | 🔴 Alta | [ ] Testado |
| 3 | Role Prompting | Mostrar impacto de persona | 🟡 Média | [ ] Testado |
| 4 | Escopo | Testar limitações | 🟡 Média | [ ] Testado |
| 5 | Validação Crítica | Auto-crítica de IA | 🔴 Alta | [ ] Testado |

---

## Instruções Finais

### Como Executar

1. **Duração:** ~30 minutos para testar todos os 5
2. **Ferramenta:** Use Claude (chat.claude.com) ou ChatGPT
3. **Documentação:** Preencha os checklists acima conforme testa
4. **Desvios:** Se resultado diferir do esperado, anote o desvio e a razão

### Se Encontrar Problemas

- **Prompt muito vago?** Refine e re-teste
- **Modelo não segue instrução?** Teste em ferramenta diferente (ChatGPT vs Claude)
- **Resultado inconsistente?** Pode ser variação normal — teste 2–3 vezes

### Próximo Passo

Após validar todos os 5 prompts:
- [ ] Todos aprovados ✅
- [ ] Alguns com ressalvas ⚠️
- [ ] Necessitam ajustes 🔧

Informe o status para proceder com **Aula 2** ou **refinamentos de Aula 1**.

---

**Documento gerado em:** 18/04/2026  
**Autor:** Claude (validação de prompts)  
**Próxima ação:** Aguardando resultados de teste manual
