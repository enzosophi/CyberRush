# CyberRush

Jogo de corrida infinita em 3D com estética synthwave, feito em **um único arquivo HTML** com JavaScript puro e [Three.js](https://threejs.org/) (r128, via CDN). Inspirado no conceito do *.kkrieger*: quase tudo é gerado por código, incluindo texturas, cenário, personagem e sons.

## Como jogar

Abra o `index.html` em qualquer navegador moderno. É preciso estar conectado à internet na primeira vez, para carregar o Three.js.

| Tecla | Ação |
|---|---|
| `A` `D` / `←` `→` | Mover para os lados |
| `Espaço` | Pular (segure durante a queda para planar, se tiver a melhoria) |
| `S` / `↓` | Deslizar (no ar: descer rápido) |
| `Shift` | Dash (melhoria) |
| `Enter` / `R` | Começar / reiniciar |
| `L` | Loja |

## Destaques

- **Pista contínua em 3 faixas**, com corredores, zigue-zagues, buracos curtos, barreiras para deslizar e plataformas aéreas em dois andares.
- **Cenário dinâmico:** a cada 900 m a zona muda (Sunset Drive → Neon City → Deep Space → Aurora). Céu, neblina, luzes, cores da pista e objetos de fundo se misturam suavemente.
- **Corredor estilo robô synthwave:** capacete cromado, viseira com painel de LED animado e jaqueta de couro, com animações de corrida, pulo e deslize capturadas (Mixamo) e transferidas para o modelo feito por código.
- **Perks na pista:** escudo, super ímã, cristais ×2, pulo lunar, fantasma e turbo.
- **Loja de melhorias** com progresso salvo no navegador (`localStorage`).
- Texturas, sons (WebAudio) e modelos 100% procedurais, sem nenhum arquivo de imagem ou áudio.

## Estrutura

```
index.html            o jogo completo (HTML + CSS + JS)
anim_src/convert.html ferramenta que converte animações FBX do Mixamo para o rig do jogo
```

### Convertendo novas animações (opcional)

Os arquivos `.fbx` do Mixamo não estão no repositório. A licença permite usá-los em projetos, mas não redistribuí-los. Para regenerar ou adicionar animações:

1. Baixe do [Mixamo](https://www.mixamo.com) no formato **FBX, Without Skin, In Place**.
2. Coloque-os em `anim_src/` com os nomes `running.fbx`, `jump.fbx` e `slide.fbx`.
3. Sirva a pasta com um servidor local (por exemplo, `python -m http.server`) e abra `anim_src/convert.html`.
4. O resultado (`window.MOCAP`) é o objeto `MOCAP` embutido no `index.html`.
