---
description: Entenda como configurar uma visualização da tela de jornada.
title: Configurar a visualização de uma tela de jornada
feature: Visualizations
role: User
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
TQID: https://experienceleague.adobe.com/pC3wjv6Q7RHRfDfHq75CP2Lqd-HzN-s7iLZ9t4N4ZR0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: aff2ef09-fc60-4018-9197-e2befd623064
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: c6b215f9fe718d0d3e8f81b7f55421c909b69c5a
workflow-type: tm+mt
source-wordcount: 6499
ht-degree: 90%

---

# Configurar a visualização de uma tela de jornada

A Visualização de tela da jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes.

![Tela da jornada](assets/journey-canvas.png)

## Visão geral da tela da jornada

Consulte [Visão geral da tela de jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) para saber mais sobre a tela de jornada, incluindo:

* Recursos principais

* Possíveis insights

* Diferenças entre tela de jornada e fallout

* Detalhes sobre a análise de jornadas do Journey Optimizer

* E muito mais

## Começar a criar uma visualização de tela de jornada

1. Adicione um painel em branco ao projeto, selecione o ícone [!UICONTROL **Visualizações**] no painel à esquerda e arraste a visualização ![GraphPathing](/help/assets/icons/Branch3.svg) [!UICONTROL **Tela de jornada**] para o painel.

   Ou

   Adicione uma visualização de tela de jornada de qualquer uma das maneiras descritas na seção [Adicionar visualizações a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) em [Visão geral de visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Configuração de tela de jornada](assets/journey-canvas-configure.png)

1. Especifique as seguintes informações básicas para configurar a tela de jornada:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Métrica principal**] | Determina a métrica utilizada no cálculo dos valores percentuais e numéricos em cada nó da jornada.<p>**Observação**: o escopo dos dados incluídos em cada valor percentual e numérico é determinado pela métrica que você escolher no campo **[!UICONTROL Container de tela de jornada]**. Por exemplo, se **[!UICONTROL Pessoa]** estiver definida como o container, as estatísticas mostradas na jornada englobarão várias sessões para uma determinada pessoa. Se **[!UICONTROL Sessão]** estiver definida como o container, as estatísticas mostradas na jornada serão restritas a uma única sessão definida para uma determinada pessoa.</p><p>Considere os seguintes exemplos de como a métrica principal afeta os valores percentuais e numéricos de cada nó:</p><ul><li>Se _Pessoas_ for a métrica principal e _Pessoa_ for o container, apenas as pessoas que têm um evento que corresponde aos critérios de cada nó sucessivo na jornada serão movidas pela jornada. O fallout ocorre em um nó quando uma pessoa nunca chegou a qualquer um dos próximos nós imediatos na jornada. Ela pode ter executado outras ações no site, mas não atendeu aos critérios definidos por nenhum dos nós que se seguem imediatamente.</li><li>Se _Pessoas_ for a métrica principal e _Sessão_ for o container, apenas as pessoas que têm um evento que corresponde aos critérios de cada nó na jornada em uma única sessão serão movidas pela jornada. O fallout ocorre em um nó quando uma pessoa nunca chegou a qualquer um dos próximos nós imediatos na jornada em uma única sessão. Ela pode ter executado outras ações no site na sessão, mas não atendeu aos critérios definidos por nenhum dos nós que se seguem imediatamente.</li></ul> <p>A métrica principal afeta os seguintes aspectos da visualização da tela de jornada:</p><ul><li>O número total exibido em cada nó.  <p>Por exemplo, se Eventos for a métrica principal, cada nó mostra o número de pessoas que tiveram um evento que corresponde aos critérios desse nó (e de cada nó anterior que o antecedeu na jornada).</p></li><li>O percentual mostrado em cada nó. (Depois que a visualização for criada, você poderá usar o menu suspenso **[!UICONTROL Valor percentual]** para escolher mostrar o percentual do total, o percentual do nó anterior ou o percentual do nó inicial.)<p>Por exemplo, se Eventos for a métrica principal, cada nó mostrará o percentual de pessoas que tiveram um evento que corresponde aos critérios desse nó (e de cada nó anterior que o antecedeu na jornada).</p></li><li>Quando uma dimensão é adicionada à visualização, os 3 principais nós da visualização são adicionados, com base na métrica principal.</li></ul> |
   | [!UICONTROL **Métrica secundária**] | Determina a métrica secundária que é usada ao calcular os valores percentuais e numéricos em cada nó da jornada. A métrica secundária é opcional. <p>**Observação**: o escopo dos dados incluídos em cada valor percentual e numérico é determinado pela métrica que você escolher no campo **[!UICONTROL Container de tela de jornada]**. Por exemplo, se **[!UICONTROL Pessoa]** estiver definida como o container, as estatísticas mostradas na jornada englobarão várias sessões para uma determinada pessoa. Se **[!UICONTROL Sessão]** estiver definida como o container, as estatísticas mostradas na jornada serão restritas a uma única sessão definida para uma determinada pessoa.</p><p>Quando uma métrica secundária é configurada, ela afeta os seguintes aspectos da visualização da Tela de jornada:</p><ul><li>O número total mostrado em cada nó abaixo da métrica principal. <p>Por exemplo, se Contas for a métrica secundária, o número de contas será mostrado no nó para todas as pessoas que atingiram esse nó na jornada.</p></li><li>O percentual mostrado em cada nó abaixo da métrica principal. (Depois que a visualização é criada, você pode optar por mostrar o percentual do total ou do nó inicial.)</li><p>Por exemplo, se Sessões for a métrica secundária, cada nó mostrará o percentual de sessões que atingiram esse nó na jornada (a porcentagem do total ou do nó inicial).</p></li></ul> |
   | [!UICONTROL **Jornada do Journey Optimizer**]<!-- name? --> | Selecione a jornada do Journey Optimizer que deseja usar como base para sua análise na Tela de jornada. Jornadas com qualquer um dos seguintes status estão disponíveis: Ativo, Interrompido ou Concluído <p>Como alternativa, é possível deixar essa opção em branco caso deseje uma tela em branco a partir da qual a análise será criada no Analysis Workspace.</p> <p>Ao analisar uma jornada do Journey Optimizer na Tela de jornada, ela é exibida com a mesma ordem, sequência e estrutura que tem no Journey Optimizer. Para obter mais informações, consulte [Analisar jornadas do Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) em [visão geral da Tela de jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Observação**: essa opção é exibida somente quando dados do Journey Optimizer são detectados na mesma visualização de dados selecionada no painel do Analysis Workspace ao qual você está adicionando a visualização. Para obter informações sobre como alterar a visualização de dados em um painel no Analysis Workspace, consulte [Visão geral do Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Opcional) Selecione [!UICONTROL **Mostrar configurações avançadas**] e especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Container de tela de jornada**] | Selecione o container no qual você deseja se concentrar na jornada. O container escolhido determina o escopo dos dados capturados na jornada. Isso afeta as estatísticas exibidas na visualização. (Se os nomes dos containers forem diferentes dos nomes padrão mostrados abaixo, eles serão personalizados na visualização de dados.)<ul><li>**Sessão:** restringe as estatísticas da visualização para que se enquadrem em uma única sessão definida para uma determinada pessoa. Isso significa que os números e percentuais exibidos em cada nó (que são baseados nas métricas principal e secundária) devem ocorrer em uma única sessão para cada pessoa. Em outras palavras, uma pessoa pode ser representada várias vezes em uma única jornada.<p>Este container usa a métrica Sessões.</p></li><li>**Pessoa:** (padrão) permite que as estatísticas da visualização englobem várias sessões para uma determinada pessoa. Isso significa que os números e percentuais exibidos em cada nó (que são baseados nas métricas principal e secundária) podem ocorrer em qualquer número de sessões, desde que as sessões pertençam à mesma pessoa. Em outras palavras, uma pessoa só pode ser representada uma vez em uma única jornada.<p>Esse container usa a métrica Pessoas.</p></li></ul> |

