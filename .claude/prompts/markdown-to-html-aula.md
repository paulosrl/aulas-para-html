# Prompt Genérico: Converter Markdown → HTML (Padrão Aulas)

## Instrução Crítica

Você vai converter **100% do conteúdo** de um arquivo Markdown para HTML, usando o padrão de layout das aulas (idêntico ao de `html/aula1.html`, `html/aula2.html`, `html/aula3.html`).

**IMPORTANTE:** 
- ✅ O arquivo HTML de entrada é um TEMPLATE com toda a estrutura, styles e scripts já prontos
- ✅ Você SUBSTITUI APENAS o conteúdo `<main class="main-content">` mantendo tudo o resto intacto
- ✅ O markdown é a FONTE DE VERDADE — 100% dele deve estar no HTML final
- ✅ Nenhum conteúdo deve ser adicionado, removido ou modificado

---

## Parâmetros Configuráveis

| Parâmetro | Descrição | Exemplo |
|-----------|-----------|---------|
| `MARKDOWN_FILE` | Arquivo markdown de entrada | `03_AULA3_SLIDES_CONTEUDO.md` |
| `HTML_FILE` | Arquivo HTML para atualizar | `html/aula3.html` |
| `PAGE_TITLE` | Título da página (no `<title>`) | `Aula 3 - Aplicação Prática em Análises Investigativas` |
| `MOBILE_TITLE` | Título para mobile header | `Aula 3` |

---

## Procedimento Passo-a-Passo

### PASSO 1: Preservar Estrutura HTML

✅ **MANTENHA INTACTOS:**
- `<!DOCTYPE html>` até `<main class="main-content">`
- `<head>` completo (CSS, meta tags, title)
- `<aside class="sidebar">` com navegação
- `<button class="btn-theme">` (tema toggle)
- `</main>` até `</html>` (scripts, footer)
- Todas as classes CSS

❌ **SUBSTITUA APENAS:**
- Conteúdo dentro de `<div class="content-container">...</div>`

### PASSO 2: Estruturar Conteúdo em Seções

O conteúdo markdown será organizado em `<section>` com IDs sequenciais:
- `<section id="p1">` — Primeira seção do markdown
- `<section id="p2">` — Segunda seção do markdown
- `<section id="pN">` — Enésima seção do markdown

Cada seção segue a classe CSS: `class="caor-card"`

### PASSO 3: Converter Markdown → HTML

Para cada elemento markdown:

```
Markdown                    →  HTML
─────────────────────────────────────────
# Título H1                 →  <h1>Título H1</h1>
## Título H2                →  <h2>Título H2</h2>
### Título H3               →  <h3>Título H3</h3>

Parágrafo simples           →  <p>Parágrafo simples</p>

- item 1                    →  <ul>
- item 2                        <li>item 1</li>
                                <li>item 2</li>
                            </ul>

1. item 1                   →  <ol>
2. item 2                       <li>item 1</li>
                                <li>item 2</li>
                            </ol>

| Col1 | Col2 |              →  <table>
|------|------|                 <thead>
| A    | B    |                   <tr><th>Col1</th><th>Col2</th></tr>
| C    | D    |                 </thead>
                                <tbody>
                                  <tr><td>A</td><td>B</td></tr>
                                  <tr><td>C</td><td>D</td></tr>
                                </tbody>
                            </table>

```code
bloco de código
```                         →  <pre>bloco de código</pre>

**negrito**                 →  <strong>negrito</strong>
_itálico_                   →  <em>itálico</em>
```

### PASSO 4: Elementos Especiais (Prompts, Depoimentos, etc)

Para blocos de código nomeados (como prompts), adicione `.prompt-actions`:

```html
<pre id="prompt-X">CONTEÚDO</pre>
<div class="prompt-actions">
    <button class="btn copy-btn" type="button" onclick="copyPrompt('prompt-X', this)">Copiar</button>
    <a class="btn gemini" target="_blank" rel="noopener noreferrer" href="https://gemini.google.com/app" onclick="copyPrompt('prompt-X')">Testar no Gemini</a>
    <a class="btn claude" target="_blank" rel="noopener noreferrer" href="https://claude.ai/new" onclick="copyPrompt('prompt-X')">Testar no Claude</a>
    <a class="btn copilot" target="_blank" rel="noopener noreferrer" href="https://copilot.microsoft.com/" onclick="copyPrompt('prompt-X')">Testar no Copilot</a>
    <a class="btn chatgpt" target="_blank" rel="noopener noreferrer" href="https://chatgpt.com/" onclick="copyPrompt('prompt-X')">Testar no ChatGPT</a>
</div>
```

