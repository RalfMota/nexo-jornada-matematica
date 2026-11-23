# NEXO — Uma Jornada Matemática

**Um jogo de aventura em que a Matemática do Ensino Fundamental é a própria ação, e não um questionário dentro do jogo.**

O jogador chega à vila de Nexo logo depois de uma chuva de meteoros. O impacto rachou o Cristal do Nexo, e as pessoas esqueceram como usar a matemática no dia a dia: ninguém lê o relógio, o troco da padaria não fecha, a receita desanda. Para reconectar a vila, o jogador percorre seis regiões, ajuda os guardiões de cada uma e resolve missões em que dividir, comparar, medir e generalizar são gestos feitos no mundo: repartir sementes entre canteiros, abrir comportas com a fração certa de água, montar a regra de uma máquina.

Este repositório apresenta **o conceito do projeto**: a ideia inicial, a proposta pedagógica, a história e o desenho das missões. O código do jogo é mantido em um repositório separado.

## Por que este projeto existe

O NEXO nasceu de uma pergunta de sala de aula: como fazer o estudante do Ensino Fundamental **querer** resolver um problema de matemática, e não só responder a um enunciado?

A proposta é uma aplicação gamificada para a didática da Matemática do Ensino Fundamental, que usa elementos de RPG e aventura. O estudante progride na história enquanto aprende e revisa conceitos. Cada missão gera indícios sobre o que ele já domina, e o professor acompanha esse percurso num painel próprio, para diagnosticar e planejar. O jogo serve como ferramenta de ensino que desperta o interesse pelo conteúdo de forma mais divertida e dinâmica.

## Os princípios

1. **A matemática acontece na ação.** Não há formulários nem enunciados longos. O personagem diz uma frase curta, e o estudante age na cena: pega, leva, divide, encaixa, puxa a alavanca.
2. **O erro é informação, não punição.** Uma resposta errada tem consequência visível no mundo: a plantação fica encharcada ou seca, a caixa não cabe, a energia transborda. O estudante pode tentar de novo.
3. **Descobrir a regra, não chutar o número.** As mecânicas são pensadas para que a tentativa e erro às cegas não funcione. Testar, comparar e prever vale mais.
4. **Cada regra descoberta vira ferramenta.** As leis encontradas nas missões entram num Códice e passam a ser usadas para calcular nas missões seguintes.
5. **O professor enxerga o pensamento.** Acertos, erros, dicas e tempo são registrados por missão e etapa, cruzados com a grade curricular, e viram um relatório por estudante e por tópico.
6. **Acessível e respeitoso com os dados.** Texto maior, alto contraste, legendas dos sons, menos animação, teclado, toque e controle. Os estudantes entram por apelido, nunca pelo nome completo.

## A jornada

| # | Região | Guardião | Conteúdo |
|---|---|---|---|
| 0 | Praça do Nexo e Cratera (prólogo) | Lyra | contagem e composição do 10 (quadrado mágico) |
| 1 | Vale dos Recursos | Tainá | divisão com resto; frações de uma quantidade |
| 2 | Mercado das Trocas | Orin | agrupamento; proporcionalidade; preço por unidade e porcentagem |
| 3 | Oficina dos Construtores | Kael | relações entre grandezas (y = 3x; y = 2x + 4) |
| 4 | Estação das Rotas | Serah | comparação de custos e o primeiro gráfico (5 + 3d contra 15 + 2d) |
| 5 | Torre dos Padrões | Nyla | generalização e escrita de regras (h = 3n + 1) |
| 6 | Núcleo do Nexo | Lyra | função afim: teste, valor de entrada e gráfico |

**Desafios extras:** simetria de reflexão, perímetro e área, e equação do 2º grau como problema de área.

As regiões se abrem em ordem. Há uma **trilha completa** (2º ao 7º ano) e uma **trilha rápida** (8º e 9º anos), em que as regiões dos anos iniciais viram aquecimento opcional.

## Documentos

