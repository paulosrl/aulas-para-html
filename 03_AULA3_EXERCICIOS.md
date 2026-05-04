# Exercício Prático Intensivo – Aula 3
## Aplicação Integrada de Técnicas

---

## Estrutura do Exercício

**Nível:** Avançado (integração de 4 técnicas)  
**Tempo em Aula:** 12 minutos (duplas completam TAREFAS 1–2)  
**Tempo Extra/Casa:** 6–8 minutos (TAREFAS 3–5 são opcionais)  
**Objetivo:** Aplicar extração, reconhecimento de vínculos, reconstrução cronológica e validação crítica em caso realista.  
**Formato:** Duplas  
**Entrega Aula:** Estruturação + Mapeamento de Vínculos  
**Entrega Casa (Opcional):** Timeline + Validação + Relatório

---

## CENÁRIO

Você é analista investigativo de órgão de combate a fraudes.

Recebeu um conjunto de documentos sobre **operação de falsificação de documentação bancária**. Os documentos chegaram desorganizados e incompletos. Sua tarefa é:

1. **Estruturar informações** (datas, nomes, locais)
2. **Mapear vínculos** entre envolvidos
3. **Reconstruir timeline** de eventos
4. **Validar criticamente** antes de usar em relatório oficial

---

## DATASET COMPLETO

### DOCUMENTO 1: Depoimento de Vítima (Parcial)

```
DEPOIMENTO DE CLARA SILVA

Sou Clara Silva, CPF XXX.XXX.XXX-XX, residente em São Paulo.

Descobri em 15 de janeiro de 2024 que meu CPF foi utilizado para abrir 
uma conta corrente no Banco Credito Legal, agência Pinheiros, São Paulo. 
A conta foi aberta em 8 de janeiro de 2024 segundo informações do banco.

Recebi ligação do gerente Sr. Rafael (não obtive sobrenome) na data de 
20 de janeiro, informando sobre a conta. Ele perguntou se tinha autorizado 
aquela abertura. Falei que não. Sr. Rafael informou que a documentação 
(RG e comprovante de residência) foi entregue por uma pessoa que se 
apresentou como representante meu, chamada Patricia Mendes.

Quando pedi cópias para análise, vi que:
- RG era meu documento original (não falsificado, surpreendentemente)
- Comprovante de residência era falso (endereço parcialmente correto, 
  assinatura não minha)
- Há suspeita de que alguém roubou meu RG de uma carteira em dezembro

Liguei para São Paulo (onde moro) em 21 de janeiro para prestar queixa 
na delegacia sobre roubo de documentos. Fui informada que já existia 
queixa anterior de pessoa com mesmo sobrenome (Silva) em 18 de janeiro.
```

---

### DOCUMENTO 2: Depoimento de Gerente Bancário

```
DEPOIMENTO DE RAFAEL TORRES, GERENTE

Trabalho como gerente há 7 anos no Banco Credito Legal, agência Pinheiros.

Em 8 de janeiro de 2024, recebi solicitação de abertura de conta. 
A pessoa se apresentou como Patricia Mendes (mostrando RG de Patricia Mendes, 
CNH de Patricia Mendes) afirmando ser representante/procuradora de Clara Silva. 
Apresentou documentação:
- RG original em nome de Clara Silva (parecia legítimo)
- Comprovante de residência em nome de Clara Silva (assinado por "Clara Silva")
- Procuração assinada por Clara Silva autorizando Patricia como representante

Na época, não identifiquei falsificações. Patricia abriu conta com limite 
de R$ 5.000.

Em 20 de janeiro, recebi ligação de Clara Silva questionando a abertura. 
Clara nega ter autorizado qualquer procuração. Informei à superintendência 
do banco sobre suspeita de fraude em 21 de janeiro.

Nota: Patricia Mendes nunca retornou à agência após 8 de janeiro.
```

---

### DOCUMENTO 3: Registros de Movimentação Bancária

