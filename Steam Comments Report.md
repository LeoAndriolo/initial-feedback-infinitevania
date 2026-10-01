# Infinitevania - Feedback de comentários da Steam

Relatório para a equipe JHT Games | 29 de setembro de 2026 | [Página do jogo na Steam](https://store.steampowered.com/app/1983620/Infinitevania/) (App ID 1983620)

O relatório faz uma análise das avaliações de Infinitevania e compara os relatos com as notas das versões 1.0.1 a 1.0.4. 
O jogo recebeu elogios à movimentação, à exploração e à dublagem brasileira. 
A tabela abaixo resume o que merece investigação e o que já teve uma correção anunciada.

## Decisão rápida

| Tema | Situação nas notas oficiais | Próxima ação |
| --- | --- | --- |
| Recursos após morte | Relato isolado de 20/09, posterior à 1.0.4; sem correção específica anunciada. | Reproduzir o comportamento antes de classificar como bug. |
| Resposta dos controles | Crítica de 13/09; sem mudança de tempo de resposta anunciada. | Medir entrada, animação e ação; observar jogadores novos. |
| Save da demo | A 1.0.3 trata dados corrompidos, sem mencionar migração da demo. | Testar save da demo válido e inválido se pertinente. |
| Colisões e rotas | Correções específicas nas versões 1.0.1 a 1.0.4. | Fazer regressão dirigida; fechar casos já resolvidos. |
| Crashes e travadas | A 1.0.2 anuncia correção de crashes em portáteis e PCs antigos. | Verificar dispositivos e trechos dos relatos antigos. |

Notas consultadas: [1.0.1 (01/08)](https://store.steampowered.com/news/app/1983620/view/1839676055889734); [1.0.2 (07/08)](https://store.steampowered.com/news/app/1983620/view/1840310314343644); [1.0.3 (15/08)](https://store.steampowered.com/news/app/1983620/view/1840944183782849); [1.0.4 (18/09)](https://store.steampowered.com/news/app/1983620/view/1844115010494693). A 1.0.4 é a última publicação oficial encontrada até a coleta. Uma avaliação de agosto foi editada para registrar que as travadas na primeira luta haviam sido resolvidas ([08/08, 2,0 h - atualização do relato](https://steamcommunity.com/profiles/76561198176811909/recommended/1983620/)).

## Base e limite da análise

A API pública da Steam retornou 303 avaliações em 29/09/2026 (281 positivas, 22 negativas; compras e chaves). A amostra tem tamanho de 100: todas as 22 negativas e 78 positivas sorteadas entre julho, agosto e setembro. 

**n/100* (mencionado abaixo) conta menções nesta amostra, não a porcentagem de jogadores afetados**, pois todas as críticas foram incluídas de propósito. Uma avaliação conta uma vez em cada tema. Não testei a build atual comparando com as críticas; ausência nas notas não prova ausência de correção.

## Relatos a investigar na versão atual

### Recuperação de recursos após morte

relato posterior à 1.0.4 | Reproduzir antes de classificar

Um jogador relata dificuldade para recuperar recursos após morrer e descreve uma caveira que não aparece como esperado. O texto não permite determinar se falhou a caveira, a interação ou a regra de recuperação ([20/09, 1,9 h - relato original](https://steamcommunity.com/profiles/76561198081145965/recommended/1983620/)).

**Sugestão:** Reproduzir morte, retorno e coleta com diferentes saves. 
Critério: a regra prevista fica clara e, se houver falha, o recurso pode ser recuperado de forma consistente.

### Resposta dos controles

9/100\* | Sem ajuste específico anunciado

Alguns jogadores percebem atraso ou peso ([13/09, 0,7 h - atraso em combate](https://steamcommunity.com/profiles/76561197974956415/recommended/1983620/)), enquanto outros elogiam precisão. Uma mudança global sem medição pode afetar trechos que funcionam.

**Sugestão:** Comparar (através de debug) o momento de ativação do botão, da animação, do deslocamento e do golpe em encontros citados. 
Critério: a causa de qualquer atraso reproduzido é identificada e o ajuste não piora as seções elogiadas.

### Save da demo

1/100\* | Relato antigo; caso distinto de save corrompido (Baixa importância pois a demo parece não estar mais disponível)

Um jogador relatou carregamento infinito ao abrir seu save da demo ([25/07, 8,7 h - save da demo](https://steamcommunity.com/profiles/76561198303303614/recommended/1983620/)). A 1.0.3 menciona dados corrompidos, mas não migração da demo.

**Sugestão:** Testar saves válidos e inválidos da demo na versão atual.
Critério: o save abre ou mostra uma mensagem recuperável, sem carregamento infinito.

## Regressão das correções publicadas

### Colisão e acesso fora da sequência

8/100\* | Correções específicas na 1.0.1 a 1.0.4

Os relatos de entrada em paredes, quinas indevidas e passagem por portões na amostra são de julho ([27/07, 6,5 h - portão no castelo](https://steamcommunity.com/profiles/76561198942236192/recommended/1983620/); [25/07, 8,7 h - atravessar paredes](https://steamcommunity.com/profiles/76561198303303614/recommended/1983620/)). As notas citam várias rotas corrigidas, sem comprovar todos os cenários.

**Sugestão:** Repetir rotas relatadas com quinas, dano perto de portões e espinhos. 
Critério: o personagem não antecipa um save, não atravessa barreiras previstas e não fica preso; encerrar os casos já resolvidos.

### Crashes e travamentos

6/100\* | Crashes de hardware corrigidos na 1.0.2

Há relatos antigos em portáteis e no chefe final ([28/07, 36,9 h - ROG Ally X e chefe final](https://steamcommunity.com/profiles/76561199472060310/recommended/1983620/)). A nota da 1.0.2 não especifica todos os cenários nem correção geral de travamentos.

**Sugestão:** Testar primeira luta, segunda área e chefe final em PC low-end e portáteis (se possível); registrar logs e tempo de quadro. 
Critério: nenhum crash ou congelamento nos cenários verificados.

## Playtests de experiência de usuário

### Primeira floresta

5/100\* | Ritmo inicial a validar

Alguns relatam floresta longa ou impressão inicial de linearidade ([29/07, 0,6 h - abandono na floresta](https://steamcommunity.com/profiles/76561197996226472/recommended/1983620/); [29/07, 6,9 h - começo lento, mas melhora depois](https://steamcommunity.com/profiles/76561198018911671/recommended/1983620/)).

**Sugestão:** Adicionar indicadores para medir o progresso de jogadores novos do início até ganhar a primeira habilidade de mobilidade. 
Critério: compreendem objetivo e descobrem o apelo da exploração sem instrução externa; alterar apenas pontos de abandono reproduzidos.

### Leitura dos inimigos

6/100\* | Alcance e antecipação a validar

Jogadores relatam alcance surpreendente ou inimigos sobre plataformas precisas ([06/08, 0,3 h - alcance dos ataques](https://steamcommunity.com/profiles/76561198062347370/recommended/1983620/); [24/07, 11,2 h - inimigos em trechos precisos](https://steamcommunity.com/profiles/76561198317053451/recommended/1983620/)). Outros elogiam os chefes.

**Sugestão:** Verificar hitboxes contra as animações e observar mortes nesses encontros.
Critério: jogadores conseguem explicar por que sofreram dano e têm tempo de reação apropriado ao ataque.

### Visão nos saltos

2/100\* (pedidos explícitos) | Câmera do castelo ajustada na 1.0.3; pedido ainda não anunciado

Dois jogadores pedem olhar para baixo antes de certos saltos (look foward) ([30/07, 4,7 h - pedido de câmera](https://steamcommunity.com/profiles/76561198081171005/recommended/1983620/); [25/07, 8,6 h - pedido semelhante](https://steamcommunity.com/profiles/76561198415650031/recommended/1983620/)).

**Sugestão:** Prototipar olhar para baixo (ou direção apontada) ou enquadramento pontual. 
Critério: o jogador vê destino e perigo antes de saltar sem perder o personagem de vista.

## Oportunidades após validação

**Economia e habilidades:** 6/100\* mencionam custo, farm ou opções pouco úteis. As versões 1.0.2 a 1.0.4 ajustaram Sage, Kaminari, fireball e Orbital Spirit, sem anunciar revisão do farm final. Medir moedas de uma partida normal e uso de equipamentos antes de mudar preços ([26/07, 5,4 h - farm para 100%](https://steamcommunity.com/profiles/76561197978556496/recommended/1983620/)).

**Conforto e dispositivos:** um pedido de desativar tremor de tela ([28/07, 2,6 h - tremor](https://steamcommunity.com/profiles/76561198107775270/recommended/1983620/)) e um relato de mapa/menu sem resposta com Steam Controller em uma área ([28/07, 36,9 h - controle](https://steamcommunity.com/profiles/76561199472060310/recommended/1983620/)). Testar o controle e considerar intensidade configurável de tremor.

**Mapa, duração e voz:** as opiniões se dividem; 12/100\* mencionam duração ou variedade, inclusive como elogio à experiência compacta. Nove trazem ressalvas sobre voz ou repetição, enquanto 16 elogiam áudio ou dublagem. A 1.0.3 ajustou o volume de diálogos finais e a 1.0.4 corrigiu um efeito sonoro; testar públicos distintos antes de ampliar conteúdo ou alterar falas.

## Pontos fortes a preservar

Na amostra, 19 avaliações elogiam explicitamente movimento ou combate, 16 destacam áudio ou dublagem e 14 valorizam exploração ou progressão. A dublagem em português, as referências ao gênero e a experiência compacta são qualidades importantes para parte dos jogadores. Os ajustes sugeridos devem ser testados contra essas forças.

## Como usar este relatório

Os status acima comparam comentários públicos e notas oficiais, não constituem reprodução técnica dos bugs. Começar pelos relatos não cobertos nas notas, fazer regressões direcionadas nas correções anunciadas e transformar em correção apenas os problemas reproduzidos. Os links levam às avaliações originais e aos updates.

Fonte da amostra: [API de avaliações da Steam](https://store.steampowered.com/appreviews/1983620?json=1&filter=recent&language=all&purchase_type=all&num_per_page=100). Análise temática realizada em 29/09/2026. Uma avaliação pode contribuir para vários temas, mas apenas uma vez por tema.
