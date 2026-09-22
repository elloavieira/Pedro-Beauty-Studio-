# Maquiando Professor Pedro - Versão Python

Jogo em Python com Pygame - ETEC

### Como rodar
1. Instale o Python
2. No terminal: pip install pygame
3. Rode: python main.py

### Como jogar
- Clica pra sair da capa
- Escolhe a expressão em cima (20 opções)
- Esquerda: escolhe Batom / Blush / Sombra
- Direita: escolhe a cor
- Clique e arraste no rosto pra pintar
- Tecla C = Limpa tudo

### Como funciona o código
- **Sprite Sheet**: usa 1 imagem `expressoes.jpg` com 20 rostos (5x4). Recorta com `subsurface()`
- **3 camadas**: `layer_batom`, `layer_blush`, `layer_sombra` são Surfaces transparentes, igual os 3 canvas do HTML
- **Validação**: `inside()` verifica se o mouse tá dentro da boca/bochecha/pálpebra pra não pintar fora
- **Pygame**: desenha tudo em 60 FPS

Versão original em HTML: https://elloavieira.github.io/Pedro-Beauty-Studio-/