```
MOVIMENTAÇÃO DA CONTA — CLARA SILVA / PATRICIA MENDES

Data de Abertura: 8 de janeiro de 2024
Limite Concedido: R$ 5.000

MOVIMENTAÇÕES:
- 8/1/2024, 14h32: Saque de R$ 2.500 (terminal ATM, Pinheiros)
- 9/1/2024, 09h15: Saque de R$ 1.200 (terminal ATM, Centro)
- 10/1/2024, 16h45: Saque de R$ 1.000 (terminal ATM, Consolação)
- 12/1/2024, 11h20: Tentativa de transferência para conta externa 
                    (BLOQUEADA por sistema de segurança — limite excedido)
- 15/1/2024, 08h00: Conta bloqueada por solicitação de vítima

SALDO FINAL: -R$ 4.700 (limite excedido)

Observação: Todos os saques realizados em São Paulo (zona central/oeste).
```

---

### DOCUMENTO 4: Registro de Queixa na Delegacia

```
BOLETIM DE OCORRÊNCIA — ROUBO E FALSIFICAÇÃO

BO 123456/2024 — Registrada em 18 de janeiro de 2024

Queixoso: MARIA SILVA (CPF diferente de Clara Silva — parente?)
Tipo: Roubo de documentos pessoais + Falsificação de procuração
Local: Não especificado (possível zona central de São Paulo)

Descrição breve: "Minha carteira foi roubada em São Paulo contendo 
documentos pessoais. Suspeito que meus documentos estejam sendo usados 
para fraude."

Situação: Em andamento

---

NOTA INVESTIGATIVA POSTERIOR (22 de janeiro):
Detectado padrão: BO 123456/2024 (Maria Silva) e reclamação de Clara Silva 
podem estar conectados. Maria e Clara têm mesmo sobrenome. Possível que 
mesmo criminoso tenha roubado documentos de ambas?
```

---

## INSTRUÇÕES PARA DUPLAS

### ✅ TAREFAS EM AULA (12 minutos)

**Duplas completam TAREFAS 1–2 durante a aula (20h53–21h05)**

---

### TAREFA 1: Estruturação e Extração (5 min) — ✅ EM AULA

Leia os 4 documentos acima e crie uma **tabela de informações estruturadas**:

```
| DATA | HORÁRIO | EVENTO | PESSOA(S) | LOCAL | TIPO DE INFORMAÇÃO |
|------|---------|--------|-----------|-------|-------------------|
```

**O que extrair:**
- Todas as datas/horários mencionados
- Pessoas envolvidas e papéis
- Locais
- Tipo: ROUBO / FALSIFICAÇÃO / ABERTURA DE CONTA / SAQUE / TRANSFERÊNCIA / INVESTIGAÇÃO

**Critério:** Use APENAS informações explícitas. Se não houver data, indique [DATA NÃO ESPECIFICADA].

---

### TAREFA 2: Mapeamento de Vínculos (5 min) — ✅ EM AULA

Construa uma **rede de relacionamento** em texto simples:

```
PESSOA A ↔ [TIPO DE VÍNCULO] ↔ PESSOA B
Força: [DIRETA/INDIRETA]
Evidência: [Citação resumida]
```

**Vínculos a procurar:**
- Quem conhece quem?
- Quem fez transações com quem?
- Quem se comunicou com quem?
- Quem estava em qual local em que data?

---

### ⏳ TAREFAS OPCIONAIS / ATIVIDADE EM CASA (6–8 minutos)

**Duplas completam TAREFAS 3–5 como atividade extra / homework**  
**Trazer resultados para Aula 4 (11/11) se realizarem**

---

### TAREFA 3: Timeline Cronológica (4 min) — ⏳ EM CASA

Reconstrua a **sequência de eventos** em ordem temporal:

```
[DATA] — [HORÁRIO] → [EVENTO]
[LACUNA: X dias] — [O QUÊ está faltando?]
```

---

### TAREFA 4: Validação Crítica (2 min) — ⏳ EM CASA

Para cada informação IMPORTANTE que sua dupla extraiu, classifique como:
- ✅ VERIFICÁVEL (explícito em documento)
- ⚠️ INFERIDO (dedução, mas suportada)
- ❌ ESPECULATIVO (além dos dados)

---

### TAREFA 5: Síntese em Relatório (2 min) — ⏳ EM CASA

Redija **1 parágrafo executivo** (máximo 5 linhas) resumindo:
- O que aconteceu?
- Quem estava envolvido?
- Qual é o próximo passo investigativo?

