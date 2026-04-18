# Aulas para HTML (Offline)

Projeto de aulas em HTML com foco em **entrega final 100% offline**.

## Regra principal

- O produto final deve ser **um único arquivo HTML**.
- Esse arquivo deve abrir localmente no navegador, **sem internet**.
- Não usar dependências externas (CDN, fontes remotas, JS remoto).

## Estrutura

- `html/aula1.html`: versão visual da Aula 1.
- `html/aula1-pratica-html.html`: versão prática da Aula 1 (mesmo layout-base da Aula 1).
- `aulas-md/aula1.md`: conteúdo-base em Markdown.
- `aulas-md/aula1-pratica.md`: conteúdo-base da prática em Markdown.
- `aulas-md/aula2.md`: rascunho da Aula 2.
- `aulas-md/aula3.md`: rascunho da Aula 3.
- `aulas-md/aula4.md`: rascunho da Aula 4.
- `aulas-md/GUIA-APOIO.md`: padrão editorial e checklist.

## Fluxo recomendado

1. Escrever conteúdo da aula em `aulas-md/aulaX.md`.
2. Aplicar no `html/aulaX.html` com layout já validado.
3. Garantir que o HTML final continue offline (sem links de dependência).

## Controle (atualizado em 18/04/2026)

- A página de práticas da Aula 1 foi consolidada em `html/aula1-pratica-html.html`.
- A versão prática usa o mesmo layout estrutural de `html/aula1.html` (sidebar, menu mobile e tema).
- O menu lateral da Aula 1 recebeu item final `Práticas` com link para `aula1-pratica-html.html`.
- Os prompts da prática possuem:
  - botão de copiar;
  - botões de teste para Gemini, Claude, Copilot e ChatGPT;
  - caixa de prompt com quebra de linha para não estourar o layout.
- Tabelas de avaliação da prática foram convertidas para formulário interativo.
- Regra operacional: novos HTMLs gerados devem ficar na pasta `html/`.
