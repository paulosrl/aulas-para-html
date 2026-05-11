## TÓPICO 3: Reconstrução Cronológica de Fatos

### Contexto

Investigações dependem de **entender ordem dos eventos**. Problemas comuns:
- Informações chegam fora de ordem
- Há períodos sem dados (lacunas)
- Datas conflitam entre fontes
- Sequência temporal revela causalidade
A tarefa é **organizar**, **questionar lacunas**, e **apontar contradições** — exatamente o que PROMPT 3 ensina.

### 🔑 Técnica Empregada: Chain-of-Thought + Marcação de Certeza + Validação

**O que:** (1) Force raciocínio passo-a-passo (PASSO 1 → 2 → 3...), (2) diferencie [DATA CERTA] vs [APROXIMADA] vs [INCERTA], (3) valide se sequência é internamente consistente.

**Por que funciona aqui:** Eventos chegam fora de ordem. CoT força ordem sistemática. Marcação diferencia fatos de deduções. Validação detecta contradições antes de conclusions. Lacunas marcadas mostram exatamente onde investigação tem gaps.

---

### Técnica de Prompt: Detalhamento Completo

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

### Estudo de Caso: Fraude Bancária em Rede

Uma rede criminosa coordenada executou um esquema de fraude bancária entre dezembro de 2023 e março de 2024. O crime envolveu abertura de contas falsificadas em nome de três vítimas diferentes, seguida de saques não autorizados. O ponto central deste caso é como a análise cronológica dos fatos permitiu conectar os envolvidos, mapear a sequência de ações e identificar a dinâmica da fraude.

Este é um caso real que representa exatamente o tipo de desafio enfrentado por investigadores modernos: informações fragmentadas, fora de ordem, com datas conflitantes e lacunas críticas. O foco está em organizar esses dados com método para sustentar a apuração e orientar a solução do crime.

---

#### Os Envolvidos

**Criminosos:**
- **Sr. José da Silva** — O operador. Faz as chamadas telefônicas oferecendo crédito pré-aprovado. Obtém os documentos pessoais das vítimas (CPF, RG) enganando-as sobre a suposta oferta de crédito.
- **Marisa Oliveira** — A executora. Usa os documentos fornecidos para abrir contas bancárias falsificadas em nome das vítimas. Depois realiza os saques nas agências ou caixas eletrônicos.

**Vítimas:**
- **Anderson Silva** — Vítima 1. Ligação de Sr. José em 30 de dezembro. Envia documentos em 31 de dezembro. Descobre saque em sua conta em 2 de janeiro.
- **Clara Silva** — Vítima 2. Conta aberta em seu nome em 10 de janeiro. Descobre múltiplos saques em 17 de janeiro (total R$ 3.700).
- **Miguel Santos** — Vítima 3. Descobre saques em 31 de janeiro (total R$ 5.200 em 5 saques diferentes).

**Instituições:**
- **Banco XYZ** — Detecta anomalias quando o gerente Sr. Carlos nota. Tem informação completa em 7 de fevereiro (depoimento + perícia). MAS só alerta a polícia em 20 de fevereiro — 13 dias depois.
- **Polícia Civil** — Recebe denúncia em 20 de fevereiro. Abre inquérito em 22 de fevereiro. Não progride. Polícia Federal assume em 1º de março.

---

#### Como o Crime Funcionou (Sequência Real)

**Dezembro 2023 — Início:**
Sr. José faz ligações para pessoas desconhecidas oferecendo crédito pré-aprovado (golpe clássico). A vítima, confiante, envia seus documentos pessoais.

**Janeiro 2024 — Execução:**
Marisa recebe os documentos e usa-os para abrir contas bancárias em nome das vítimas. Ela não é uma estranha — ela realmente entra na agência, abre contas, e consegue aprovação (falha do banco aqui: documentação falsificada não foi detectada imediatamente).

Marisa então vai aos caixas eletrônicos e saca dinheiro usando os cartões gerados para essas contas falsificadas.

**Três saques documentados:**
- Anderson: saque de R$ 1.500 em 2 de janeiro
- Clara: saque de R$ 2.000 em 11 de janeiro + outros (total R$ 3.700)
- Miguel: cinco saques não autorizados (total R$ 5.200)

**Janeiro-Fevereiro — Descoberta Lenta:**
As vítimas só descobrem quando checam seus extratos bancários. Não é detecção automática. Isso leva dias ou semanas.

Anderson descobre em 2 de janeiro. Clara descobre em 17 de janeiro (15 dias depois). Miguel descobre em 31 de janeiro (29 dias depois).

**Fevereiro — Denúncia e Investigação Falha:**
As vítimas registram boletim de ocorrência. O banco convida todas para depoimento em 5 de fevereiro e recebe depoimento em 7 de fevereiro. Perícia examina os documentos falsificados em 10 de fevereiro. Auditoria interna identifica que TODAS as contas foram abertas por Marisa em 11 de fevereiro.