---

## GABARITO COMENTADO

### TAREFA 1: Estruturação de Informações

**Resposta esperada (tabela abreviada):**

| DATA | HORÁRIO | EVENTO | PESSOA(S) | LOCAL | TIPO |
|------|---------|--------|-----------|-------|------|
| [DATA NÃO ESPECIFICADA] | — | Roubo de carteira com documentos | Desconhecido → Maria/Clara | São Paulo (zona não especificada) | ROUBO |
| 8 de janeiro de 2024 | [HORÁRIO NÃO ESP.] | Abertura de conta com procuração falsa | Patricia Mendes (apresentação) + Clara Silva (procuradora falsa) | Banco Credito Legal, agência Pinheiros | FALSIFICAÇÃO + ABERTURA |
| 8/1/2024 | 14h32 | Saque em ATM | Patricia Mendes (presumida) | Pinheiros, São Paulo | SAQUE |
| 9/1/2024 | 09h15 | Saque em ATM | Patricia Mendes (presumida) | Centro, São Paulo | SAQUE |
| 10/1/2024 | 16h45 | Saque em ATM | Patricia Mendes (presumida) | Consolação, São Paulo | SAQUE |
| 12/1/2024 | 11h20 | Tentativa de transferência (bloqueada) | Patricia Mendes (presumida) | — | TRANSFERÊNCIA (FRACASSADA) |
| 15 de janeiro de 2024 | 08h00 | Vítima descobre fraude | Clara Silva | — | DESCOBERTA |
| 15/1/2024 | [HORA NÃO ESP.] | Vítima recebe ligação do gerente | Rafael Torres ↔ Clara Silva | Telefone | COMUNICAÇÃO |
| 20 de janeiro de 2024 | — | Gerente liga para vítima confirmando fraude | Rafael Torres ↔ Clara Silva | Telefone | COMUNICAÇÃO |
| 18 de janeiro de 2024 | — | Queixa de Maria Silva na delegacia sobre roubo | Maria Silva | Delegacia de São Paulo | QUEIXA |
| [DATA NÃO ESPECIFICADA] | — | Vítima vai à delegacia prestar queixa | Clara Silva | Delegacia de São Paulo | QUEIXA |
| 21 de janeiro de 2024 | — | Gerente informa banco sobre fraude | Rafael Torres → Superintendência | Banco Credito Legal | NOTIFICAÇÃO |

**Avaliação:**
- ✅ Cronologia clara
- ✅ Pessoas e papéis identificados
- ✅ Lacunas marcadas [NÃO ESPECIFICADO]
- ✅ Tipos de evento diferenciados

---

### TAREFA 2: Mapeamento de Vínculos

**Resposta esperada:**

```
REDE DE VÍNCULOS:

1. Patricia Mendes ↔ FRAUDE ↔ Clara Silva
   Força: DIRETA
   Evidência: "pessoa se apresentou como representante, apresentando procuração assinada por Clara Silva"
   
2. Patricia Mendes ↔ ROUBO [INFERIDO] ↔ Maria Silva
   Força: INDIRETA [VÍNCULO INFERIDO]
   Evidência: "BO 123456/2024 (Maria Silva) e reclamação de Clara Silva podem estar conectados"
   Nota investigativa posterior sugere padrão
   
3. Clara Silva ↔ VÍTIMA ↔ Patricia Mendes
   (mesma relação que acima)

4. Rafael Torres (Gerente) ↔ RECEBIMENTO ↔ Patricia Mendes
   Força: DIRETA
   Evidência: "recebi solicitação de abertura de conta... a pessoa se apresentou como Patricia Mendes"
   
5. Rafael Torres ↔ COMUNICAÇÃO ↔ Clara Silva
   Força: DIRETA
   Evidência: "ligação de Clara Silva questionando a abertura" (20/1)
   
6. Clara Silva ↔ PARENTE PRESUMIDO ↔ Maria Silva
   Força: INDIRETA [VÍNCULO INFERIDO]
   Evidência: "ambas têm mesmo sobrenome Silva... possível que mesmo criminoso..."
   Nota: Falta confirmação

7. Patricia Mendes ↔ MOVIMENTAÇÃO ↔ Conta de Clara Silva (Banco Credito Legal)
   Força: DIRETA (movimentações em ATM presumem cartão)
   Evidência: Saques e tentativa de transferência após abertura em 8/1
```

