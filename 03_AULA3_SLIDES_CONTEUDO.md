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

### 🔑 Técnica Empregada: Persona + Estruturação com Restrição

**O que:** Combine 3 elementos — (1) atribua especialidade ao modelo, (2) defina formato exato, (3) restrinja a informações explícitas.

**Por que funciona aqui:** Depoimentos chegam desorganizados. Persona força qualidade analítica. Estruturação cria uniformidade (mesma resposta para qualquer documento). Restrição evita alucinações (modelo não deve inventar dados).

---

### Técnica de Prompt: Detalhamento Completo

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

## Resumo do caso

O caso resume-se a uma suposta fraude de R$ 50 mil no Banco Sul.

Em 10/03, Sandra Lima abriu uma conta acompanhada por um homem não identificado. No dia 20/03, houve uma tentativa de transferência desse valor em um terminal físico, o que causou o bloqueio automático da conta.

Os pontos centrais da investigação são:

- **Conflito de horários:** O gerente relata o bloqueio às 14h, enquanto a TI registrou às 16h30.
- **Falhas de registro:** As câmeras da agência não funcionaram e o vigilante perdeu as anotações com os horários exatos da movimentação.
- **Ausência de comando:** O gerente estava em viagem, e o homem que acompanhava Sandra foi visto saindo apressado da agência logo após o travamento do sistema.


**Três depoimentos (desorganizados):**
```

**DEPOIMENTO 1: Ricardo Souza (Gerente da Agência)**
"Eu lembro que no dia 10 de março de 2024, uma tal de Sandra Lima veio aqui na minha mesa, no Banco Sul. Ela abriu uma conta usando documentos que pareciam legítimos. Ela estava acompanhada de um homem alto que não se identificou, mas que não saiu do lado dela. Eu assinei a abertura. Mais tarde, no dia 20 de março, eu soube que o sistema travou a conta por suspeita de fraude às 14:00h, mas eu estava de férias em Salvador, então não vi quem estava operando o terminal."

**DEPOIMENTO 2: Beatriz Mendes (Analista de TI)**
"O alerta de segurança disparou no dia 20 de março de 2024, mas o sistema registrou o travamento às 16:30h, e não às 14:00h como disseram. Alguém tentou transferir R$ 50.000,00 da conta da Sandra Lima. A operação foi feita por um terminal físico aqui na nossa unidade do Banco Sul. Eu liguei imediatamente para o gerente Ricardo, mas ele não atendeu. Suspeitamos que o homem que acompanhou a Sandra na abertura da conta — que para nós é o mentor do golpe — tenha feito o acesso, mas as câmeras falharam."

**DEPOIMENTO 3: Vigilante de Turno (Marcos Santos)**
"Eu vi a movimentação no dia 20. Um homem com as mesmas características daquele que veio no dia 10 (alto e de casaco escuro) entrou na agência pouco antes do sistema travar. Ele saiu apressado logo depois. Não consegui ver o rosto, mas ele usou o terminal 04. A Dona Sandra não estava com ele dessa vez. Eu anotei tudo no meu relatório de turno, mas perdi a folha com o horário exato."

```

**Prompt de Extração:**
```
# PERSONA
Você é um Analista de Inteligência Investigativa sênior. Sua função é processar depoimentos brutos, cruzar informações e identificar pontos de divergência para auditoria.

# TAREFA
1. Extraia eventos, datas, pessoas e locais dos depoimentos fornecidos em uma tabela consolidada.
2. Identifique contradições diretas entre os depoimentos e gere uma tabela secundária de conflitos.

# REGRAS DE STATUS (TABELA 1)
- EXPLÍCITO: Informação literal no texto.
- INFERIDO: Dedução lógica baseada no contexto (deve ser sinalizada).
- [NÃO INFORMADO]: Para dados ausentes.

# REGRAS DE CONFLITOS (TABELA 2)
Se dois ou mais depoentes fornecerem informações diferentes sobre o mesmo fato (horários, nomes, sequências), liste-os na tabela "CONFLITOS IDENTIFICADOS".

# FORMATO DE SAÍDA

### TABELA 1: CRONOLOGIA CONSOLIDADA
| DATA | EVENTO | PESSOA(S) | LOCAL | STATUS |
| :--- | :--- | :--- | :--- | :--- |

### TABELA 2: CONFLITOS IDENTIFICADOS
| ASPECTO | DEPOENTE 1 | DEPOENTE 2 | CLASSIFICAÇÃO |
| :--- | :--- | :--- | :--- |
```

**Resultado Esperado (Estruturado):**

# RELATÓRIO DE INTELIGÊNCIA INVESTIGATIVA

**Analista Responsável:** Sênior
**Caso:** Suspeita de Fraude - Banco Sul (Sandra Lima)

---

### TABELA 1: CRONOLOGIA CONSOLIDADA