**IDs OBRIGATÓRIOS:**
- Use padrão `base-aX-Y` para depoimentos/exemplos
- Use padrão `prompt-aX-Y` para prompts
- Exemplo: `base-a3-1`, `prompt-a3-1`, `base-a3-2`, etc.
- X = número da aula
- Y = número sequencial (1, 2, 3...)

### PASSO 5: Navegação Sidebar

A sidebar já existe no HTML. **ATUALIZE-A APENAS SE** o markdown tiver títulos H2 que precisem de navegação por seção.

Padrão de link:
```html
<a href="#pN" class="nav-l"><i class="fas fa-ICON"></i> Título</a>
```

---

## Checklist de Validação (OBRIGATÓRIO)

Após converter, VERIFIQUE:

- ✅ Arquivo HTML válido (sem erros de sintaxe)
- ✅ Sidebar preservada intacta
- ✅ CSS preservado intacto
- ✅ Scripts JavaScript preservados intactos
- ✅ Tema toggle funcional (dark-mode)
- ✅ **100% do conteúdo markdown presente no HTML**
- ✅ Todas as seções têm `class="caor-card"`
- ✅ Todas as tabelas têm `<thead>` e `<tbody>`
- ✅ Todos os prompts têm `.prompt-actions` com 5 botões
- ✅ Nenhum conteúdo foi omitido, duplicado ou alterado
- ✅ IDs de seções são sequenciais (`#p1`, `#p2`, `#p3`, etc.)
- ✅ IDs de `<pre>` são únicos e seguem padrão

---

## Notas Críticas

1. **Markdown = Fonte de Verdade**: Tudo que está no markdown deve estar no HTML
2. **Não invente conteúdo**: Use APENAS o que está no markdown
3. **Preserve estrutura**: O HTML template já tem todo o layout pronto
4. **Mantenha IDs únicos**: Cada `<pre>` precisa de um ID diferente
5. **Respeite CSS**: Não mude nada de estilos ou classes
6. **Teste funcionalidade**: Tema toggle, copy buttons, links devem funcionar

---

## Como Usar Este Prompt

**Formato de chamada:**

```
Use o prompt genérico para converter markdown para HTML

Parâmetros:
- MARKDOWN_FILE: 03_AULA3_SLIDES_CONTEUDO.md
- HTML_FILE: html/aula3.html
- PAGE_TITLE: Aula 3 - Aplicação Prática em Análises Investigativas
- MOBILE_TITLE: Aula 3

[Inclua o prompt genérico completo]
```

**Tempo estimado:** 20-30 minutos por aula (conversão + validação)

---

## Exemplo de Estrutura Final Esperada

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <!-- CSS e meta tags: INTACTOS -->
    <title>PAGE_TITLE</title>
</head>
<body>
    <header class="mobile-header">
        <!-- INTACTO -->
        <span class="mobile-header-title">MOBILE_TITLE</span>
    </header>
    
    <aside class="sidebar">
        <!-- INTACTO com navegação -->
    </aside>
    
    <button class="btn-theme" onclick="toggleTheme()">🌓 TEMA</button>
    
    <main class="main-content">
        <div class="content-container">
            <!-- SEÇÃO 1: Primeira grande seção do markdown -->
            <section id="p1" class="caor-card">
                <h1>Título Principal</h1>
                <p>Conteúdo...</p>
            </section>
            
            <!-- SEÇÃO 2: Segunda grande seção do markdown -->
            <section id="p2" class="caor-card">
                <h2>Subtítulo</h2>
                <p>Conteúdo...</p>
            </section>
            
            <!-- ... mais seções ... -->
        </div>
    </main>
    
    <script>
        <!-- Scripts: INTACTOS -->
    </script>
</body>
</html>
```

---

## Troubleshooting

| Problema | Solução |
|----------|---------|
| CSS não está aparecendo | Verifique se `<head>` foi preservado intacto |
| Copy buttons não funcionam | Verifique se IDs de `<pre>` são únicos e `onclick` está correto |
| Sidebar desaparece | Verifique se `<aside class="sidebar">` não foi deletado |
| Tema toggle não funciona | Verifique se `<button class="btn-theme">` e `<script>` estão intactos |
| Conteúdo faltando | Compare markdown com HTML — verifique se tudo foi convertido |

