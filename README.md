# Relatório de Playtest Infinitevania

Este relatório reúne o playtest e QA inicial de Infinitevania v1.0.4, com foco em bugs, UI/UX, inputs, legibilidade e comportamento técnico. O processo incluiu um playtest natural e um Tech Test utilizando BepInEx, UnityExplorer e um plugin próprio para visualizar colliders.

## Graphics

Não aprofundei o estudo sobre a composição artística ou color pallete utilizada, acredito que possui pessoas mais capazes para isso. As notas que tomei foram apenas fatos que chamaram-me a atenção.

- A animação de background do Main Menu funciona bem e já introduz visualmente o personagem principal.
- O parallax do level inicial após a cutscene é bem executado, com o único detalhe de que as montanhas mais distantes possuem uma cor muito próxima à das nuvens, reduzindo um pouco a separação visual entre os planos.
- A tipografia utilizada nas páginas do Bestiary (livro de monstros) possui baixa legibilidade. As letras são muito verticais e ficam visualmente muito próximas umas das outras.
- Durante o teste técnico, percebi que castiçais e lustres possuem interação/destruição, um detalhe visual interessante do cenário.

## GUI

O intuito aqui era verificar consistência nos elementos e em seu comportamento.

- O Main Menu esconde o cursor do mouse, aparentemente de forma intencional. Isso pode evitar inconsistências relacionadas às áreas clicáveis dos botões.
- Os botões possuem bom feedback visual e SFX nos estados de hover e selected, bom design.
- O background preto do panel de Settings parece um pouco agressivo comparado ao restante da interface. Consideraria utilizar um cinza bem escuro para suavizar ou um background animado.
- A localization para 10 idiomas é um ponto bastante positivo e amplia bem o mercado potencial.
- A opção de tamanho do texto apresentou pouca diferença perceptível no meu monitor de 23". Acredito que a diferença em telas maiores e televisores é mais perceptível.
- Gostei bastante da arte dos botões no panel Controls.
- O feedback sonoro ao alternar entre opções no Controls também funciona bem, bom design.
- A cor interna das representações das teclas possui contraste relativamente baixo, embora o conteúdo continue legível.
- As opções para desativar CRT Filter, Lights, Particles e Screen Shake, além de Color Blindness Mode, ajudam bastante no quesito acessibilidade.
- A divisão das configurações de áudio em diferentes canais é bem profissional, bom design.
- A maioria dos menus pode ser controlada por Arrow Keys/WASD, mas o panel de Credits exige mouse scroll para navegar verticalmente. Seria interessante manter o padrão de navegação por teclado (acredito não ter problema em controles).
- O indicador Confirm / Enter no rodapé de Settings parece desnecessário em Settings, já que as alterações são aplicadas imediatamente. Ele faz mais sentido no Main Menu.
- As sombras nos textos dos comandos do rodapé ajudam na legibilidade, mas em algumas partes do Main Menu ainda há pouco contraste com o background, especialmente sobre a mão do personagem segurando a esfera.
- A transição Start → Choose Save possui ótimo feedback visual e sonoro na transição, bom design.
- O fundo totalmente preto de Choose Save/Load também parece um pouco agressivo, embora a interface em si esteja muito bem executada.

## Performance

O vídeo do playtest inicial (link abaixo) possui algumas estatísticas de performance, mas não explorei muito.

- Nenhum problema relevante de performance foi identificado até a parte que cheguei.
- Não percebi stutters, quedas significativas de FPS ou problemas aparentes durante as transições testadas.

## Music

Novamente, não sou especialista para aprofundar, mas a trilha sonora e SFX foram bem agradáveis. Joguei com diálogo em inglês e acredito que os diálogos em português devem estar melhores como citado por comentários na Steam.

- Nenhum problema específico identificado.
- Continuar observando consistência de volume e transições entre áreas durante os próximos testes.

## SFX

Foquei mais em feedback de UI.

- Bom feedback sonoro nos botões do Main Menu.
- Bom feedback sonoro ao navegar pelas opções do Settings/Controls.
- A transição Start → Choose Save utiliza bem SFX em conjunto com o feedback visual.

## Gameplay

Além do playtest inicial, gravei um tech test com mods para verificar colliders e o comportamento de algumas mecânicas.

