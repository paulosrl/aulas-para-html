# Prompt para Regenerar html/aula3.html a partir de 03_AULA3_SLIDES_CONTEUDO.md

## Instrução Crítica

Você vai converter **100% do conteúdo** do arquivo `03_AULA3_SLIDES_CONTEUDO.md` para HTML dentro do arquivo `html/aula3.html`, mantendo:
- ✅ Estrutura HTML5 intacta (DOCTYPE, head com styles, scripts)
- ✅ Sidebar com navegação intacta
- ✅ Tema toggle e dark-mode intacto
- ✅ Estilos CSS intactos
- ✅ Scripts JavaScript intactos
- ✅ Elementos interativos (copy buttons, AI test links)

## Mapa de Conteúdo (Arquivo Markdown → Seções HTML)

### Cobertura Obrigatória:

| Seção Markdown | ID HTML | Localização | Status |
|---|---|---|---|
| Aula 3 — Slides e Conteúdo Técnico | `#p1` | section 1 | ABERTURA |
| Objetivos de Aprendizado | `#p2` | section 2 | OBJETIVOS |
| Roadmap de Técnicas | `#p3` | section 3 | ROADMAP |
| TÓPICO 1: Análise Estruturada | `#p4` | section 4 | TEMA 1 |
| TÓPICO 2: Reconhecimento de Vínculos | `#p5` | section 5 | TEMA 2 |
| TÓPICO 3: Reconstrução Cronológica | `#p6` | section 6 | TEMA 3 |
| TÓPICO 4: Validação Crítica | (novo) | section 7 | TEMA 4 |

---

## Procedimento Passo-a-Passo

### PASSO 1: Preservar Estrutura HTML
- Leia o arquivo `html/aula3.html` completamente
- Identifique as seções `<section id="p1">` a `<section id="p6">`
- Mantenha INTACTOS:
  - `<head>` (estilos, meta tags)
  - `<aside class="sidebar">` (navegação)
  - `<button class="btn-theme">` (tema toggle)
  - `<script>` (JavaScript)
  - Classes CSS (`caor-card`, `table-wrapper`, `prompt-actions`, etc.)

### PASSO 2: Converter Conteúdo Markdown → HTML
Para cada seção do markdown:

1. **Títulos:** `# Texto` → `<h1>Texto</h1>` (dentro de `<section>`)
2. **Subtítulos:** `## Texto` → `<h2>Texto</h2>` (dentro de `<section>`)
3. **Parágrafos:** Texto simples → `<p>Texto</p>`
4. **Listas não numeradas:** `- item` → `<ul><li>item</li></ul>`
5. **Listas numeradas:** `1. item` → `<ol><li>item</li></ol>`
6. **Tabelas Markdown:** Converter para `<table>` com `<thead>` e `<tbody>`
7. **Código:** ` ```...``` ` → `<pre id="[ID-ÚNICO]">...</pre>` (com ID para copy button)
8. **Negrito:** `**texto**` → `<strong>texto</strong>`

### PASSO 3: Elementos Interativos (CRÍTICO)

Para **cada bloco de código/prompt**:

```html
<!-- ESTRUTURA OBRIGATÓRIA -->
<pre id="unique-id-aqui">
CONTEÚDO DO CÓDIGO/PROMPT
</pre>
<div class="prompt-actions">
    <button class="btn copy-btn" type="button" onclick="copyPrompt('unique-id-aqui', this)">Copiar [DESCRIÇÃO]</button>
    <a class="btn gemini" target="_blank" rel="noopener noreferrer" href="https://gemini.google.com/app" onclick="copyPrompt('unique-id-aqui')">Testar no Gemini</a>
    <a class="btn claude" target="_blank" rel="noopener noreferrer" href="https://claude.ai/new" onclick="copyPrompt('unique-id-aqui')">Testar no Claude</a>
    <a class="btn copilot" target="_blank" rel="noopener noreferrer" href="https://copilot.microsoft.com/" onclick="copyPrompt('unique-id-aqui')">Testar no Copilot</a>
    <a class="btn chatgpt" target="_blank" rel="noopener noreferrer" href="https://chatgpt.com/" onclick="copyPrompt('unique-id-aqui')">Testar no ChatGPT</a>
</div>
```

**IDs Obrigatórios (existentes no HTML):**
- `base-a3-1` = Depoimentos (TÓPICO 1)
- `prompt-a3-1` = Prompt extração (TÓPICO 1)
- `base-a3-2` = Dados vínculos (TÓPICO 2)
- `prompt-a3-2` = Prompt mapeamento (TÓPICO 2)
- `prompt-a3-3` = Prompt cronologia (TÓPICO 3)
- `base-a3-4` = Resposta IA com erros (TÓPICO 4)
- `prompt-a3-4` = Prompt validação (TÓPICO 4)

### PASSO 4: Navegação Sidebar

