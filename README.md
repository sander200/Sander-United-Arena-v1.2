# Sander United Arena

Projeto HTML5 2D pronto para GitHub Pages.

## Estrutura

```text
sander-united-arena/
├── index.html
├── styles.css
├── game.js
├── README.md
└── assets/
    ├── mapa.png
    ├── sander-sprites.png
    └── nemesis-sprites.png
```

## Assets

Coloque o mapa enviado no projeto como:

`assets/map-estacao-paulista.png`

O motor trabalha com área lógica de 1536 × 864 e usa a imagem inteira no minimapa.

Os sprites opcionais são:

- `assets/sander-sprites.png`
- `assets/nemesis-sprites.png`

O motor aceita spritesheets 4 × 4. Enquanto eles não existirem, há personagens de fallback desenhados pelo Canvas.

## Mecânicas

- Intro SANDERVERSE.
- Dificuldade Básico / Médio / Difícil.
- Partida de 3 minutos.
- Câmera acompanha Sander.
- Minimap mostra o mapa completo.
- Sander e Némesis aparecem no minimapa.
- Energia espalhada pelo mapa.
- Ambos recolhem energia e sobem de nível.
- Némesis possui IA própria.
- Némesis procura energia e depois pode perseguir Sander.
- Floresta/arbustos ficam bloqueados: quando `mapa.png` está disponível, o motor identifica os tons de caminho para impedir a passagem pelo bosque.
- Ataque básico Z.
- Ataque especial X.
- Teleporte C com recarga de 30 segundos.
- Controles por setas.
- Controles touch no celular.
- Pausa.
- Sons simples gerados no navegador.

## Importante sobre o mapa

A colisão não depende de desenhar um novo mapa. O `mapa.png` continua sendo a arte principal.

Quando o PNG está disponível, `game.js` cria uma máscara de navegação a partir das cores da imagem. Os caminhos em tons areia/amarelo são tratados como transitáveis e a vegetação verde como bloqueio.

Se o seu mapa tiver áreas especiais que também devam ser transitáveis, ajuste a função:

```js
function pathPixel(x,y)
```

Se for necessário um controle 100% manual, a lista `fallbackBlocks` pode ser usada como camada adicional.

## GitHub Pages

1. Crie um repositório.
2. Envie os quatro arquivos.
3. Crie `assets/`.
4. Coloque os três PNGs na pasta.
5. Em Settings → Pages, selecione a branch principal e `/root`.
6. Abra o endereço do GitHub Pages.

## Controles

PC:
- Setas: movimentação
- Z: ataque
- X: especial
- C: teleporte
- ESC: pausa

Celular:
- Direcional esquerdo: movimentação
- Z: ataque
- X: especial
- C: teleporte

## Próximas etapas

1. Substituir os fallbacks pelos sprites finais.
2. Ajustar os pontos de energia para coincidir exatamente com os caminhos.
3. Criar animações específicas de ataque.
4. Criar efeitos de aura do SANDERVERSE.
5. Criar fases 2/3.
6. Criar sons próprios e música.
7. Adicionar telas cinematográficas de vitória/derrota.


## Correção desta versão

Esta distribuição inclui os assets dentro do próprio projeto e usa o mapa real da Estação Paulista como PNG válido. O tamanho do mundo é lido automaticamente do mapa, evitando que a câmera/canvas use uma altura incorreta. O minimapa mostra o mapa completo e os marcadores de Sander e Némesis em tempo real.
