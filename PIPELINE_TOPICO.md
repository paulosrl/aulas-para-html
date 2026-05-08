# Pipeline de Geração de Tópico (Markdown -> HTML)

## Arquivos
- Template base: `templates/topico.template.html`
- Conteúdo de entrada: `conteudo/topico1.md`
- Gerador: `scripts/build_topico.py`
- Saída final: `aulas-workshop-ia-juri/topico1.html`

## Como usar
```bash
./scripts/build_topico.py conteudo/topico1.md aulas-workshop-ia-juri/topico1.html
```

## O que o script atualiza automaticamente
- Conteúdo principal (`content-container`) com seções semânticas.
- Menu da seção `Aula 1` na sidebar com links para os tópicos gerados.

## Convenções de Markdown recomendadas
- `## Título` para criar um tópico/card.
- Também aceita linha inteira em negrito como título: `**TÍTULO**`.
- Listas com `- item` ou `1. item`.
- Citação com `> texto`.

## Observação
O layout (CSS, scripts, sidebar geral, tema claro/escuro, responsividade) é preservado pelo template.