O banco tem tudo. Tem provas. Tem o padrão (todas as contas abiertas pela mesma pessoa). Tem os dados das vítimas.

**MAS a polícia só descobre em 20 de fevereiro — 13 dias depois.**

Por quê? Ninguém sabe. Aparentemente o banco não alertou imediatamente. Falha de comunicação.

**Março — Sem Progresso:**
Delegacia de Polícia Civil abre inquérito em 22 de fevereiro. Nada acontece pelos próximos 8 dias. Em 1º de março, Polícia Federal assume porque "pode envolver rede interstadual". 

Durante esses 8 dias e depois, Sr. José continua fazendo ligações (última ligação conhecida é ~início de março para novo alvo que recusou).

Marisa desaparece ~meados de fevereiro. Nunca é localizada no caso.

---

#### O Que Precisa Ser Analisado com PROMPT 3

Ler **todos os eventos deste caso**, mas **completamente fora de ordem**. Eventos são:
- Datas de ligações
- Datas de saques
- Datas de descobertas
- Datas de depoimentos
- Datas de análises forenses
- Datas de comunicação entre instituições
- Algumas datas faltando completamente (quando Marisa desapareceu? quando Sr. José fez a última ligação exatamente?)

**A tarefa do PROMPT é:**

1. **Reconstruir a sequência correta** — Colocar os 55 eventos em ordem cronológica, do primeiro ao último.

2. **Identificar lacunas** — Entre o evento A e o evento B, quantos dias passaram SEM informação? Por exemplo:
   - Entre "Clara descobre fraude (17 de janeiro)" e "Clara registra denúncia (30 de janeiro)" há 13 dias. O que Clara fez nesse tempo? Por que esperou?
   - Entre "Banco tem informação completa (7 de fevereiro)" e "Polícia é alertada (20 de fevereiro)" há 13 dias. Por quê?
   - Entre "Inquérito aberto (22 de fevereiro)" e "PF assume (1º de março)" há 8 dias. O que aconteceu?

3. **Detectar contradições** — O caso tem problemas internos:
   - Um evento diz que Marisa saca R$ 1.500 em 4 de janeiro, mas outro evento diz que ela abre a conta em 10 de janeiro. Como saca ANTES de abrir?
   - Marisa desaparece ~meados de fevereiro, mas Sr. José continua ligando em março. Como um desaparece e o outro não?

4. **Formular questões investigativas** — Para cada lacuna, pergunte:
   - Por que existe essa lacuna?
   - O que deveria ter acontecido nesse período?
   - O que o investigador deveria verificar?

**Você NÃO está julgando** ("isso foi negligência"). Você está **perguntando** ("por que isso aconteceu? o que falta saber?").

---

**Prompt de Reconstrução:**
```
Você é um ANALISTA INVESTIGATIVO EXPERIENTE com 15 anos de experiência 
em reconstrução de cronologias para casos complexos de fraude, corrupção 
e crimes financeiros.

Sua especialidade é pegar informações fragmentadas, desorganizadas e muitas 
vezes contraditórias — como você recebe de depoimentos, extratos bancários, 
comunicações e perícias — e transformá-las em uma SEQUÊNCIA TEMPORAL COERENTE 
que revela padrões, lacunas críticas e inconsistências.

Você trabalha para autoridades investigativas que precisam entender:
- O QUÊ aconteceu e em que ordem
- ONDE estão os gaps (informação faltando)
- QUAIS contradições indicam dados errados ou falha de processo
- POR QUÊ certos períodos têm silêncio investigativo

Você é metódico, não faz julgamentos precipitados, e diferencia SEQUÊNCIA 
TEMPORAL (ordem dos eventos) de CAUSALIDADE (relação causa-efeito).

---

PROCEDIMENTO:

PASSO 1: Listar TODAS as datas mencionadas
Extraia cada data ou referência temporal do material fornecido, mantendo 
a classificação original: é uma data exata, uma aproximação, ou é incerta?

PASSO 2: Ordenar cronologicamente
Coloque todos os eventos em sequência do mais antigo para o mais recente.
Marque eventos sem data clara para análise posterior.

PASSO 3: Marcar LACUNAS
Entre cada evento sucessivo, calcule quantos dias passaram sem informação.
- [LACUNA: X dias] = intervalo com duração conhecida
- [LACUNA: ~X dias] = intervalo aproximado

PASSO 4: Classificar CERTEZA de cada data
Para cada evento, classifique como:
- [DATA CERTA] = explicitamente mencionada ("7 de fevereiro")
- [DATA APROXIMADA] = inferida de contexto ("alguns dias depois", "uma semana após")
- [DATA INCERTA] = ambígua ou não mencionada ("data desconhecida")

PASSO 5: Validar ordem e causalidade
Pergunta-se:
- Evento A realmente ocorreu antes de Evento B?
- Há contradições lógicas? (Exemplo: saque antes de abertura de conta?)
- A sequência faz sentido narrativamente?

NOTA IMPORTANTE: Sequência temporal ≠ Causalidade
Exemplo: "Vítima descobriu fraude em 17 de janeiro, polícia foi alertada em 20 de fevereiro"
- SEQUÊNCIA: Verdadeira (um antes do outro)
- CAUSALIDADE: Não há — a descoberta NÃO causou o alerta imediato da polícia

PASSO 6: Formatar timeline reconstituída
Apresente a cronologia em formato claro com:
- Data (classificação)
- Evento
- Lacuna até o próximo evento

PASSO 7: Análise investigativa profunda
Para cada lacuna significativa (> 3 dias), questione:
- O que se sabe ANTES dessa lacuna?
- O que se sabe DEPOIS dessa lacuna?
- QUESTÃO INVESTIGATIVA: Por que existe esse gap? O que deveria ter acontecido?
- Como isso afetou a investigação?

Identifique todas as contradições encontradas e relate quais precisam verificação.

CONCLUSÃO: A sequência temporal é coerente? Quais pontos precisam clarificação?
Quais lacunas são "normais" vs quais indicam falha de processo?

---

OUTPUT ESPERADO:

1. Timeline cronológica formatada (eventos + datas + lacunas)
2. Tabela de lacunas significativas (duração + questões)
3. Lista de contradições detectadas
4. Análise: sequência é coerente ou há problemas?
5. Próximas etapas investigativas sugeridas (o que verificar)

Lembre-se: Você está QUESTIONANDO, não julgando. Você está EXPONDO GAPS,
não acusando de negligência. Sua função é fazer o investigador humano
entender o que falta saber.
```

