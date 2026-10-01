# Relatório de Playtest / QA

## Graphics

- A animação de background do Main Menu funciona bem e já introduz visualmente o personagem principal.
- O parallax do level inicial é bem executado.
- As montanhas mais distantes possuem uma cor muito próxima à das nuvens, reduzindo um pouco a separação visual entre os planos.
- A tipografia utilizada nas páginas do Bestiary possui baixa legibilidade. As letras são muito verticais e ficam visualmente muito próximas umas das outras.
- Durante o teste técnico, percebi que castiçais e lustres possuem interação/destruição, um detalhe visual interessante do cenário.

## GUI

- O Main Menu esconde o cursor do mouse, aparentemente de forma intencional. Isso também evita inconsistências relacionadas às áreas clicáveis dos botões.
- Os botões possuem bom feedback visual e SFX nos estados de hover e selected.
- O background preto do panel de Settings parece um pouco agressivo comparado ao restante da interface. Consideraria utilizar um cinza bem escuro para suavizar.
- A localization para 10 idiomas é um ponto bastante positivo e amplia bem o mercado potencial.
- A opção de tamanho do texto apresentou pouca diferença perceptível no meu monitor de 23". Seria interessante verificar a diferença em telas maiores e televisores.
- Gostei bastante do design dos botões no panel Controls.
- O feedback sonoro ao alternar entre opções no Controls também funciona bem.
- A cor interna das representações das teclas possui contraste relativamente baixo, embora o conteúdo continue legível.
- Há suporte para resolução até 4K.
- As opções para desativar CRT Filter, Lights, Particles e Screen Shake, além dos Color Blindness Modes, ajudam bastante no quesito acessibilidade.
- A divisão das configurações de áudio em diferentes canais também é bem profissional.
- A maioria dos menus pode ser controlada por Arrow Keys/WASD, mas o panel de Credits exige mouse scroll para navegar verticalmente. Seria interessante manter o padrão de navegação por teclado.
- O indicador Confirm / Enter no rodapé de Settings parece desnecessário em algumas telas, já que as alterações são aplicadas imediatamente. Ele faz mais sentido no Main Menu.
- As sombras nos textos dos comandos do rodapé ajudam na legibilidade, mas em algumas partes do Main Menu ainda há pouco contraste com o background, especialmente sobre a mão do personagem segurando a esfera.
- A transição Start → Choose Save possui ótimo feedback visual e sonoro.
- O fundo totalmente preto de Choose Save/Load também parece um pouco agressivo, embora a interface em si esteja muito bem executada.

## Performance

- Nenhum problema relevante de performance foi identificado até o momento.
- Não percebi stutters, quedas significativas de FPS ou problemas aparentes durante as transições testadas.

## Music

- Nenhum problema específico identificado até o momento.
- Continuar observando consistência de volume e transições entre áreas durante os próximos testes.

## SFX

- Bom feedback sonoro nos botões do Main Menu.
- Bom feedback sonoro ao navegar pelas opções do Controls.
- A transição Start → Choose Save utiliza bem SFX em conjunto com o feedback visual.

## Gameplay

- O level design inicial orienta muito bem o jogador: o caminho para a direita é inicialmente bloqueado enquanto uma escadaria naturalmente incentiva a exploração na outra direção.
- A dificuldade encontrada até agora parece adequada para o gênero.
- A história e a progressão estão bem implementadas.
- O segundo encontro/fase de Etrom apresentou ataques bem construídos e interessantes de enfrentar.
- Existe uma possível inconsistência na combinação de inputs:
  - É possível pular em uma direção mantendo `Space + D/Right Arrow` e executar um ataque com `K`.
  - Na mesma condição, não é possível executar Dash com `I`.
  - O Dash pode ser utilizado no ar se `Space` for solto após o início do pulo.
- Vale investigar se esse comportamento de Dash é intencional ou uma consequência da forma como os inputs simultâneos estão sendo tratados.

## Misc Issues

### Possível collider inesperado

Durante o teste técnico, encontrei um collider em uma área secreta do level inicial.

**Sugestão:** verificar se o collider é intencional e se corresponde corretamente à geometria visual da área.

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
- Platform: PC
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
   - Os colliders dos espinhos são menores do que a arte, oferecendo uma margem de segurança para o jogador. Considero isso uma boa decisão de design.
   - Identifiquei objetos destrutíveis no cenário que não havia percebido durante o primeiro playtest.
   - O player possui dois Box Colliders que apresentam um pequeno atraso em relação ao movimento do personagem.
   - A espada permaneceu em estado flamejante após uma troca forçada de cena. Isso provavelmente ocorreu porque o estado do personagem não foi resetado ao mudar de cena dessa forma.


## Final Thoughts

Minha primeira impressão é bastante positiva. O jogo parece tecnicamente sólido e apresenta um nível alto de polish.

Os principais pontos encontrados até agora são predominantemente relacionados a consistência de UI, contraste/legibilidade e comportamento de inputs simultâneos, em vez de bugs graves.

No próximo teste, o foco deve ficar principalmente em input combinations, edge cases, state transitions, save/load, UI navigation e possíveis softlocks.
