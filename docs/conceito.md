# O conceito do NEXO

## A ideia inicial

Desenvolver uma aplicação gamificada voltada à didática da Matemática do Ensino Fundamental, que use elementos de RPG e aventura em missões com desafios matemáticos. O estudante progride na história enquanto aprende ou revisa conceitos da matéria. O jogo gera um relatório das fases que o professor acessa para diagnosticar e avaliar o desempenho.

O jogo, nesse sentido, é uma **ferramenta de ensino**: desperta o interesse dos estudantes pelo conteúdo de forma mais divertida e dinâmica, sem substituir o professor.

## Objetivos

1. **Engajar:** dar ao estudante um motivo dentro da história para resolver cada problema.
2. **Ensinar pela ação:** representar cada conceito por um gesto no mundo do jogo (repartir, despejar, encaixar, medir, ajustar uma regra).
3. **Progredir com sentido:** organizar os conteúdos numa trilha, das operações e frações à proporcionalidade, à linguagem algébrica e às funções.
4. **Dar visibilidade ao professor:** transformar cada tentativa em indício sobre os tópicos da grade curricular, sem virar nota automática.
5. **Servir à pesquisa:** permitir, com consentimento e sem identificação, registrar as interações para estudar como o pensamento matemático se desenvolve.

## Público

Estudantes do Ensino Fundamental, do 2º ao 9º ano, com duas trilhas:
- **trilha completa** (2º ao 7º ano): todas as regiões, em ordem;
- **trilha rápida** (8º e 9º anos): as regiões dos anos iniciais viram aquecimento opcional, e o caminho principal começa na relação entre grandezas.

## Escolhas de design

### Sem enunciados, sem formulários

As missões não abrem janelas com perguntas. O personagem fala uma frase curta, que apresenta a situação e não explica a regra, e o estudante age na cena. Em vez de digitar números, ele carrega objetos, puxa alavancas e gira mostradores.

### Consequência no lugar de "errado"

O retorno de cada tentativa aparece no próprio mundo:
- a plantação que recebeu água demais fica encharcada, e a que recebeu de menos fica seca nas pontas;
- a energia transborda acima da marca prevista ou para abaixo dela;
- a peça que não cabe no molde volta para a mão.

### Contra a tentativa e erro às cegas

Várias mecânicas foram redesenhadas para que ajustar valores ao acaso não resolva:
- as lâmpadas da Torre só acendem quando o estudante testa a regra;
- a previsão da Oficina é uma marca no tubo de saída, conferida depois;
- o gráfico do Núcleo é montado com os pontos que o próprio estudante gerou.

### Leis que viram ferramentas

Cada regra descoberta (as partes do lago, a receita do Orin, a máquina de produção, as rotas, a grade de energia) entra no **Códice das Leis do Nexo**. Depois disso, o estudante pode usá-la para calcular, no Códice ou no Calculador Arcano.

### A história também ensina

O antagonista, Vesper, é um aprendiz que rompeu o Núcleo **tentando adivinhar um número em vez de descobrir a regra**. A mensagem do jogo está na própria trama.

### Dicas como apoio, não como atalho

O estudante pode pedir até três dicas por missão, cada vez mais concretas. Depois de três erros, uma dica aparece sozinha. Dicas e apoios automáticos entram no relatório do professor.

## Acessibilidade

- texto maior, alto contraste, menos animação e legendas dos sons (lidas por leitores de tela);
- jogável com teclado, mouse, toque e controle de videogame, incluindo controles adaptados;
- efeitos sonoros sintetizados no próprio navegador.

## Ética e dados

- Os estudantes entram por **apelido ou código**, nunca pelo nome completo.
- Os registros do Modo Pesquisa ficam **só no computador** e exigem um ID de participante sem nome.
- Antes de qualquer coleta com estudantes: autorização institucional, termo de consentimento dos responsáveis (LGPD, dados de menores) e assentimento dos estudantes.

## Próximos passos

- Validar as decisões pedagógicas e os números das missões com especialistas.
- Fazer um teste-piloto com estudantes para ajustar clareza, nível e engajamento.
- Concluir a edição Magitech, com ferramentas usadas sobre os objetos do mundo, e a versão em Godot, com arte nova.