**Avaliação:**
- ✅ Vínculos principais identificados
- ✅ Força (DIRETA/INDIRETA) diferenciada
- ✅ Lacunas reconhecidas (Maria Silva parente de Clara? Confirmado?)

---

### TAREFA 3: Timeline Cronológica

**Resposta esperada:**

```
SEQUÊNCIA DE EVENTOS:

[DATA INCERTA — December de 2023]
→ Roubo de carteira com documentos pessoais (presumível ocorrência antes de uso)

[LACUNA: ~2 semanas]

[DATA CERTA] 8 de janeiro de 2024, [HORA NÃO ESPECIFICADA]
→ Patricia Mendes apresenta-se ao Banco Credito Legal
→ Apresenta documentação incluindo procuração falsificada
→ Abre conta corrente em nome de Clara Silva
→ Recebe limite de R$ 5.000

[MESMO DIA] 8/1/2024, 14h32
→ Patricia Mendes realiza saque de R$ 2.500 em ATM (Pinheiros)

[PRÓXIMOS DIAS] 9/1 (09h15), 10/1 (16h45)
→ Saques sucessivos em ATMs diferentes (Centro, Consolação)
→ Total sacado: R$ 3.700

[DATA CERTA] 12 de janeiro de 2024, 11h20
→ Tentativa de transferência para conta externa BLOQUEADA
→ Razão: Limite de R$ 5.000 excedido

[LACUNA: 3 dias]

[DATA PRESUMIDA] 15 de janeiro de 2024, 08h00
→ Clara Silva descobre fraude ao verificar conta

[MESMO DIA] 15/1 (horário não especificado)
→ Clara recebe ligação de Rafael Torres (gerente) confirmando abertura
→ Clara nega ter autorizado procuração

[LACUNA: 3 dias]

[DATA CERTA] 18 de janeiro de 2024
→ Maria Silva presta queixa na delegacia sobre roubo de documentos
→ NOTA: Mesma zona de São Paulo? Mesmo criminoso?

[LACUNA: 2 dias]

[DATA PRESUMIDA] 20 de janeiro de 2024
→ Clara Silva recebe nova ligação de Rafael confirmando conclusões
→ Rafael informa que vai notificar banco

[DATA CERTA] 21 de janeiro de 2024
→ Rafael notifica superintendência do banco sobre fraude
→ Clara Silva presta queixa sobre falsificação (data registrada como após 18/1)

[APÓS 21/1]
→ Investigação em andamento
```

**Avaliação:**
- ✅ Ordem cronológica respeitada
- ✅ Lacunas marcadas e analisadas
- ✅ [INFERIDO] vs [CERTA] diferenciado
- ✅ Padrão de saques progressivos evidente

---

### TAREFA 4: Validação Crítica

**Resposta esperada (amostra):**

| Afirmação | Status | Confiança | Justificativa |
|-----------|--------|-----------|---|
| "Patricia Mendes abriu conta em 8/1/2024" | ✅ VERIFICÁVEL | ALTA | Explícito em depoimento de gerente |
| "Patricia apresentou procuração falsificada" | ✅ VERIFICÁVEL | ALTA | Clara nega ter assinado; procuração não autêntica |
| "Patricia é criminosa profissional" | ❌ ESPECULATIVO | BAIXA | Inferência; poderia ser apenas oportunista |
| "Maria Silva e Clara Silva são parentes" | ⚠️ INFERIDO | MÉDIA | Mesmo sobrenome + padrão; não confirmado |
| "Mesmo criminoso roubou ambas" | ❌ ESPECULATIVO | BAIXA | Hipótese plausível mas sem evidência sólida |
| "Patricia Mendes está em fuga" | ❌ ESPECULATIVO | MUITO BAIXA | Não mencionado; possível mas não suportado |
| "Total defraudado foi R$ 4.700" | ✅ VERIFICÁVEL | ALTA | Conta movimentação + limite |