- [`docs/conceito.md`](docs/conceito.md): a ideia inicial, os objetivos e as escolhas de design.
- [`docs/historia.md`](docs/historia.md): o mundo, os personagens e o roteiro.
- [`docs/missoes.md`](docs/missoes.md): cada missão, o conteúdo e o que o estudante faz.
- [`docs/professor.md`](docs/professor.md): como o professor usa o jogo e o que ele vê.
- [`docs/roteiro-teste-piloto.md`](docs/roteiro-teste-piloto.md): o roteiro do teste-piloto com estudantes.

## Situação do projeto

- **Protótipo jogável no navegador**, com todas as regiões, o Painel do Professor, a turma online e o Modo Pesquisa.
- **Edição Magitech em desenvolvimento**, com ferramentas que o estudante usa sobre os objetos do mundo (Compasso, Calibrador, Visor e Matriz).
- **Versão em Godot em desenvolvimento**, com arte nova.
- Os números das missões são escolhas de design e **ainda precisam passar por teste com estudantes** antes de valerem como instrumento de pesquisa.

## Tecnologias

O projeto tem duas versões do jogo e uma linha de produção de arte. O código fica no repositório separado; aqui está o que cada parte usa.

### Protótipo no navegador

| Parte | Tecnologia |
|---|---|
| Linguagens | JavaScript (módulos ES, sem framework de interface), HTML5 e CSS3 |
| Motor do jogo | [Phaser 3](https://phaser.io/) (3.90) |
| Empacotamento | [Vite](https://vite.dev/) 7, com um plugin próprio que copia a trilha sonora para a versão publicada |
| Ambiente | [Node.js](https://nodejs.org/) e npm |
| Hospedagem | [Vercel](https://vercel.com/), com funções sem servidor para a turma online |
| Dados da turma online | Vercel Blob (`@vercel/blob`) |
| Dados no computador | `localStorage` para os perfis e IndexedDB para o Modo Pesquisa, com exportação em CSV e JSON |
| Som | Web Audio API: efeitos sonoros sintetizados no próprio navegador |
| Fontes | Google Fonts, com as fontes do sistema quando não há internet |
| Testes | `node --test` (testes das regras) e [Playwright](https://playwright.dev/) (testes no navegador e jogada completa automática) |

### Versão em Godot (em desenvolvimento)

| Parte | Tecnologia |
|---|---|
| Motor | [Godot Engine](https://godotengine.org/) 4.7 |
| Linguagens | GDScript e a linguagem de shaders do Godot (vento, árvores, neblina e troca de paleta de cores) |
| Renderização | GL Compatibility, para rodar no navegador (WebGL 2) |
| Exportação | Web (WebAssembly), primeiro; Windows depois |
| Recursos do motor | `CharacterBody2D`, `AnimationPlayer` e `AnimationTree`, navegação dos moradores, save em `user://` (IndexedDB no navegador) |
| Fonte | Fredoka |

### Produção de arte

| Ferramenta | Uso |
|---|---|
| [LibreSprite](https://libresprite.github.io/) | pixel art à mão e acabamento dos personagens (arquivos `.ase`) |
| [ImageMagick](https://imagemagick.org/) | conversão e montagem de imagens nos scripts de produção |
| Scripts em Node.js | conversão das referências, montagem dos personagens em camadas, folhas de animação e exportação da arte para o Godot |
| Playwright | roda os módulos da versão web para exportar o cenário para o Godot |
| Python | apoio pontual (servidor local e um script de revisão) |
| SpriteCook e SpriteKiln | geração de sprites e animações de personagens |
| ChatGPT e Gemini | folhas de referência visual para a direção de arte |

### Desenvolvimento e apoio

| Ferramenta | Uso |
|---|---|
| Git e GitHub | controle de versão |
| Visual Studio Code, com Live Server | edição e teste local da versão web |
| Claude Code | apoio à programação, aos testes e à documentação |
| Codex CLI | avaliação automática da direção de arte, revisada depois pela direção |

## Direitos

© 2026 Ralf Mota. Todos os direitos reservados. Este repositório é público para divulgação do projeto. O texto, a história, os personagens e o desenho das missões não podem ser reproduzidos nem adaptados sem autorização do autor. Veja [`LICENSE`](LICENSE).

## Autor

Ralf Mota — [github.com/RalfMota](https://github.com/RalfMota)