- O level design inicial (+onboarding) orienta muito bem o jogador: o caminho para a direita é inicialmente bloqueado enquanto uma escadaria naturalmente incentiva a exploração na outra direção.
- A dificuldade encontrada durante o playtest pareceu adequada para o gênero.
- A história e a progressão estão bem implementadas.
- O segundo encontro/fase de Etrom apresentou ataques bem construídos e interessantes de enfrentar.
- Existe uma possível inconsistência na combinação de inputs:
  - É possível pular em uma direção mantendo `Space + D/Right Arrow` e executar um ataque com `K`.
  - Na mesma condição, não é possível executar Dash com `I`.
  - O Dash pode ser utilizado no ar se `Space` for solto após o início do pulo.
- Vale investigar se esse comportamento de Dash é intencional ou uma consequência da forma como os inputs simultâneos estão sendo tratados.

## Misc

### Possível collider inesperado

Durante o teste técnico, encontrei um collider em uma área secreta do level inicial.

### Credits dependente de mouse

A navegação geral utiliza teclado, enquanto Credits exige mouse scroll.

**Sugestão:** permitir `W/S`, Arrow Keys ou `Page Up/Page Down` para manter consistência de navegação.

### Legibilidade do Bestiary

A fonte das páginas do Bestiary pode dificultar leitura prolongada.

**Sugestão:** revisar spacing, largura dos caracteres ou utilizar uma variante mais legível para textos longos.

## Notes

### Test Environment

- Version: `1.0.4`
- Build ID: `25357912`
- Platform: PC (Ryzen 5 3500X / 16GB RAM / SSD / GEFORCE GTX 1660 SUPER (6GB))
- OS: Windows 10
- Input: Keyboard + Mouse
- Recording: OBS

### First Playtest

- Duração: **38 minutos**
- Nenhum bug relevante encontrado.
- O jogo apresenta um nível alto de polish.
- História e progressão funcionaram bem durante o primeiro contato.
- A dificuldade parece coerente com o gênero. 
- Como referência pessoal de dificuldade, meu último metroidvania/plataformer foi *Hollow Knight: Silksong*.


### Vídeos da sessão

   Obs: Os vídeos estão sem áudio por uma configuração errada no OBS.

1. **Infinitevania v1.0.4 — 10-01-26**  
   https://youtube.com/live/40l5QkuY76M  
   Playtest de aproximadamente **35 minutos**, sem anotações durante a sessão, com o objetivo de ter um primeiro contato com o jogo.  
   Dei uma olhada nas Settings no início e avancei a história até derrotar uma guerreira na floresta.  
   **Resultado:** nenhum bug ou problema relevante identificado.

2. **Infinitevania Tech Test — 10-01-26**  
   https://youtube.com/live/I7AigENAXBI  
   Tech Test de aproximadamente **15 minutos**.  
   Para esse teste, utilizei o modloader **BepInEx** com dois plugins:
   - **UnityExplorer**
   - Um plugin self-made para exibir os colliders

   O objetivo era verificar como os objetos estavam interagindo por trás da arte e entender melhor a estrutura física das cenas.

   Consegui carregar cenas específicas, o que foi útil porque a GUI do UnityExplorer estava bloqueando os inputs do mouse.

   **Pontos observados:**
   - Os colliders dos espinhos são menores do que a arte, oferecendo uma margem de segurança para o jogador, bom design.
   - Identifiquei objetos destrutíveis no cenário que não havia percebido durante o primeiro playtest (castiçais).
   - O player possui dois Box Colliders que apresentam um pequeno atraso em relação ao movimento do personagem.
   - A espada permaneceu em estado flamejante após uma troca forçada de cena. Isso provavelmente ocorreu porque o estado do personagem não foi resetado ao mudar de cena dessa forma.


## Final Thoughts

Minha primeira impressão é bastante positiva. O jogo parece tecnicamente sólido e apresenta um nível alto de polish.

Os principais pontos encontrados até agora são predominantemente relacionados a consistência de UI, contraste/legibilidade e comportamento de inputs simultâneos, em vez de bugs graves.

No próximo teste, o foco deve ficar principalmente em input combinations, edge cases, state transitions, save/load, UI navigation e possíveis softlocks.