| DATA | EVENTO | PESSOA(S) | LOCAL | STATUS |
| :--- | :--- | :--- | :--- | :--- |
| 10/03/2024 | Abertura de conta bancária | Sandra Lima, Homem Alto (não identificado) e Ricardo Souza | Banco Sul (Agência) | EXPLÍCITO |
| 20/03/2024 | Tentativa de transferência de R$ 50.000,00 | Sandra Lima (Conta Origem) | Banco Sul (Terminal Físico) | INFERIDO |
| 20/03/2024 | Disparo do alerta e travamento do sistema | Sandra Lima e Homem Alto (Suspeito) | Banco Sul (Terminal 04) | EXPLÍCITO |
| 20/03/2024 | Tentativa de comunicação frustrada com gerência | Beatriz Mendes e Ricardo Souza | [NÃO INFORMADO] | EXPLÍCITO |
| 20/03/2024 | Ausência do Gerente por período de férias | Ricardo Souza | Salvador | EXPLÍCITO |

---

### TABELA 2: CONFLITOS IDENTIFICADOS

| ASPECTO | DEPOENTE 1 (Ricardo Souza) | DEPOENTE 2 (Beatriz Mendes) | CLASSIFICAÇÃO |
| :--- | :--- | :--- | :--- |
| **Horário do Incidente** | Afirma que a conta foi travada às 14:00h. | Afirma que o sistema registrou o travamento às 16:30h. | **Divergência Temporal Crítica** |
| **Comunicação** | Não menciona tentativa de contacto; afirma estar em Salvador. | Afirma ter ligado imediatamente para o gerente Ricardo. | **Divergência de Conduta** |

---

### NOTAS DE AUDITORIA

1.  **Lacuna de Horário:** Existe uma discrepância de 2h30min entre o horário citado pelo gerente (14:00) e o log técnico da TI (16:30). É vital auditar os logs do sistema para verificar se houve acesso remoto ou tentativa de encobrimento.
2.  **Identificação Visual:** O vigilante confirma que o mesmo indivíduo do dia 10 (abertura) estava no Terminal 04 no dia 20. A "falha" simultânea das câmeras de segurança é um forte indício de sabotagem interna.
3.  **Localização Geográfica:** Recomenda-se a validação das passagens aéreas ou comprovantes de estadia do Gerente Ricardo Souza em Salvador para confirmar o álibi.



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

### 🔑 Técnica Empregada: Role Prompting + Taxonomia + Força do Vínculo

**O que:** (1) Atribua identidade especializada ao modelo, (2) crie categorias pré-definidas (COLEGUISMO, TRANSAÇÃO, etc.), (3) marque certeza (DIRETA vs INDIRETA).

**Por que funciona aqui:** Redes caóticas precisam de ordem. Taxonomia diferencia tipos (não confunde parentesco com corrupção). Força DIRETA/INDIRETA documenta confiança. Evidência citada torna cada vínculo verificável.

---

### Técnica de Prompt: Detalhamento Completo

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

Neste exemplo, iremos usar um arquivo com os dados em formato csv, simulando um arquivo que você poderia receber de um setor de inteligência.
Este arquivo pode ser baixado clicando diretamente no link abaixo:

inserir LINK

```

**Prompt de Mapeamento — VERSÃO OTIMIZADA:**
```
Você é analista de inteligência especializado em mapeamento de redes.

INSTRUÇÃO:
Para CADA frase abaixo, identifique TODAS as pessoas mencionadas e TODOS os vínculos EXPLÍCITOS entre elas.

PASSO 1: Processe cada frase sequencialmente.
PASSO 2: Extraia vínculos DIRETOS, ditos explicitamente, antes de qualquer vínculo indireto.
PASSO 3: Não invente pessoas, vínculos, datas, locais ou relações.
PASSO 4: Quando houver pessoa mencionada sem nome próprio ou não identificada completamente, use exatamente: [PESSOA NÃO IDENTIFICADA].
PASSO 5: Quando a frase não tiver vínculo interpessoal explícito, registre a frase com os demais campos preenchidos como [SEM VÍNCULO].
PASSO 6: Entregue a resposta exclusivamente em formato CSV, sem comentários antes ou depois.
PASSO 7: Além de gerar o CSV no corpo da resposta, crie e disponibilize um arquivo baixável em formato .csv com o nome: vinculos_extraidos.csv.

TIPOS DE VÍNCULO, use EXATAMENTE um destes:
COLEGUISMO = trabalho/relação profissional, exemplo: "trabalha com", "supervisionava", "assessora de", "contratado por"
INTERMEDIAÇÃO = mediação/facilitação de negócio ou operacional
TRANSAÇÃO = troca, pagamento, recebimento, entrega ou transferência presencial ou documental
COMUNICAÇÃO = ligação, conversa, contato verbal, WhatsApp, Telegram, mensagem ou orientação por chamada
PARENTESCO = família ou laço pessoal, exemplo: "amiga de infância", "esposa", "filha", "mãe", "primo", "padrinha"
ACOMPANHAMENTO = presença conjunta, encontro, reunião, viagem, jantar, frequência no mesmo local ou deslocamento conjunto
FACILITAÇÃO ILÍCITA = facilitação de crime, fraude, falsificação, uso ilícito de documento, ocultação ou ação operacional ilícita

