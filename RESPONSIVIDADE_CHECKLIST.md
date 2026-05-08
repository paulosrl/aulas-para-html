# Checklist de Responsividade (Template + Página Gerada)

## 1366px (Desktop)
- Sidebar fixa sem sobrepor conteúdo: OK
- Conteúdo centralizado com largura máxima: OK
- Tabelas legíveis sem quebra de layout: OK
- Títulos e ícones renderizados corretamente: OK

## 1024px (Laptop/Tablet horizontal)
- Sidebar e main-content proporcionais via `clamp(...)`: OK
- Menu lateral com quebra de linhas longas (`overflow-wrap`): OK
- Cartões mantêm padding e bordas sem corte: OK

## 768px (Tablet/Mobile)
- Sidebar vira drawer off-canvas: OK
- Header mobile visível com botão menu: OK
- Botão de tema reposicionado para não sobrepor header: OK
- Tipografia de títulos ajustada para leitura: OK
- Tabelas com rolagem horizontal (`table-wrapper`): OK

## 460px (Mobile pequeno)
- Drawer com largura segura (`min(90vw, 320px)`): OK
- Botão tema dentro da viewport e sem colisão visual: OK
- Cards, alertas e caixas discretas com padding compacto: OK
- Textos longos quebram corretamente (`overflow-wrap/word-break`): OK

## Regras Globais Confirmadas
- Mídias fluidas: `img, video, canvas, svg, iframe { max-width: 100%; height: auto; }`
- Overflow horizontal evitado no body: `overflow-x: hidden`
- Navegação mobile com overlay + fechamento por link: OK
- Pipeline Markdown -> HTML preservando layout: OK
