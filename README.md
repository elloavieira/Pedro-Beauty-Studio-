# 💄 Maquiando o Professor Pedro

Jogo interativo feito em HTML, CSS e JavaScript puro para a ETEC.
Link do jogo: https://SEU-USUARIO.github.io/Pedro-Beauty-Studio-/

### Como jogar
1. Clica em JOGAR na capa
2. Escolhe uma das 20 expressões em cima
3. Na esquerda escolhe: Batom, Blush ou Sombra
4. Na direita escolhe a cor e o tamanho do pincel
5. Pinta o rosto no centro arrastando o mouse

### Como o código funciona - Explicação completa

**1. HTML - O esqueleto**
- `<!DOCTYPE html>`: diz que é HTML5
- `<html lang="pt-BR">`: site em português
- `<meta charset="UTF-8">`: permite acentos
- `<title>`: nome que aparece na aba do navegador

**2. CSS - A aparência**
- `body { background:#ffb6dd; display:flex; justify-content:center }`: fundo rosa e tudo centralizado
- `.game`: caixa principal branca com borda rosa forte de 5px e canto arredondado 24px
- `#capa { position:absolute; inset:0; background:url('capa.jpg'); z-index:100 }`: capa que cobre tudo no início, fica por cima de tudo
- `.top`: barra de cima com as expressões, usa `display:flex`
- `.mini`: as 20 carinhas pequenas. Truque principal: usamos SPRITE SHEET. Só temos 1 imagem `expressoes.jpg` com 20 rostos (5 colunas x 4 linhas). Usamos `background-size: 500% 400%` e mudamos o `background-position` para recortar 1 rosto por vez. Isso deixa o site muito mais leve e rápido.
- `.mid`: divide o meio em 3 colunas
- `.face-wrap { position:relative }` e `canvas { position:absolute; inset:0 }`: o rosto grande no meio e 3 folhas transparentes por cima (cSombra, cBlush, cBatom). Pintamos no vidro, não no rosto. Por isso conseguimos apagar só o batom sem apagar o resto.

**3. JavaScript - O cérebro**
- `const cores = { batom:[...], blush:[...], sombra:[...] }`: objeto que guarda todas as cores disponíveis
- `let atual e corAtual`: variáveis que lembram qual pincel e qual cor estão selecionados agora
- `function getAreas()`: define onde pode pintar. Batom só na boca (oval), blush nas bochechas (2 círculos), sombra nas pálpebras (2 retângulos)
- `function renderCores()`: quando clica em um pincel na esquerda, apaga as cores da direita e cria botões só com as cores daquele tipo
- `function paintAt(x,y)`: é o pincel. Primeiro verifica `if(!inside(x,y,area)) return;` - se o mouse está fora da área permitida, não pinta. Se está dentro, desenha um círculo `ctx.arc(x,y, size/2)` e preenche com `ctx.fill()` usando a cor escolhida
- `mousedown, mousemove, mouseup`: eventos que ligam e desligam o pincel quando clica e arrasta o mouse
- `trocarExpressao(i)`: quando clica numa carinha em cima, muda o `background-position` do rosto grande para mostrar a expressão clicada
- `clearAll() e clearOne()`: limpa os canvas com `clearRect()`. Um limpa tudo, outro limpa só a camada selecionada

**4. Tecnologias usadas**
- HTML5, CSS3, JavaScript puro (sem biblioteca)
- GitHub Pages para hospedagem

### Arquivos do projeto
- `index.html`: todo o código do jogo
- `capa.jpg`: imagem da capa inicial
- `expressoes.jpg`: imagem única com as 20 expressões do professor

Feito por alunos da ETEC.