A navegação DEVE ter links para **TODAS** as 7 seções:
```html
<a href="#p1" class="nav-l"><i class="fas fa-calendar-alt"></i> Abertura</a>
<a href="#p2" class="nav-l"><i class="fas fa-list-ol"></i> Objetivos</a>
<a href="#p3" class="nav-l"><i class="fas fa-route"></i> Roadmap</a>
<a href="#p4" class="nav-l"><i class="fas fa-file-alt"></i> Tópico 1</a>
<a href="#p5" class="nav-l"><i class="fas fa-project-diagram"></i> Tópico 2</a>
<a href="#p6" class="nav-l"><i class="fas fa-clock"></i> Tópico 3</a>
<!-- NOVO: -->
<a href="#p7" class="nav-l"><i class="fas fa-check-circle"></i> Tópico 4</a>
```

### PASSO 5: Validação de Cobertura

Após converter, VERIFIQUE:

- ✅ Seção `#p1` tem "Aula 3 — Slides e Conteúdo Técnico"
- ✅ Seção `#p2` tem "Objetivos de Aprendizado" com 5 objetivos
- ✅ Seção `#p3` tem tabela de "Roadmap de Técnicas" com 4 linhas
- ✅ Seção `#p4` tem TÓPICO 1 completo (🔑 Persona + Estruturação)
  - Contexto, desafio, técnica, procedimento, exemplo prático, limitações
  - Contém: 3 depoimentos (`base-a3-1`), prompt (`prompt-a3-1`), resultado esperado
- ✅ Seção `#p5` tem TÓPICO 2 completo (🔑 Role Prompting + Taxonomia)
  - Contexto, desafio, técnica, procedimento, exemplo prático, limitações
  - Contém: dados (`base-a3-2`), prompt (`prompt-a3-2`), resultado esperado (CSV)
- ✅ Seção `#p6` tem TÓPICO 3 completo (🔑 Chain-of-Thought + Marcação)
  - Contexto, desafio, técnica, procedimento, estudo de caso
  - Contém: prompt (`prompt-a3-3`), resultado esperado
- ✅ Seção `#p7` tem TÓPICO 4 (🔑 Metacognição + Taxonomia V/I/E)
  - Contexto, desafio, técnica, procedimento
  - Contém: resposta IA com erros (`base-a3-4`), prompt validação (`prompt-a3-4`), resultado
- ✅ Todos os `<pre>` tem IDs únicos
- ✅ Todos os prompts/depoimentos têm `.prompt-actions` com buttons
- ✅ Todas as tabelas têm `<thead>` e `<tbody>`
- ✅ Sidebar tem 7 links de navegação para `#p1` até `#p7`
- ✅ Não há duplicatas de ID
- ✅ Estilos CSS preservados (sem mudanças)
- ✅ Scripts JavaScript intactos

---

## Estrutura Final do HTML

```
<!DOCTYPE html>
<html>
  <head>
    <!-- CSS E META TAGS: INTACTOS -->
  </head>
  <body>
    <!-- MOBILE HEADER: INTACTO -->
    <!-- SIDEBAR: INTACTO com 7 links -->
    <!-- BOTÃO TEMA: INTACTO -->
    
    <main class="main-content">
      <div class="content-container">
        <!-- SEÇÃO 1: p1 -->
        <!-- SEÇÃO 2: p2 -->
        <!-- SEÇÃO 3: p3 -->
        <!-- SEÇÃO 4: p4 (TÓPICO 1) -->
        <!-- SEÇÃO 5: p5 (TÓPICO 2) -->
        <!-- SEÇÃO 6: p6 (TÓPICO 3) -->
        <!-- SEÇÃO 7: p7 (TÓPICO 4) - NOVO -->
      </div>
    </main>
    
    <!-- SCRIPTS: INTACTOS -->
  </body>
</html>
```

---

## Checklist de Execução

- [ ] Arquivo `html/aula3.html` aberto e lido completamente
- [ ] Arquivo `03_AULA3_SLIDES_CONTEUDO.md` aberto e lido completamente
- [ ] Head, sidebar, scripts, CSS preservados
- [ ] 7 seções criadas com IDs `#p1` a `#p7`
- [ ] 100% do conteúdo markdown convertido para HTML
- [ ] Todos os `<pre>` com IDs únicos
- [ ] Todos os prompts/depoimentos com `.prompt-actions` buttons
- [ ] Tabelas com `<thead>` e `<tbody>`
- [ ] Sidebar com 7 links de navegação
- [ ] Validação de cobertura completa
- [ ] Arquivo salvo sem erros HTML

---

## Notas Importantes

1. **Não invente conteúdo** — Use APENAS o que está no markdown
2. **Preserve IDs existentes** — Mantenha `base-a3-1`, `prompt-a3-1`, etc.
3. **Não altere CSS** — Os estilos já estão funcionando
4. **Não altere JavaScript** — Os scripts de copy e tema já funcionam
5. **100% de cobertura** — Se algo do markdown não entrou no HTML, é um erro

---

## Como Usar Este Prompt

Quando precisar regenerar o HTML:

1. Cole este prompt em seguida: "Use este prompt para regenerar html/aula3.html"
2. Confirme que entendeu a cobertura esperada
3. Comece a conversão seção por seção
4. Ao final, valide contra o checklist

**Tempo estimado:** 30-45 minutos para garantir 100% de cobertura correta.