**Avaliação:**
- ✅ Diferencia VERIFICÁVEL de ESPECULATIVO
- ✅ Protege contra conclusões prematuras
- ✅ Identifica hipóteses para investigação futura

---

### TAREFA 5: Parágrafo Executivo

**Resposta esperada:**

```
SÍNTESE EXECUTIVA:

Entre 8 e 15 de janeiro de 2024, pessoa identificada como Patricia Mendes 
utilizou documentação (incluindo procuração presumivelmente falsificada) para 
abrir conta bancária em nome de Clara Silva no Banco Credito Legal, realizando 
saques sucessivos totalizando R$ 3.700 antes de ser bloqueada. Investigação 
indica possível padrão similar envolvendo vítima adicional (Maria Silva) com 
roubo de documentos em mesma região. Recomenda-se: (1) investigar vínculo entre 
Clara e Maria Silva; (2) localizar Patricia Mendes; (3) analisar CCTV dos ATMs 
utilizados; (4) rastrear documentação forjada (fornecedor de procurações falsas).
```

**Avaliação:**
- ✅ Conciso (5 linhas)
- ✅ Responde: O QUÊ, QUEM, QUANDO
- ✅ Próximos passos indicados (investigação futura)

---

## Critérios de Avaliação da Dupla

| Aspecto | Fraco (0) | Adequado (1) | Bom (2) |
|---------|-----------|-------------|---------|
| **TAREFA 1: Estruturação** | Tabela incompleta ou desorganizada | Tabela presente, informações corretas | Tabela clara, lacunas marcadas, tipos diferenciados |
| **TAREFA 2: Vínculos** | Poucos vínculos identificados | Vínculos principais listados | Todos os vínculos, força diferenciada, inferências marcadas |
| **TAREFA 3: Timeline** | Ordem errada ou lacunas não marcadas | Sequência correta, algumas lacunas | Ordem correta, lacunas analisadas, credibilidade marcada |
| **TAREFA 4: Validação** | Todas as informações acreditadas | Algumas afirmações validadas | Cada afirmação classificada, confiança atribuída |
| **TAREFA 5: Síntese** | Ausente ou incoerente | Presente, mas incompleto | Claro, responde O QUÊ/QUEM/QUANDO, próximos passos |
| **INTEGRAÇÃO** | Técnicas não aplicadas | Algumas técnicas aplicadas | Todas as 4 técnicas integradas sistematicamente |

**Máximo por dupla:** 12 pontos

---

## Notas para Apresentador

### Durante Aula (Tarefas 1–2, 12 min)
- ✅ **Compartilhar os 4 documentos em tela** (já antes de aula começar, ou em slide)
- ✅ Ativar timer de **12 minutos** (alarme em 10 min para avisar faltam 2 min)
- ✅ Ter gabarito (Tarefas 1–2) em segundo monitor ou impresso
- ✅ **Não dê respostas** — circule oferecendo dicas ("Quais técnicas vocês estão usando?")
- ✅ Se dupla terminar cedo (em ~9 min): "Vocês conseguem detectar gaps nos dados?"
- ✅ Se atrasarem: mantenha timing e avance — feedback rápido ao fim
- ⚠️ Foco é em **processo**, não perfeição

### Tarefas 3–5 (Casa)
- 📧 Enviar gabarito completo (TAREFAS 1–5) **após aula**
- 📧 Mencionar que Tarefas 3–5 são **opcionais** (não obrigatórias)
- 💡 Encorajar: "Quem completar todas as 5 tarefas traz para Aula 4 (11/05) — vamos discutir"

---

## Tarefa de Casa

**Para alunos que quiserem aprofundar:**

1. Refine o relatório da dupla com as técnicas de validação crítica
   - Identifique 2-3 afirmações que mereceriam investigação adicional
   - Que tipo de investigação (CCTV, análise de documentos, depoimentos adicionais)?

2. Expanda timeline com "ações investigativas necessárias"
   - Para cada evento-chave, qual evidência corroboraria?

3. Traga **caso anônimo real** de seu trabalho
   - Seu próprio exercício funcionaria para aquele caso?
   - Que desafios apareceriam?

4. **Discussão na Aula 4 (11/05):**
   - Qual técnica foi mais útil?
   - Qual foi mais difícil de aplicar?