**RO Que Esperamos do Resultado**

```
## 📋 Output Principal: Timeline Reconstruída

- **52 de 55 eventos** ordenados cronologicamente (do mais antigo ao mais recente)
- Cada evento com **classificação de data:**
  - [DATA CERTA] = mencionada explicitamente
  - [DATA APROXIMADA] = inferida do contexto
  - [DATA INCERTA] = não mencionada
- **Lacunas marcadas** entre cada evento (duração em dias)

---

## ❌ Contradições a Detectar (2 críticas)

- **Contradição 1:** Saque em 4 de janeiro, mas conta abre em 10 de janeiro
  - Questão: Qual data está correta?
  
- **Contradição 2:** Marisa desaparece ~meados de fevereiro, mas Sr. José continua ativo até ~março
  - Questão: Como um desaparece e o outro não?

---

## ⚠️ Lacunas Significativas a Identificar

- **Lacuna 1 (5 dias):** Gerente vê irregularidade (5/1) mas conta abre normalmente (10/1)
  
- **Lacuna 2 (15-29 dias):** Vítimas descobrem em momentos completamente diferentes
  
- **Lacuna Crítica 3 (13 dias):** Banco tem prova completa (11/2) → Polícia alerta (20/2)
  - 🔴 Crime continua ativo nesse período
  
- **Lacuna Crítica 4 (8 dias):** Inquérito aberto (22/2) → PF assume (1/3)
  - 🔴 Sem progresso documentado

---

## 💡 Análise Investigativa Esperada

- **Questões "Por quê?"** para cada lacuna (sem julgamentos)
  - "Por que banco esperou 13 dias?"
  - "O que foi feito nesses 8 dias?"
  
- **Diferença sequência vs causalidade:**
  - Sequência: cronologicamente correto
  - Causalidade: relação causa-efeito existe?
  
- **Conclusão:** A sequência revela onde o sistema falhou

---

## ✅ Critérios de Sucesso

- ✅ Ordena ≥95% dos eventos
- ✅ Identifica ≥5 lacunas com duração
- ✅ Classifica datas com ≥90% acurácia
- ✅ Detecta ambas as contradições
- ✅ Questiona investigativamente (sem julgamentos)
- ✅ Diferencia sequência de causalidade
- ✅ Sugere 8+ próximas etapas de investigação

---

## 🎯 Resultado Final

**PROMPT 3 PASSOU quando:** Descobre naturalmente (a partir dos dados caóticos) que há falhas de comunicação críticas entre banco e polícia, investigação parada por 8 dias, e dados contraditórios que indicam erros de processo.

```

#### Por que Este Exercício Importa

No mundo real, um investigador recebe:
- Depoimentos (desorganizados)
- Extratos bancários (com datas)
- Comunicações (emails, mensagens)
- Perícias (com datas)
- Histórico de ligações (com datas)

### Limitações

⚠️ **Não confundir sequência com causalidade:**
- Só porque A ocorreu antes de B não significa A causou B
- Marque [SEQUÊNCIA INFERIDA] quando causalidade é dedução

✅ **Marcar incertezas:**
- Datas aproximadas recebem [DATA APROXIMADA]
- Lacunas recebem [LACUNA: X dias]
---