1. Selecione [!UICONTROL **Criar**].

   Se você selecionou uma jornada do Journey Optimizer, ela será exibida na mesma ordem, sequência e estrutura que tem no Journey Optimizer. (Somente usuários com acesso ao Journey Optimizer podem selecionar uma jornada do Journey Optimizer.)

   <!-- add screen shot -->

   Se você não selecionou uma jornada do Journey Optimizer, uma tela em branco é exibida, onde você pode começar a adicionar nós à jornada. (Somente usuários com acesso ao Journey Optimizer podem selecionar uma jornada do Journey Optimizer.)

   <!-- add screen shot -->

1. Se você estiver criando uma nova análise a partir de uma tela em branco ou analisando uma jornada do Journey Optimizer, poderá configurar a jornada conforme descrito em [Definir configurações de visualização](#configure-visualization-settings).


## Definir configurações de visualização

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_percentage_value"
>title="Escolha como as porcentagens são calculadas"
>abstract="As porcentagens exibidas em cada nó se baseiam nas métricas primárias e secundárias configuradas. Você pode escolher se as porcentagens estão relacionadas ao nó inicial, ao nó anterior ou a todos os dados no conjunto de relatórios."

<!-- markdownlint-enable MD034 -->

Várias opções de configuração estão disponíveis no cabeçalho da Tela de jornada.

Para definir as configurações da visualização de Tela de jornada:

1. No Analysis Workspace, abra uma visualização existente da Tela de jornada ou [comece a criar uma nova](#begin-building-a-journey-canvas-visualization).

   As opções que permitem configurar a visualização da Tela de jornada estão disponíveis no cabeçalho:

   ![Opções de cabeçalho da Tela de jornada](assets/journey-canvas-header.png)

1. Defina qualquer uma das seguintes configurações exibidas na parte superior da visualização:

   | Configuração | Função |
   |---------|----------|
   | [!UICONTROL **Valor percentual**] | O valor percentual mostrado em cada nó da jornada.<p>![valor percentual](assets/journey-canvas-percentage.png)</p> <p>Considere o seguinte ao configurar os valores percentuais mostrados nos nós da jornada:</p><ul><li>Um percentual é mostrado em cada nó para a métrica principal. Um percentual também é mostrado para a métrica secundária, se uma estiver configurada. (Para obter mais informações sobre as configurações de métrica primária e secundária, consulte [Começar a criar uma visualização de Tela de jornada](#begin-building-a-journey-canvas-visualization).)</li><li>As porcentagens incluem todas as pessoas ou sessões incluídas na visualização de dados no intervalo de datas do painel. A utilização de _pessoas_ ou _sessões_ depende da configuração do container. (Para obter mais informações sobre a configuração do container, consulte [Começar a criar uma visualização de Tela de jornada](#begin-building-a-journey-canvas-visualization).)</li></ul> <p>Escolha entre as seguintes opções:</p> <ul><li>[!UICONTROL **Percentual do nó inicial**]: calcula os percentuais exibidos em cada nó em relação ao nó inicial. Os percentuais se baseiam nas métricas principal e secundária selecionadas. <p>Um _nó inicial_ é um nó que não tem nós conectados anteriores a ele.</p><p>Uma jornada pode conter vários nós iniciais. No entanto, [!UICONTROL **Percentual do total**] será usado se a jornada tiver 2 ou mais nós iniciais que levam a um nó comum. Se quiser usar [!UICONTROL **Percentual do nó inicial**], atualize a jornada para que cada nó na jornada possa ser rastreado até um único nó inicial.</p></li><li>[!UICONTROL **Percentual do nó anterior**]: calcula os percentuais exibidos em cada nó em relação ao nó anterior. Os percentuais se baseiam nas métricas principal e secundária selecionadas.</li><li>[!UICONTROL **Percentual do total**]: calcula os percentuais exibidos em cada nó em relação a todos os dados na visualização de dados. Os percentuais se baseiam nas métricas principal e secundária selecionadas.</li></ul> |
   | [!UICONTROL **Configurações de seta**] | As setas que aparecem entre os nós na Tela de jornada podem ser configuradas para mostrar rótulos e valores personalizados. <p>![configurações de seta](assets/journey-canvas-arrow-settings.png)</p><p>_Rótulos_ são nomes personalizados que aparecem em setas. Somente um único rótulo é exibido em uma determinada seta. Os rótulos podem ser qualquer um dos seguintes e são mostrados nesta ordem de preferência:</p><ol><li>Um nome personalizado adicionado da Tela de jornada (conforme descrito em [Adicionar ou atualizar um rótulo em uma seta](#add-or-update-a-label-on-an-arrow))</li><li>Um rótulo do Journey Optimizer</li><li>Uma condição do Journey Optimizer</li></ol><p>_Valores_ são os números e percentuais que aparecem nas setas e indicam as pessoas ou sessões que passaram de um nó para outro na jornada. (Em outras palavras, aqueles que não desistiram da jornada em uma determinada etapa.) </p><p>As seguintes opções estão disponíveis para jornadas que não foram originadas no Journey Optimizer e para jornadas do Journey Optimizer que não foram significativamente modificadas na Tela de jornada: (modificações significativas incluem adicionar ou remover nós, adicionar ou remover setas ou alterar os componentes de um nó.)</p><ul><li>[!UICONTROL **Nenhum rótulo**]: nenhum rótulo é mostrado nas setas da jornada. </br> Essa opção só estará disponível se a jornada tiver sido modificada no </li><li>[!UICONTROL **Somente rótulos**]: os rótulos são mostrados nas setas da jornada.</li></ul><p>As seguintes opções estão disponíveis para o Journey Optimizer jornada que foram significativamente modificadas na tela do Jornada: (Modificações significativas incluem adicionar ou remover nós, adicionar ou remover setas ou alterar os componentes de um nó.)(**Observação**: essas opções são exibidas somente quando os dados do Journey Optimizer são detectados na mesma visualização de dados selecionada no painel do Analysis Workspace em que você está adicionando a visualização. Para obter informações sobre como alterar a visualização de dados em um painel do Analysis Workspace, consulte [Visão geral do Analysis Workspace](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Nenhum rótulo ou valor**]: nenhum rótulo ou valor é mostrado nas setas da jornada.</li><li>[!UICONTROL **Somente rótulos**]: somente rótulos são exibidos nas setas da jornada. Os valores não são exibidos.</li><li>[!UICONTROL **Somente valores**]: somente valores são mostrados nas setas da jornada. Rótulos não são exibidos.</li><li>[!UICONTROL **Valores e rótulos**]: rótulos e valores são mostrados nas setas da jornada.</li></ul> |
   | [!UICONTROL **Mostrar fallout**] | Os dados de fallout mostram o percentual e o número de usuários que saem em cada etapa da jornada. Os dados de fallout se baseiam na métrica associada às configurações do container da jornada; não se baseiam na métrica principal ou secundária. <p>![fallout](assets/journey-canvas-fallout.png)</p><p>Por padrão, o container é _Pessoa_, portanto, a métrica usada para os dados de fallout é _Pessoas_. Se o container for alterado para _Sessão_, a métrica usada para os dados de fallout será _Sessões_, e assim por diante.</p><p>Por exemplo, com _Pessoa_ como a configuração do container, o fallout mostra o percentual e o número de pessoas em cada nó da jornada que nunca chegaram a nenhum dos próximos nós imediatos. Ela pode ter executado outras ações no site, mas não atendeu aos critérios definidos por nenhum dos nós que se seguem imediatamente.</p> <p>Para obter mais informações sobre a configuração do container da Tela de jornada, consulte [Começar a criar uma visualização da Tela de jornada](#begin-building-a-journey-canvas-visualization). |
   | **Controles de zoom** | Os seguintes controles de zoom estão disponíveis no canto superior direito da tela:<ul><li>**Aumentar zoom** ![ícone aumentar zoom](assets/zoom-in-icon.png): amplia áreas específicas da visualização.<p>Também é possível usar os controles do mouse, como o pinçamento em um trackpad.</li><li>**Reduzir zoom** ![ícone reduzir zoom](assets/zoom-out-icon.png): reduz a visualização para permitir mais espaço na tela.<p>Também é possível usar os controles do mouse, como o pinçamento em um trackpad.</p></li><li>**Ajustar tela** ![ícone ajustar tela](assets/fill-screen-icon.png): ajusta as configurações atuais de zoom e panorâmica para preencher a tela com a visualização completa.</li></ul><p>Para percorrer a tela após aumentar ou diminuir o zoom, clique com o mouse e arraste até o local desejado.</p> |

1. Continuar com [Adicionar nós](#add-nodes).

## Adicionar nós

Os nós em uma visualização de Tela de jornada representam os eventos ou as ações de uma jornada do usuário.

Você cria nós das seguintes maneiras: arrastando componentes do Espaço de trabalho do painel esquerdo para a tela; permitindo que a Tela de jornada escolha os nós principais anteriores ou seguintes com base em nós existentes; ou duplicando nós existentes.

### Arrastar componentes do painel esquerdo

1. No Analysis Workspace, abra uma visualização existente de Tela de jornada ou [comece a criar uma nova](#begin-building-a-journey-canvas-visualization).

1. Arraste métricas, dimensões, itens de dimensão, segmentos ou intervalos de datas do painel esquerdo para a tela. Métricas baseadas em um [campo derivado](/help/data-views/derived-fields/derived-fields.md) são compatíveis. No entanto, métricas calculadas, bem como qualquer métrica ou dimensão que seja baseada em um [conjunto de dados de resumo](/help/data-views/summary-data.md), não são compatíveis.

   Você pode selecionar vários componentes no painel esquerdo mantendo pressionada a tecla Shift, ou mantendo pressionada a tecla Command (no Mac) ou Ctrl (no Windows).

   A visualização é atualizada com base na métrica principal, da seguinte maneira (dependendo do tipo de componente e da área da tela onde você o coloca):

   | Tipo de componente | Posicionamento de componente | Atualizações de visualização após a adição do nó |
   |---------|----------|----------|
   | Métrica | Área em branco da tela | O nó exibe onde o componente foi solto, desconectado de todos os nós existentes. |
   | Métrica | Um nó existente | O componente é combinado automaticamente com o nó existente. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.) |
   | Métrica | Uma seta entre 2 nós existentes | O nó é exibido entre os dois nós existentes onde o componente foi solto e está conectado a ambos os nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.) |
   | Dimensão | Área em branco da tela | Três nós são criados para os três principais itens de dimensão em que o componente foi solto, desconectados de qualquer nó existente. (**Observação:** se apenas um ou dois nós forem exibidos, significa que os dados estão disponíveis apenas para um ou dois dos itens de dimensão. Se nenhum nó for exibido, significa que os dados não estão disponíveis para nenhum dos itens de dimensão. Nesse caso, tente adicioná-lo a um ponto diferente da jornada, ajustar o intervalo de datas da visualização ou escolher uma dimensão diferente.)<p>Mantenha pressionada a tecla Shift ao soltar a dimensão na tela para adicioná-la como um único nó com 3 itens de dimensão.</p> |
   | Dimensão | Um nó existente | Um detalhamento é aplicado automaticamente ao nó com os 5 itens de dimensão principais exibidos.<!--what happens if you hold Shift?--><p>Para exibir o detalhamento em uma nova visualização de tabela de forma livre, clique no link [!UICONTROL **Abrir em uma tabela de forma livre**] no nó.</p> |
   | Dimensão | Uma seta que conecta 2 nós existentes | Três nós são criados para os três principais itens de dimensão que seguem o primeiro evento após o primeiro nó (de pessoas/sessões que acabaram chegando ao segundo nó). Os nós são exibidos entre os dois nós existentes onde o componente foi solto e cada nó está conectado aos dois nós existentes. (**Observação:** se apenas um ou dois nós forem exibidos, significa que os dados estão disponíveis apenas para um ou dois dos itens de dimensão. Se nenhum nó for exibido, significa que os dados não estão disponíveis para nenhum dos itens de dimensão. Nesse caso, tente adicioná-lo a um ponto diferente da jornada, ajustar o intervalo de datas da visualização ou escolher uma dimensão diferente.)<p>Mantenha pressionada a tecla Shift ao soltar a dimensão na tela para adicioná-la como um único nó com 3 itens de dimensão. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.)</p> |
   | Item de dimensão | Área em branco da tela | O nó exibe onde o componente foi solto, desconectado de todos os nós existentes. |
   | Item de dimensão | Um nó existente | O componente é combinado automaticamente com o nó existente. |
   | Item de dimensão | Uma seta que conecta 2 nós existentes | O nó é exibido entre os dois nós existentes onde o componente foi solto e está conectado a ambos os nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.) |
   | Segmento | Área em branco da tela | O nó é exibido onde o componente foi solto sem conexão com outros nós.<p>O número e o percentual exibidos no nó incluem o total da métrica principal, segmentado pelo segmento selecionado.</p> <p>Por exemplo, se a opção Pessoas estiver selecionada como a métrica principal da jornada, adicionar um segmento de Hoje a uma área em branco da tela mostrará todas as pessoas que tiveram um evento hoje.</p> |
   | Segmento | Um nó existente | Aplica o segmento ao nó existente. |
   | Segmento | Uma seta que conecta dois nós | O nó é exibido entre os dois nós existentes onde o componente foi solto e está conectado a ambos os nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.)<p>Aplica o segmento ao ponto no caminho em que o componente foi solto.</p> |
   | Intervalo de datas | Área em branco da tela | O nó exibe onde o componente foi solto, desconectado de quaisquer outros nós.<p>O número e o percentual exibidos no nó incluem o total da métrica principal, segmentado pelo intervalo de datas selecionado.</p> <p>Por exemplo, se a opção Pessoas estiver selecionada como a métrica principal da jornada, adicionar um intervalo de datas Este mês a uma área em branco da tela mostrará todas as pessoas que tiveram um evento durante o mês atual.</p> |
   | Intervalo de datas | Um nó existente | Aplica o intervalo de datas ao nó existente. |
   | Intervalo de datas | Uma seta que conecta dois nós | O nó é exibido entre os dois nós existentes onde o componente foi solto e está conectado a ambos os nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.)<p>Aplica o intervalo de datas ao ponto no caminho em que o componente foi solto.</p> |
   | Vários componentes | Uma área em branco da tela | **Se nenhum dos componentes for uma dimensão:**<p>Cada componente é exibido como um nó separado onde os componentes foram soltos, desconectado de qualquer nó existente.</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. </p><p>**Se algum dos componentes que você está adicionando for uma dimensão:**</p><p>Cada componente é exibido como um nó separado onde os componentes foram soltos, desconectado de qualquer nó existente.</p><p>Apenas uma dimensão pode ser adicionada por vez. Quando a dimensão é adicionada, três nós são criados para os três principais itens de dimensão nos quais o componente foi solto.</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. Os três principais itens de dimensão são combinados com cada nó. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p> |
   | Vários componentes | Um nó existente | Todos os componentes são combinados com o nó existente.<p>Se algum dos componentes que você está adicionando for uma dimensão, os 3 principais itens de dimensão serão combinados com o nó.</p> <p>Apenas uma dimensão pode ser adicionada por vez.</p> |
   | Vários componentes | Uma seta que conecta 2 nós existentes | **Se nenhum dos componentes for uma dimensão:**<p>Cada componente é exibido como um nó separado onde os componentes foram soltos, e cada nó está conectado aos dois nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.)<p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. (Os componentes devem ser do mesmo tipo para serem combinados em um único nó.) (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p><p>**Se algum dos componentes que você está adicionando for uma dimensão:**</p><p>Cada componente é exibido como um nó separado onde os componentes foram soltos, e cada nó está conectado aos dois nós existentes.</p><p>Apenas uma dimensão pode ser adicionada por vez. Quando a dimensão é adicionada, três nós são criados para os três principais itens da dimensão que seguem o primeiro evento após o primeiro nó (de pessoas ou sessões que acabaram chegando ao segundo nó). Cada nó está conectado aos dois nós existentes. (Consulte [Conectar nós](#connect-nodes) para obter mais informações.)</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. Os três principais itens de dimensão são combinados com cada nó, e cada nó é conectado aos dois nós existentes. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p> |

   Os nós são exibidos como uma caixa retangular com as seguintes informações:

   * Nome do componente

   * O tipo de componente (como métrica ou dimensão)

   * Estatísticas da métrica principal (total e percentual)

   * Estatísticas da métrica secundária (total e percentual)

   Um nó pulsante ou brilhante indica que os dados estão sendo carregados para esse nó.

1. Repita esse processo para continuar adicionando nós para criar sua jornada.

1. Continue personalizando a jornada conforme descrito nas seções abaixo. Você pode conectar nós, renomear nós, aplicar detalhamentos, criar públicos-alvo, adicionar restrições de tempo e muito mais.

### Mostrar os nós principais com base nos nós existentes

Você pode mostrar automaticamente os principais nós imediatos com base nos nós que já estão na tela. Você pode adicionar os nós principais à Tela de jornada ou visualizá-los em uma tabela de forma livre.

A Tela de jornada usa a métrica principal ao determinar quais nós serão mostrados.

Essa opção está disponível para os seguintes objetos na tela:

* Nós individuais

* A seta entre os nós

#### Mostrar os nós principais após um nó existente

Você pode selecionar um nó e mostrar os itens de dimensão principais que vêm imediatamente após ele na jornada. Você pode adicionar os três principais itens de dimensão à Tela de jornada como nós separados, ou pode visualizar todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse no nó onde deseja mostrar os itens de dimensão principais que vêm depois dele na jornada.

   O nó não pode ter nenhum nó existente saindo dele na jornada.

1. Selecione [!UICONTROL **Mostrar nós principais após este nó**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na Tela de jornada**]: adiciona os 3 nós principais à tela que vem após este nó na jornada. Cada nó está conectado ao nó selecionado como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm após este nó na jornada.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

#### Mostrar os nós principais antes de um nó existente

Você pode selecionar um nó e mostrar os itens de dimensão principais que vêm imediatamente antes dele na jornada. Você pode adicionar os três principais itens de dimensão à Tela de jornada como nós separados, ou pode visualizar todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse no nó onde deseja mostrar os itens de dimensão principais que vêm antes dele na jornada.

   Este nó não pode ter nós existentes entrando nele na jornada.

1. Selecione [!UICONTROL **Mostrar nós principais antes deste nó**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na Tela de jornada**]: adiciona os 3 nós principais à tela que vem antes deste nó na jornada. Cada nó está conectado ao nó selecionado como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm antes deste nó na jornada.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

#### Mostrar os nós principais entre os nós existentes

Você pode selecionar uma seta e mostrar os itens de dimensão principais que ficam entre dois nós existentes na jornada. Você pode adicionar os três principais itens de dimensão à Tela de jornada como nós separados, ou pode visualizar todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse na seta entre os dois nós em que deseja mostrar os itens de dimensão principais.

1. Selecione [!UICONTROL **Mostrar nós principais entre estes nós**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na Tela de jornada**]: adiciona os 3 nós principais à tela que fica entre os 2 nós existentes. Cada nó é conectado aos nós adjacentes como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm entre os 2 nós existentes.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

### Nós duplicados

A opção de duplicação está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

Para duplicar nós:

1. Selecione um ou mais nós que deseja duplicar.

   Para selecionar vários nós, mantenha pressionada a tecla Command (no Mac) ou Ctrl (no Windows).

1. Clique com o botão direito em um dos nós selecionados e selecione [!UICONTROL **Duplicar**].

## Criar a jornada

A ordem dos nós e as conexões entre eles afetam os dados da Tela de jornada. As jornadas devem refletir de forma visual e precisa a sequência de eventos sobre a qual você deseja criar relatórios.

Depois que os nós forem adicionados à tela, você poderá reorganizá-los, combiná-los, conectá-los e adicionar restrições de tempo entre eles.

### Reorganizar nós

As jornadas na Tela de jornada consistem em um gráfico flexível de nós e setas que representam qualquer combinação de eventos, itens de dimensão e segmentos.

Você pode arrastar os nós na tela para reorganizar os eventos e as condições da jornada.

À medida que você reorganiza a ordem dos nós na jornada, os dados são atualizados de acordo.

### Combinar nós

Um nó combinado na Tela de jornada é um ponto único na jornada do usuário (nó) que contém 2 ou mais componentes unidos por meio da lógica.

#### Criar nós combinados

Você pode executar qualquer um dos seguintes procedimentos para combinar nós na Tela de jornada:

* No painel à esquerda, arraste um único componente para um nó na tela.

* No painel à esquerda, arraste vários componentes simultaneamente para um nó na tela.

* No painel esquerdo, arraste vários componentes simultaneamente para uma área em branco da tela enquanto mantém pressionada a tecla Shift.

<!-- * On the canvas, select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**. Is there a limit on how many you can combine? -->

#### Lógica ao combinar nós

A lógica aplicada aos nós quando combinados varia de acordo com os tipos de componentes que estão sendo combinados, conforme descrito a seguir:

>[!TIP]
>
>Você pode visualizar a lógica de um nó combinado clicando com o botão direito do mouse no nó e selecionando [!UICONTROL **Criar segmento a partir do nó**]. A lógica é mostrada na seção [!UICONTROL **Definição**].


| Tipos de componentes a serem combinados | Lógica (operador) usada |
|---------|----------|
| Métrica + Métrica | Unido com OR |
| Item de dimensão + Item de dimensão (da mesma dimensão principal) | Unido com OR |
| Item de dimensão + Item de dimensão (de dimensões principais diferentes) | Unido com AND |
| Segmento + Segmento | Unido com AND |
| Dimension + Métrica, Intervalo de datas ou Segmento | Unido com AND |
| Intervalo de datas + Métrica, Segmento ou Dimensão | Unido com AND |
| Segmento + Métrica, Intervalo de datas ou Dimensão | Unido com AND |

### Conectar nós

Você pode conectar nós que já estão na tela ou pode conectar um nó ao adicioná-lo à tela.

Você pode conectar nós para definir a sequência de eventos da jornada.

#### Setas entre nós

Os nós são conectados por uma seta. A direção e a largura da seta têm significado:

* **Direção**: indica a sequência de eventos da jornada

* **Largura**: indica o volume percentual de um nó para outro

  ![Direção e largura da seta](assets/journey-canvas-arrow-width.png)

#### Lógica ao conectar nós

Ao conectar nós na tela de jornada, eles são conectados por meio do operador “THEN”. Isso também é conhecido como [segmentação sequencial](/help/components/segments/seg-sequential-build.md).

Os nós são conectados como um “caminho eventual”, ou seja, os visitantes são contados desde que eventualmente se movam de um nó para outro, independentemente de qualquer evento que ocorra entre os dois nós. O tempo alocado para que os usuários se movam pelo caminho é determinado pela configuração do container. <!-- It can also be controlled by [adding a time constraint](#add-a-time-constraint-between-nodes). -->

Para visualizar a lógica dos nós conectados, clique com o botão direito do mouse no nó e selecione [!UICONTROL **Criar segmento a partir do nó**]. A lógica é mostrada na seção [!UICONTROL **Definição**].

#### Conectar nós existentes

As jornadas não podem ser circulares, em circuitos que retornam a nós conectados anteriormente.

Para conectar nós na tela de jornada:

1. Em uma visualização da tela “Jornada”, passe o mouse sobre o nó que aparece primeiro na sequência de jornadas que você deseja conectar a outro nó.

   Quatro pontos azuis são exibidos em cada lado do nó selecionado.

1. Arraste qualquer um dos quatro pontos azuis para qualquer um dos quatro lados do nó ao qual você deseja se conectar.

   Uma seta é exibida, conectando os dois nós. Consulte [Setas entre nós](#arrows-between-nodes) para obter mais informações.

#### Conectar nós ao adicionar um nó

Quando você adicionar um nó à tela, pode colocá-lo entre dois nós conectados. O nó é adicionado ao fluxo da jornada entre os dois nós existentes.

Para obter mais informações, consulte [Adicionar nós](#add-nodes).

<!--

### Add a time constraint between nodes

>[!AVAILABILITY]
>
>This feature is not yet available.

You can set a time constraint between nodes. When a time constraint is in place, people are considered to have fallen out of the journey if they follow the defined journey but take longer than the allotted time period to move between the nodes.

The option to add a time constraint is available for the following objects on the canvas:

* The arrow between nodes

To add a time constraint:

1. In a Journey canvas visualization, right-click the arrow between 2 nodes, then select [!UICONTROL **Add time constraint**].

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Gerenciar nós ou setas

<!--

### Change the color of a node or arrow

>[!AVAILABILITY]
>
>This feature is not yet available.

You can visually customize a journey by changing the color of any node or arrow on the canvas. For example, you could adjust colors to indicate a desirable or undesirable event.

The option to change the color is available for the following objects on the canvas:

* Individual nodes

* The arrow between nodes

To change the color of a node or arrow:

1. In a Journey canvas visualization, right-click the node or arrow whose color you want to change.

1. Select [!UICONTROL **Change color**]. 

1. Select the desired color. 

   The following colors are available: 

-->

### Renomear um nó

Quando você arrasta um componente para uma visualização da tela de jornada, isso cria um nó com o mesmo nome do componente. Você pode renomear o nó para corresponder melhor à etapa da jornada que o nó representa.

A opção de renomear está disponível para os seguintes objetos na tela:

* Nós individuais

Para renomear um nó:

1. Em uma visualização da tela “Jornada”, clique com o botão direito do mouse no nó que deseja renomear.

1. Selecione [!UICONTROL **Renomear**].

1. Especifique um novo nome e pressione Enter.<!--is that right?-->

### Adicionar ou atualizar um rótulo em uma seta

As setas que aparecem entre os nós na Tela de jornada podem ser configuradas para mostrar rótulos e valores personalizados.

Rótulos são nomes personalizados que aparecem nas setas. Somente um único rótulo é exibido em uma determinada seta.

Para obter mais informações sobre os rótulos e valores que aparecem nas setas, consulte “Configurações de seta” em [Definir configurações de visualização](#configure-visualization-settings).

A opção para adicionar ou atualizar um rótulo está disponível para os seguintes objetos na tela:

* A seta entre os nós

Para adicionar um rótulo a uma seta:

1. Em uma visualização da Tela de jornada, clique com o botão direito do mouse na seta à qual deseja adicionar um rótulo.

1. Selecione **[!UICONTROL Adicionar rótulo]**.

1. Especifique um nome para o rótulo e pressione Enter.

   Se as configurações de seta estiverem definidas para ocultar rótulos, uma mensagem será exibida solicitando que você exiba os rótulos.

Para atualizar um rótulo existente em uma seta:

1. Em uma visualização da Tela de jornada, clique com o botão direito do mouse na seta à qual deseja adicionar um rótulo.

1. Selecione **[!UICONTROL Atualizar rótulo]**.

1. Especifique um nome para o rótulo e pressione Enter.

   Se as configurações de seta estiverem definidas para ocultar rótulos, uma mensagem será exibida solicitando que você exiba os rótulos.

### Aplicar um detalhamento

A opção para aplicar um detalhamento aos dados está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* A seta entre os nós

* Várias setas entre nós

* Dados de fallout (quando o fallout é mostrado em um nó)

Considere o seguinte ao aplicar um detalhamento:

* Os detalhamentos são aplicados à métrica principal. A métrica secundária não é afetada.

* Aplicar um detalhamento não altera a jornada. Em vez disso, ele simplesmente mostra um detalhamento dos dados do nó em que é aplicado.

* Se um nó já tiver um detalhamento, a aplicação de um novo detalhamento substituirá o existente.

* Os dados de detalhamento são atualizados se as alterações forem feitas em um ponto anterior da jornada.

#### Aplicar um detalhamento a nós, setas ou dados de fallout

1. Em uma visualização da tela de Jornada, siga um destes procedimentos:

   * Clique com o botão direito do mouse no fallout que está saindo de um nó (quando o fallout for exibido) ao qual você deseja aplicar um detalhamento.

   * Selecione um ou mais nós aos quais deseja aplicar um detalhamento e clique com o botão direito do mouse em um dos nós selecionados.

   * Selecione uma ou mais setas entre 2 nós aos quais deseja aplicar um detalhamento e clique com o botão direito do mouse em uma das setas selecionadas.

     Para selecionar vários nós ou setas, mantenha pressionada a tecla Command (no Mac) ou Ctrl (no Windows).

1. Selecione [!UICONTROL **Detalhamento**].

1. Selecione onde deseja exibir o detalhamento:

   * [!UICONTROL **Na Tela de jornada**]

   * [!UICONTROL **Em uma tabela de forma livre**]

1. Selecione a dimensão que deseja usar para o detalhamento.

   Se você optar por exibir o detalhamento na Tela de jornada, os 5 principais itens de dimensão serão mostrados no nó. Uma opção está disponível no nó para abrir o detalhamento em uma tabela de forma livre.

   Se você optar por exibir o detalhamento em uma tabela de forma livre, os itens de dimensão principais serão mostrados em uma nova tabela de forma livre imediatamente acima da visualização da Tela de jornada.

#### Aplicar um detalhamento a um nó individual

Você pode arrastar uma dimensão do painel esquerdo para o nó na tela em que deseja aplicar o detalhamento.

Para obter mais informações, consulte [Adicionar nós](#add-nodes).

#### Remover um detalhamento

Para remover um detalhamento que foi aplicado:

1. Clique com o botão direito do mouse no nó com o detalhamento aplicado.

1. Selecione **[!UICONTROL Remover detalhamento]**.

### Criar um público-alvo

A opção para criar um público-alvo está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* A seta entre os nós

* Várias setas entre nós

* Dados de fallout (quando o fallout é mostrado em um nó)

Ao criar um público-alvo a partir de vários nós ou setas, eles são unidos com o operador OR.

Para criar um público-alvo:

1. Em uma visualização da tela de Jornada, siga um destes procedimentos:

   * Clique com o botão direito do mouse no fallout que está saindo de um nó (quando o fallout é exibido) para o qual você deseja criar um público-alvo.

   * Selecione um ou mais nós para os quais deseja criar um público-alvo e clique com o botão direito do mouse em um dos nós selecionados.

   * Selecione uma ou mais setas entre 2 nós para os quais deseja criar um público-alvo e clique com o botão direito do mouse em uma das setas selecionadas.

     Para selecionar vários nós ou setas, mantenha pressionada a tecla Command (no Mac) ou Ctrl (no Windows).

   >[!NOTE]
   >
   >Os públicos-alvo não podem incluir métricas calculadas nem outras métricas baseada em um [conjunto de dados de resumo](/help/data-views/summary-data.md). Se você tentar criar um público-alvo a partir de qualquer área da tela “Jornada” que contenha uma métrica calculada ou uma métrica baseada em um conjunto de dados de resumo, a métrica calculada não será incluída na definição do público-alvo.

1. Selecione [!UICONTROL **Criar público-alvo a partir de um nó**] ou [!UICONTROL **Criar público-alvo a partir de uma seta**].

1. Continue criando e publicando o público-alvo conforme descrito em [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).

### Visualizar dados de tendência

Você pode visualizar os dados de tendência em um gráfico de linhas referente a objetos na tela “Jornada”. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

A opção de tendência está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* As setas entre nós

* Várias setas entre nós

* Dados de fallout (quando o fallout é mostrado em um nó)

Para visualizar os dados de tendência:

1. Em uma visualização da tela de Jornada, siga um destes procedimentos:

   * Clique com o botão direito do mouse no fallout que está saindo de um nó (quando o fallout for exibido) para o qual você deseja exibir dados de tendência.

   * Selecione um ou mais nós para os quais deseja exibir dados de tendência e clique com o botão direito do mouse em um dos nós selecionados.

   * Selecione uma ou mais setas entre dois nós para os quais deseja exibir dados de tendência e clique com o botão direito do mouse em uma das setas selecionadas.

     Para selecionar vários nós ou setas, mantenha pressionada a tecla Command (no Mac) ou Ctrl (no Windows).

1. Selecione [!UICONTROL **Tendência**].

### Criar um segmento com base em um nó, seta ou dados de fallout

A opção para criar um segmento está disponível para os seguintes objetos na tela:

* Nós individuais

* As setas entre nós

* Dados de fallout (quando o fallout é mostrado em um nó)

Depois de criar o segmento, você pode usá-lo em qualquer lugar do Analysis Workspace.

Segmentos criados a partir da tela “Jornada” usam a [segmentação sequencial](/help/components/segments/seg-sequential-build.md). Isso significa que o segmento usa o operador “THEN” para vincular a sequência de eventos (a jornada) pela qual as pessoas fluíram, levando até o nó ou a seta selecionada. Todos os eventos que correspondem ao nó ou à seta selecionada são incluídos no segmento.

Se você criar um segmento com base em um nó para o qual haja vários caminhos fluindo, todos os caminhos serão incluídos no segmento. Caminhos separados são unidos com o operador “OR”.

Para criar um segmento:

1. Em uma visualização da tela de Jornada, clique com o botão direito do mouse no nó, na seta ou nos dados de fallout que deseja usar para criar o segmento.

1. Selecione [!UICONTROL **Criar segmento do nó**], [!UICONTROL **Criar segmento a partir da seta**] ou [!UICONTROL **Criar segmento a partir do fallout**].

   O construtor de segmentos é exibido. Na seção [!UICONTROL **Definição**], a definição de segmento é criada com base no nó, seta ou fallout selecionado e seu contexto na jornada.

1. Especifique um título para o segmento e faça quaisquer outras alterações desejadas. Para obter mais informações sobre como criar um segmento, consulte [Construtor de segmentos](/help/components/segments/seg-builder.md).

1. Clique em [!UICONTROL **Salvar**] para salvar o segmento.

### Excluir nós

É possível excluir um ou mais nós por vez em uma jornada. Ao excluir um nó conectado entre dois nós na jornada, os dois nós restantes ficam conectados diretamente.

Para excluir nós na tela “Jornada”:

1. Em uma visualização da tela “Jornada”, selecione um ou mais nós que deseja excluir, e clique com o botão direito do mouse em um dos nós selecionados.

1. Clique em [!UICONTROL **Excluir**].

### Excluir nós

Quando você exclui um nó de uma jornada, os dados da jornada são atualizados para excluir jornadas que passaram por esse nó. A definição de segmento para a jornada também é atualizada para excluir jornadas que passaram por esse nó.

Para excluir um nó de uma jornada:

1. Em uma visualização da tela de Jornada, clique com o botão direito do mouse no nó que deseja excluir.

1. Selecione [!UICONTROL **Excluir da jornada**].

Para incluir novamente um nó excluído na jornada:

1. Em uma visualização da tela de Jornada, clique com o botão direito do mouse no nó excluído.

1. Selecione [!UICONTROL **Remover exclusão de jornada**].

### Excluir setas entre nós

É possível excluir uma ou mais setas por vez em uma jornada. Ao excluir uma seta entre dois nós, os nós não estarão mais conectados. Se a seta fizer parte de um caminho mais longo, o caminho será desconectado.

Para excluir setas entre nós na Tela de jornada:

1. Em uma visualização Tela de jornada, selecione uma ou mais setas entre 2 nós que deseja excluir e clique com o botão direito do mouse em uma das setas selecionadas.

1. Clique em [!UICONTROL **Excluir**].

## Abrir uma jornada no Journey Optimizer

Ao visualizar uma jornada no Journey Optimizer, você pode optar por visualizá-la na Tela de jornada.

1. No Journey Optimizer, abra a jornada que deseja analisar na Tela de jornada.

1. Selecione [!UICONTROL **Analisar no CJA**]. <!-- ?? -->