REGRAS DE FORÇA:
DIRETA = o vínculo está expresso literalmente entre as pessoas na frase.
INDIRETA = o vínculo é textual, mas depende de relação intermediária explícita na própria frase.
Não use inferências externas à frase.

FORMATO OBRIGATÓRIO DE SAÍDA:
A saída deve ser um CSV válido, usando vírgula como separador, com cabeçalho exatamente assim:

Frase,Pessoa A,Tipo,Pessoa B,Força,Evidência

REGRAS DO CSV:
1. Cada vínculo deve ocupar uma linha.
2. Se uma frase tiver mais de um vínculo, crie uma linha para cada vínculo.
3. A coluna Frase deve conter apenas o número da frase.
4. A coluna Tipo deve conter apenas um dos tipos permitidos.
5. A coluna Força deve conter apenas DIRETA ou INDIRETA.
6. A coluna Evidência deve conter uma citação curta, literal e exata da frase original.
7. Todos os campos textuais devem estar entre aspas duplas.
8. Se a evidência tiver aspas internas, escape-as duplicando as aspas, padrão CSV.
9. Não use markdown.
10. Não use tabela visual.
11. Não explique o resultado.
12. Não inclua observações finais.
13. O arquivo .csv baixável deve conter exatamente as mesmas colunas e linhas da resposta.

EXEMPLO DE SAÍDA:
"Frase","Pessoa A","Tipo","Pessoa B","Força","Evidência"
"1","Roberto Mendes","COLEGUISMO","Carlos Henrique","DIRETA","trabalha diretamente com o gerente de operações Carlos Henrique"
"3","Patricia Gonçalves","COLEGUISMO","Carlos Henrique","DIRETA","Patricia Gonçalves, assessora de Carlos"
"3","Patricia Gonçalves","TRANSAÇÃO","João da Silva","DIRETA","recebeu pessoalmente os documentos falsificados de um courier identificado como ""João da Silva"""
"14","[SEM VÍNCULO]","[SEM VÍNCULO]","[SEM VÍNCULO]","[SEM VÍNCULO]","[SEM VÍNCULO]"

DADOS PARA PROCESSAR:

```

**Resultado Esperado (Rede):**

Um arquivo em formato CSV será gerado com a relação de vínculos entre pessoas.

A estrutura do arquivo csv é a seguinte:  
1. Frase
2. Pessoa A
3. Tipo de vínculo
4. Pessoa B
5. Força do vínculo
6. Evidência

O prompt acima é um bom exemplo de como usar o role prompt para obter informações estructuradas de um texto. 

Usando a técnica de prompt anterior, obteremos um arquivo em formato CSV com a relação de vínculos entre pessoas

Com este arquivo poderemos importar para o i2 analysts notebook, software de análise de dados em rede. A visualização em rede facilita o entendimento da estrutura da organização.  
```
Entrada:

Frase 1: Roberto Mendes é sócio do Banco Fiduciário desde 2018 e trabalha diretamente com o gerente de operações Carlos Henrique.
Frase 2: Carlos Henrique intermediou a abertura de 12 contas fictícias em nome de terceiros entre janeiro e março de 2024.
Frase 3: Patricia Gonçalves, assessora de Carlos, recebeu pessoalmente os documentos falsificados de um courier identificado como "João da Silva" em 15/02/2024.
Frase 4: João da Silva trabalha como entregador autônomo há 8 anos e foi recrutado por Marisa Oliveira, ex-funcionária do Tabelionato de Santos.

...

Saída:

Frase,"Pessoa A","Tipo","Pessoa B","Força","Evidência"
1,"Roberto Mendes","COLEGUISMO","Carlos Henrique","DIRETA","trabalha diretamente com o gerente de operações Carlos Henrique"
2,"Carlos Henrique","INTERMEDIAÇÃO","[PESSOA NÃO IDENTIFICADA]","DIRETA","intermediou a abertura de 12 contas fictícias em nome de terceiros"
3,"Patricia Gonçalves","COLEGUISMO","Carlos Henrique","DIRETA","Patricia Gonçalves, assessora de Carlos"
3,"Patricia Gonçalves","TRANSAÇÃO","João da Silva","DIRETA","recebeu pessoalmente os documentos falsificados de um courier identificado como ""João da Silva"""
4,"João da Silva","COLEGUISMO","Marisa Oliveira","DIRETA","foi recrutado por Marisa Oliveira"

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
- Relações que são deduções lógicas mas não explícitas
- Força INDIRETA para conexões via terceiros

---

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

Uma rede criminosa coordenada executou um esquema de fraude bancária entre dezembro de 2023 e março de 2024. O crime envolveu abertura de contas falsificadas em nome de três vítimas diferentes, seguida de saques não autorizados. O aspecto crítico: **a investigação demorou 51 dias para começar**, e quando começou, ficou parada por 8 dias enquanto os criminosos continuavam ativos.

Este é um caso real de investigação deficiente onde as autoridades falharam em comunicação e resposta rápida — exatamente o tipo de cenário que um investigador moderno enfrenta: informações fragmentadas, fora de ordem, com datas conflitantes e lacunas críticas.

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