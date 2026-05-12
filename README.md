# aulas-engenharia-prompt

Material completo de ensino para **Engenharia de Prompt em Análises Investigativas** — um curso sobre técnicas estruturadas de uso de IA para investigadores, analistas e agentes da lei.

Atualizado em: **2026-05-12**

## Estrutura do Projeto

```text
.
├── html/                               Aulas e práticas (HTML final)
│   ├── index.html                      Página inicial (GitHub Pages)
│   ├── aula1.html
│   ├── aula2.html
│   ├── aula2-pratica.html
│   ├── aula3.html
│   ├── aula3-pratica.html
│   ├── aula4.html
│   ├── aula 4 - topico 3.md
│   └── dados/                          Dados para exercícios práticos
│       ├── dados-topico1.md
│       ├── dados-topico2.md
│       ├── dados-topico3.md
│       ├── 12345-rif.zip
│       └── RIF12345_Base_Relacional_Auditavel.xlsx
├── graphify-out/                       Grafo de conhecimento do projeto
├── AGENTS.md                           Instruções operacionais para agentes
└── README.md (este arquivo)
```

## Princípio Fundamental

**HTML é a fonte de verdade.** 

Cada página é um arquivo HTML completo e independente:
- ✅ Contém CSS e JavaScript embutidos
- ✅ Funciona offline para conteúdo principal
- ✅ Abre diretamente no navegador
- ✅ Versão única para desktop e mobile

## Status das Aulas

| Aula | Status | Acesso |
| --- | --- | --- |
| **Aula 1** | ✅ Completa | [html/aula1.html](html/aula1.html) |
| **Aula 2** | ✅ Completa | [html/aula2.html](html/aula2.html) |
| **Prática Aula 2** | ✅ Disponível | [html/aula2-pratica.html](html/aula2-pratica.html) |
| **Aula 3** | ✅ Completa | [html/aula3.html](html/aula3.html) |
| **Prática Aula 3** | ✅ Disponível | [html/aula3-pratica.html](html/aula3-pratica.html) |
| **Aula 4** | ✅ Completa | [html/aula4.html](html/aula4.html) |

## Como Editar uma Aula

### Fluxo de Trabalho

1. **Abra o arquivo HTML** da aula desejada (ex: `html/aula3.html`)
2. **Edite o conteúdo** diretamente no arquivo HTML
3. **Procure pela seção** que deseja modificar (use Ctrl+F para buscar)
4. **Altere o texto**, atualize exemplos, revise exercícios
5. **Salve o arquivo**
6. **Teste localmente** — abra no navegador para verificar:
   - Tema claro/escuro funciona
   - Botões de copiar prompts funcionam
   - Layout responsivo em desktop e mobile
   - Nenhum overflow em tabelas ou blocos de código
7. **Faça commit** com mensagem clara: `update: revise Aula 3 Tópico 2`
8. **Push para GitHub** — publica automaticamente via GitHub Pages

## Detalhes Técnicos

### Template de Prompt

Quando adicionar um novo prompt, use este padrão:

```html
<pre id="prompt-aX-Y">Seu prompt aqui...</pre>
<div class="prompt-actions">
    <button class="btn copy-btn" onclick="copyPrompt('prompt-aX-Y', this)">Copiar</button>
    <a class="btn gemini" target="_blank" href="https://gemini.google.com/app" onclick="copyPrompt('prompt-aX-Y')">Testar no Gemini</a>
    <a class="btn claude" target="_blank" href="https://claude.ai/new" onclick="copyPrompt('prompt-aX-Y')">Testar no Claude</a>
    <a class="btn copilot" target="_blank" href="https://copilot.microsoft.com/" onclick="copyPrompt('prompt-aX-Y')">Testar no Copilot</a>
    <a class="btn chatgpt" target="_blank" href="https://chatgpt.com/" onclick="copyPrompt('prompt-aX-Y')">Testar no ChatGPT</a>
</div>
```

**Convenção de IDs:**
- `prompt-aX-Y` → prompts (aX = aula X, Y = sequência)
- `base-aX-Y` → exemplos
- `p1`, `p2`, `p3`... → seções principais

### Estrutura Didática

Cada aula segue este padrão:

1. **Título** — Claro e profissional
2. **Objetivo** — O que o aluno aprenderá (3-5 pontos com ✅)
3. **Agenda** — Tópicos e tempo estimado
4. **Tópico 1, 2, 3...** — Cada com:
   - 📌 Situação-problema (contexto)
   - 🎯 Objetivo (o que alcançar)
   - 🔧 Solução (técnica passo a passo)
   - 💡 Por que funciona (benefícios)
   - 📋 Exemplo prático
   - ✍️ Exercício para o aluno
5. **Integração Final** — Como as técnicas se conectam
6. **Fechamento** — Resumo e próximos passos

### Restrições Offline-First

- ⚠️ Priorizar HTML autônomo e funcional sem backend
- ❌ Sem JavaScript externo
- ⚠️ Evitar CSS externo (estado atual ainda usa Font Awesome via CDN em algumas páginas)
- ❌ Sem imagens hospedadas
- ⚠️ Quando houver CDN, manter fallback visual para uso offline

## Publicação Pública

O repositório é publicado automaticamente no GitHub Pages.

### 🌐 Acessar Agora

**→ [https://paulosrl.github.io/aulas-engenharia-prompt/html/index.html](https://paulosrl.github.io/aulas-engenharia-prompt/html/index.html)**

### Exemplos de acesso

- Página inicial: `https://paulosrl.github.io/aulas-engenharia-prompt/html/index.html`
- Aula 1: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula1.html`
- Aula 2: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula2.html`
- Prática Aula 2: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula2-pratica.html`
- Aula 3: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula3.html`
- Prática Aula 3: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula3-pratica.html`
- Aula 4: `https://paulosrl.github.io/aulas-engenharia-prompt/html/aula4.html`

## Manutenção do Repositório

- Use `README.md` e `html/index.html` como referência pública da estrutura e do status das aulas.
- Ao alterar aulas em `html/`, revise também a seção "Status das Aulas" neste arquivo.
- Quando uma nova aula/prática for publicada, adicione o link no `html/index.html` e atualize a tabela de status.

## Requisitos para Publicação

Antes de marcar uma aula como completa:

- [ ] HTML testado localmente sem internet
- [ ] Tema toggle funciona (claro ↔ escuro)
- [ ] Botões copiar funcionam (IDs corretos)
- [ ] Links de teste em plataformas de IA funcionam
- [ ] Tabelas têm `<thead>` e `<tbody>`
- [ ] Sem overflow em desktop ou mobile
- [ ] Links internos funcionam
- [ ] `html/index.html` atualizado com novo link

## Contribuindo

Para adicionar ou modificar conteúdo:

1. Clone ou faça fork do repositório
2. Edite o arquivo HTML desejado
3. Teste localmente no navegador
4. Faça commit com mensagem descritiva
5. Abra pull request

## Contato

**Prof. Paulo Lima**  
📧 paulosrl@gmail.com  
🌐 [paulosrl.github.io](https://paulosrl.github.io/)
