---
description: Configurar a visualização de uma tela da jornada
title: Tela da jornada
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: 90180e1231ab8b50f1f6b8552e00d1c251d10a2f
workflow-type: tm+mt
source-wordcount: '5408'
ht-degree: 1%

---

# Configurar a visualização de uma tela da jornada

{{release-limited-testing}}

A visualização da tela de Jornada permite analisar e obter insights profundos sobre as jornadas fornecidas aos usuários e clientes.

## Visão geral da tela da jornada

Consulte [visão geral da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) para saber mais sobre a tela de Jornada, incluindo:

* Recursos principais

* Possíveis insights

* Diferenças entre a tela do Jornada e o fallout

* Detalhes sobre a análise de jornadas do Journey Optimizer

* E muito mais

## Começar a criar uma visualização da tela de Jornada

1. Adicione um painel em branco ao projeto, selecione o ícone [!UICONTROL **Visualizações**] no painel à esquerda e arraste a visualização [!UICONTROL **tela de Jornada**] para o painel.

   Ou

   Adicione uma visualização da tela de Jornada de qualquer uma das maneiras descritas na seção [Adicionar visualizações a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) em [Visão geral das visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Especifique as seguintes informações básicas:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Métrica primária**] | A métrica primária afeta os seguintes aspectos da visualização da tela de Jornada:  <ul><li>Define como as pessoas se movem pela jornada.</li><li>O número total exibido em cada nó.<p>Por exemplo, se a métrica principal for Pessoas, cada nó mostrará o número de pessoas que acessaram esse nó na jornada.</p></li><li>A porcentagem mostrada em cada nó. (Depois que a visualização é criada, você pode optar por mostrar a porcentagem do total ou do nó inicial.)</li><p>Por exemplo, se a métrica principal for Pessoas, cada nó mostrará a porcentagem de pessoas que atingiram esse nó na jornada (a porcentagem do total ou do nó inicial).</p></li><li>Quando uma dimensão é adicionada à visualização, os três principais nós da visualização são adicionados, com base na métrica primária.</li></ul> |
   | [!UICONTROL **Métrica secundária**] | A métrica secundária é opcional. Quando um é selecionado, as seguintes informações são mostradas em cada nó abaixo da métrica primária: <ul><li>O número total<p>Por exemplo, se Sessões for a métrica secundária, cada nó mostrará o número de sessões que atingiram esse nó na jornada.</p></li><li>A porcentagem (após a visualização ser criada, é possível optar por mostrar a porcentagem do total ou do nó inicial).</li><p>Por exemplo, se Sessões for a métrica secundária, cada nó mostrará a porcentagem de sessões que atingiram esse nó na jornada (a porcentagem do total ou do nó inicial).</p></li></ul> |
   | [!UICONTROL **jornada DO Journey Optimizer**]<!-- name? --> | Selecione a jornada do Journey Optimizer que deseja usar como base para sua análise na tela de Jornada. (Como alternativa, você pode deixar essa opção em branco se quiser uma tela em branco da qual criar sua análise no Analysis Workspace.)</p> <p>Ao analisar uma jornada do Journey Optimizer na tela do Jornada, a jornada é exibida com a mesma ordem, sequência e estrutura que tem no Journey Optimizer. Para obter mais informações, consulte [Analisar jornadas do Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) em [visão geral da tela do Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Observação**: essa opção é exibida somente quando dados do Journey Optimizer são detectados na mesma visualização de dados selecionada no painel do Analysis Workspace ao qual você está adicionando a visualização. Para obter informações sobre como alterar a visualização de dados em um painel no Analysis Workspace, consulte [visão geral do Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Opcional) Selecione [!UICONTROL **Mostrar configurações avançadas**] e especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **contêiner da tela de Jornada**] | Escolha o contêiner no qual deseja se concentrar na jornada. O contêiner escolhido determina as estatísticas exibidas na visualização. (Se os nomes dos containers forem diferentes dos nomes padrão mostrados abaixo, eles serão personalizados na visualização de dados.)<ul><li>**Sessões:** Restringe as estatísticas da visualização a se enquadrarem em uma única sessão definida para uma determinada pessoa. Isso significa que os números e as porcentagens exibidos em cada nó (que são baseados nas métricas principal e secundária) devem ocorrer em uma única sessão para cada pessoa.</li><li>**Pessoas:** permite que as estatísticas da visualização abranjam várias sessões de uma determinada pessoa. Isso significa que os números e porcentagens exibidos em cada nó (que são baseados nas métricas primária e secundária) podem ocorrer em qualquer número de sessões, desde que as sessões pertençam à mesma pessoa. Esta é a configuração padrão.</li></ul> |

1. Selecione [!UICONTROL **Criar**].

   Se você tiver o Journey Optimizer e tiver selecionado uma jornada do Journey Optimizer, a jornada será exibida com a mesma ordem, sequência e estrutura que teve no Journey Optimizer.

   <!-- add screen shot -->

   Se você não tiver o Journey Optimizer ou se não tiver selecionado uma jornada do Journey Optimizer, uma tela em branco será exibida, onde você poderá começar a preencher a jornada.

   <!-- add screen shot -->

1. Se você estiver criando uma nova análise a partir de uma tela em branco ou analisando uma jornada do Journey Optimizer, poderá configurar a jornada conforme descrito em [Definir configurações de visualização](#configure-visualization-settings).


## Definir configurações de visualização

Várias opções de configuração estão disponíveis no cabeçalho da tela de Jornada.

Para definir as configurações da visualização da tela de Jornada:

1. No Analysis Workspace, abra uma visualização existente da tela de Jornada ou [comece a criar uma nova](#begin-building-a-journey-canvas-visualization).

   As opções que permitem configurar a visualização da tela de Jornada estão disponíveis no cabeçalho:

   ![Opções de cabeçalho da tela de Jornada](assets/journey-canvas-header.png)

1. Defina qualquer uma das seguintes configurações exibidas na parte superior da visualização:

   | Configuração | Função |
   |---------|----------|
   | [!UICONTROL **Tipo de nó**] | Permite configurar quais tipos de nó são mostrados na visualização.<p>Para ocultar um tipo de nó da visualização, selecione o (x) ao lado do tipo de nó ou desmarque-o do menu suspenso. Para mostrar um tipo de nó oculto, selecione-o no menu suspenso. (Os nós não são excluídos da jornada quando você os oculta. Para obter informações sobre como excluir um nó, consulte [Excluir nós](#delete-nodes).)</p><p>Este campo pode conter tipos de nó Journey Optimizer ([!UICONTROL **Segmento de leitura**], [!UICONTROL **Fim**] e assim por diante) e tipos de nó de componente ([!UICONTROL **Dimension**], [!UICONTROL **Métrica**], [!UICONTROL **Filtro**] e [!UICONTROL **Intervalo de datas**]), como a seguir: </p><ul><li>**Somente os tipos de nó do Journey Optimizer serão exibidos** se a jornada for uma jornada do Journey Optimizer que não foi modificada na tela do Jornada com qualquer uma das seguintes modificações:<ul><li>Nós adicionados ou removidos</li><li>Setas adicionadas ou removidas</li><li>Alterados os componentes em um nó</li></ul></li><li>**Os tipos de nó do Journey Optimizer e os tipos de nó de componente serão mostrados** se a jornada for uma jornada do Journey Optimizer que foi modificada na tela do Jornada com qualquer uma das seguintes modificações:<ul><li>Nós adicionados ou removidos</li><li>Setas adicionadas ou removidas</li><li>Alterados os componentes em um nó</li></ul></li><li>**Somente tipos de nó de componente serão exibidos** se a jornada não for uma jornada do Journey Optimizer.</li></ul></p> |
   | [!UICONTROL **Valor percentual**] | O valor percentual mostrado em cada nó da jornada. Essa porcentagem inclui apenas as pessoas incluídas na visualização de dados dentro do intervalo de datas do painel. <p>Escolha entre as seguintes opções:</p> <ul><li>[!UICONTROL **Percentual do nó inicial**]: a porcentagem de todas as pessoas que atendem aos critérios de um nó inicial na jornada. <p>Um _nó inicial_ é um nó que não tem nós conectados anteriores a ele.</p><p>Uma jornada pode conter vários nós iniciais. No entanto, [!UICONTROL **Percentual do total**] será usado se a jornada contiver 2 ou mais nós iniciais que levam a um nó comum. Se quiser usar [!UICONTROL **Percentual do nó inicial**], atualize a jornada para que cada nó na jornada possa ser rastreado até um único nó inicial.</p></li><li>[!UICONTROL **Percentual do nó anterior**]: a porcentagem de todas as pessoas do nó anterior.</li><li>[!UICONTROL **Percentual do total**]: a porcentagem de todas as pessoas incluídas na visualização de dados no intervalo de datas do painel.</li></ul> |
   | [!UICONTROL **Configurações de seta**] | As setas que aparecem entre os nós na tela de Jornada podem ser configuradas para mostrar rótulos e valores personalizados. <p>_Rótulos_ são nomes personalizados que aparecem em setas. Somente um único rótulo é exibido em uma determinada seta. Os rótulos podem ser qualquer um dos seguintes e são mostrados nesta ordem de preferência:</p><ol><li>Um nome personalizado foi adicionado da tela de Jornada (conforme descrito em [Renomear um nó ou uma seta](#rename-a-node-or-arrow))</li><li>Um rótulo do Journey Optimizer</li><li>Uma condição do Journey Optimizer</li></ol><p>_Valores_ são os números e porcentagens que aparecem nas setas e indicam as pessoas ou sessões que passaram de um nó para outro na jornada. (Em outras palavras, aqueles que não caíram da jornada em uma determinada etapa.) </p><p>As seguintes opções estão disponíveis para jornadas que não se originaram do Journey Optimizer e para jornadas do Journey Optimizer que não foram modificadas significativamente na tela do Jornada: (Modificações significativas incluem adicionar ou remover nós, adicionar ou remover setas ou alterar os componentes de um nó.)</p><ul><li>[!UICONTROL **Nenhum rótulo**]: nenhum rótulo é mostrado nas setas da jornada. </br> Essa opção só estará disponível se a jornada tiver sido modificada em </li><li>[!UICONTROL **Somente rótulos**]: os rótulos são mostrados nas setas da jornada.</li></ul><p>As seguintes opções estão disponíveis para o Journey Optimizer jornada que foram significativamente modificadas na tela do Jornada: (Modificações significativas incluem adicionar ou remover nós, adicionar ou remover setas ou alterar os componentes de um nó.)(**Observação**: essas opções são exibidas somente quando os dados do Journey Optimizer são detectados na mesma visualização de dados selecionada no painel do Analysis Workspace ao qual você está adicionando a visualização. Para obter informações sobre como alterar a visualização de dados em um painel no Analysis Workspace, consulte [visão geral do Analysis Workspace](/help/analysis-workspace/home.md).)</p><ul><li>[!UICONTROL **Nenhum rótulo ou valor**]: nenhum rótulo ou valor é mostrado nas setas da jornada.</li><li>[!UICONTROL **Somente rótulos**]: somente rótulos são exibidos nas setas da jornada. Os valores não são exibidos.</li><li>[!UICONTROL **Somente valores**]: somente valores são mostrados nas setas da jornada. Os rótulos não são exibidos.</li><li>[!UICONTROL **Valores e rótulos**]: ambos os rótulos e valores são mostrados nas setas da jornada.</li></ul> |
   | [!UICONTROL **Mostrar fallout**] | Exibir dados de fallout de cada nó. Isso mostra o número e a porcentagem de pessoas que deixaram a jornada após um determinado nó. <p>As pessoas que abandonaram a jornada podem ter executado outras ações no site, mas nunca atenderam aos critérios definidos pelo próximo nó na jornada.</p> |
   | **Controles de zoom** | Os seguintes controles de zoom estão disponíveis no canto superior direito da tela:<ul><li>**Ícone de Ampliação** ![Ampliar](assets/zoom-in-icon.png): Amplia áreas específicas da visualização.<p>Também é possível usar os controles do mouse, como o pinçamento em um trackpad.</p></li><li>**Ícone de menos zoom** ![menos zoom](assets/zoom-out-icon.png): reduz a visualização para permitir mais espaço na tela.<p>Também é possível usar os controles do mouse, como o pinçamento em um trackpad.</p></li><li>**Ajustar tela** ![ícone de ajustar tela](assets/fill-screen-icon.png): ajusta as configurações atuais de zoom e panorâmica para preencher a tela com a visualização completa.</li></ul><p>Para deslocar-se pela tela de desenho depois de aumentar ou diminuir o zoom, clique com o mouse e arraste para o local desejado.</p> |

1. Continuar com [Adicionar nós](#add-nodes).

## Adicionar nós

Os nós em uma visualização da tela de Jornada representam os eventos ou as ações de uma jornada do usuário.

Você cria nós arrastando componentes do Workspace do painel esquerdo para a tela de desenho, permitindo que a tela de Jornada escolha os nós superiores anteriores ou seguintes com base nos nós existentes, ou duplicando nós existentes.

### Arraste os componentes do painel esquerdo

1. No Analysis Workspace, abra uma visualização existente da tela de Jornada ou [comece a criar uma nova](#begin-building-a-journey-canvas-visualization).

1. Arraste métricas, dimensões, itens de dimensão, filtros ou intervalos de datas do painel esquerdo para a tela. Métricas baseadas em um [campo derivado](/help/data-views/derived-fields/derived-fields.md) têm suporte. No entanto, métricas calculadas, bem como qualquer métrica ou dimensão que seja baseada em um [conjunto de dados de resumo](/help/data-views/summary-data.md), não são suportadas.

   Você pode selecionar vários componentes no painel à esquerda, mantendo pressionada a tecla Shift ou a tecla Command (no Mac) ou Ctrl (no Windows).

   A visualização é atualizada da seguinte maneira, dependendo do tipo de componente e da área da tela onde você o coloca:

   | Tipo de componente | Posicionamento do componente | Atualizações de visualização após a adição do nó |
   |---------|----------|----------|
   | Métrica | Área em branco da tela de desenho | O nó exibe onde o componente foi solto, desconectado de todos os nós existentes. |
   | Métrica | Um nó existente | O componente é combinado automaticamente com o nó existente. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p> |
   | Métrica | Uma seta entre 2 nós existentes | O nó é exibido entre os dois nós existentes onde o componente foi descartado e está conectado a ambos os nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p> |
   | Dimensão | Área em branco da tela de desenho | Três nós são criados para os três principais itens de dimensão em que o componente foi descartado, desconectados de qualquer nó existente. (**Observação:** se apenas um ou dois nós forem exibidos, significa que os dados estão disponíveis apenas para um ou dois dos itens de dimensão. Se nenhum nó for exibido, significa que os dados não estão disponíveis para nenhum dos itens de dimensão. Nesse caso, tente adicioná-lo a um ponto diferente da jornada, ajustar o intervalo de datas da visualização ou escolher uma dimensão diferente.)<p>Mantenha pressionada a tecla Shift ao soltar a dimensão na tela para adicioná-la como um único nó com 3 itens de dimensão.</p><p></p> |
   | Dimensão | Um nó existente | Um detalhamento é aplicado automaticamente ao nó com os 5 itens de dimensão principais exibidos.<!--what happens if you hold Shift?--><p>Para exibir o detalhamento em uma nova visualização de tabela de forma livre, selecione o link [!UICONTROL **Abrir em uma tabela de forma livre**] no nó.</p> |
   | Dimensão | Uma seta que conecta dois nós existentes | Três nós são criados para os três principais itens de dimensão que seguem o primeiro evento após o primeiro nó (de pessoas/sessões que eventualmente chegam ao segundo nó). Os nós são exibidos entre os dois nós existentes onde o componente foi descartado e cada nó está conectado aos dois nós existentes. (**Observação:** se apenas um ou dois nós forem exibidos, significa que os dados estão disponíveis apenas para um ou dois dos itens de dimensão. Se nenhum nó for exibido, significa que os dados não estão disponíveis para nenhum dos itens de dimensão. Nesse caso, tente adicioná-lo a um ponto diferente da jornada, ajustar o intervalo de datas da visualização ou escolher uma dimensão diferente.)<p>Mantenha pressionada a tecla Shift ao soltar a dimensão na tela para adicioná-la como um único nó com 3 itens de dimensão. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p> |
   | Item de dimensão | Área em branco da tela de desenho | O nó exibe onde o componente foi solto, desconectado de todos os nós existentes. |
   | Item de dimensão | Um nó existente | O componente é combinado automaticamente com o nó existente. |
   | Item de dimensão | Uma seta que conecta dois nós existentes | O nó é exibido entre os dois nós existentes onde o componente foi descartado e está conectado a ambos os nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p> |
   | Filtro | Área em branco da tela de desenho | O nó é exibido onde o componente foi solto sem conexão com outros nós.<p>O número e a porcentagem exibidos no nó incluem o total da métrica primária, filtrado pelo filtro selecionado.</p> <p>Por exemplo, se a opção Pessoas estiver selecionada como a métrica principal da jornada, adicionar um filtro Hoje a uma área em branco da tela mostrará todas as pessoas que tiveram um evento hoje.</p> |
   | Filtro | Um nó existente | Aplica o filtro ao nó existente. |
   | Filtro | Uma seta que conecta dois nós | O nó é exibido entre os dois nós existentes onde o componente foi descartado e está conectado a ambos os nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p><p>Aplica o filtro ao ponto no caminho em que o componente foi solto.</p> |
   | Intervalo de datas | Área em branco da tela de desenho | O nó exibe onde o componente foi solto, desconectado de quaisquer outros nós.<p>O número e a porcentagem exibidos no nó incluem o total da métrica primária, filtrado pelo intervalo de datas selecionado.</p> <p>Por exemplo, se a opção Pessoas estiver selecionada como a métrica principal da jornada, adicionar um intervalo de datas Este mês a uma área em branco da tela mostrará todas as pessoas que tiveram um evento durante o mês atual.</p> |
   | Intervalo de datas | Um nó existente | Aplica o intervalo de datas ao nó existente. |
   | Intervalo de datas | Uma seta que conecta dois nós | O nó é exibido entre os dois nós existentes onde o componente foi descartado e está conectado a ambos os nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p><p>Aplica o intervalo de datas ao ponto no caminho em que o componente foi solto.</p> |
   | Vários componentes | Uma área em branco da tela de desenho | **Se nenhum dos componentes for uma dimensão:**<p>Cada componente é exibido como um nó separado onde os componentes foram descartados, desconectado de qualquer nó existente.</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. </p><p>**Se algum dos componentes que você está adicionando for uma dimensão:**</p><p>Cada componente é exibido como um nó separado onde os componentes foram descartados, desconectado de qualquer nó existente.</p><p>Somente uma dimensão pode ser adicionada de cada vez. Quando a dimensão é adicionada, três nós são criados para os três principais itens de dimensão nos quais o componente foi descartado.</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. Os três principais itens de dimensão são combinados com cada nó. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p> |
   | Vários componentes | Um nó existente | Todos os componentes são combinados com o nó existente.<p>Se qualquer um dos componentes que você está adicionando for de dimensões, os três principais itens de dimensão serão combinados com o nó.</p> <p>Somente uma dimensão pode ser adicionada de cada vez.</p> |
   | Vários componentes | Uma seta que conecta dois nós existentes | **Se nenhum dos componentes for uma dimensão:**<p>Cada componente é exibido como um nó separado, em que os componentes foram descartados e cada nó está conectado aos dois nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. (Os componentes devem ser do mesmo tipo para serem combinados em um único nó.) (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p><p>**Se algum dos componentes que você está adicionando for uma dimensão:**</p><p>Cada componente é exibido como um nó separado, em que os componentes foram descartados e cada nó está conectado aos dois nós existentes.</p><p>Somente uma dimensão pode ser adicionada de cada vez. Quando a dimensão é adicionada, três nós são criados para os três principais itens da dimensão que seguem o primeiro evento após o primeiro nó (de pessoas/sessões que eventualmente chegam ao segundo nó). Cada nó está conectado aos dois nós existentes. (Consulte [Nós Connect](#connect-nodes) para obter mais informações.)</p><p>Mantenha pressionada a tecla Shift ao soltar os componentes na tela para adicioná-los como um nó combinado. Os três principais itens de dimensão são combinados com cada nó, e cada nó é conectado aos dois nós existentes. (Consulte [Combinar nós](#combine-nodes) para obter mais informações.)</p> |

   Os nós são exibidos como uma caixa retangular com as seguintes informações:

   * Nome do componente

   * O tipo de componente (como métrica ou dimensão)

   * Estatísticas de métrica primária (total e porcentagem)

   * Estatísticas de métrica secundária (total e porcentagem)

1. Repita esse processo para continuar adicionando nós para criar sua jornada.

1. Continue personalizando a jornada conforme descrito nas seções abaixo. Você pode conectar nós, renomear nós, aplicar detalhamentos, criar públicos, adicionar restrições de tempo e muito mais.

### Mostrar os nós principais com base nos nós existentes

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

Você pode mostrar automaticamente os nós principais com base nos nós que já estão na tela. Você pode adicionar os nós principais à tela de Jornada ou visualizá-los em uma tabela de forma livre.

Essa opção está disponível para os seguintes objetos na tela de desenho:

* Nós individuais

* A seta entre os nós

#### Mostrar nós principais após um nó existente

Você pode selecionar um nó e mostrar os itens de dimensão principais que vêm depois dele na jornada. Você pode adicionar os três principais itens de dimensão à tela de Jornada como nós separados, ou pode exibir todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse no nó onde deseja mostrar os itens de dimensão principais que vêm depois dele na jornada.

   O nó não pode ter nenhum nó existente saindo dele na jornada.

1. Selecione [!UICONTROL **Mostrar nós principais após este nó**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na tela de Jornada**]: adiciona os 3 nós principais à tela que vem após este nó na jornada. Cada nó está conectado ao nó selecionado como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm após este nó na jornada.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

#### Mostrar nós principais antes de um nó existente

Você pode selecionar um nó e mostrar os itens de dimensão principais que vêm antes dele na jornada. Você pode adicionar os três principais itens de dimensão à tela de Jornada como nós separados, ou pode exibir todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse no nó onde deseja mostrar os itens de dimensão principais que vêm antes dele na jornada.

   Este nó não pode ter nós existentes entrando nele na jornada.

1. Selecione [!UICONTROL **Mostrar nós principais antes deste nó**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na tela de Jornada**]: adiciona os 3 nós principais à tela que vem antes deste nó na jornada. Cada nó está conectado ao nó selecionado como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm antes deste nó na jornada.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

#### Mostrar nós principais entre nós existentes

Você pode selecionar uma seta e mostrar os itens de dimensão principais que ficam entre dois nós existentes na jornada. Você pode adicionar os três principais itens de dimensão à tela de Jornada como nós separados, ou pode exibir todos os itens de dimensão principais em uma tabela de forma livre.

1. Clique com o botão direito do mouse na seta entre os dois nós em que deseja mostrar os itens de dimensão principais.

1. Selecione [!UICONTROL **Mostrar nós superiores entre estes nós**].

1. Selecione onde deseja mostrar os itens de dimensão:

   * [!UICONTROL **Na tela de Jornada**]: adiciona os 3 nós principais à tela que fica entre os 2 nós existentes. Cada nó é conectado aos nós adjacentes como uma ramificação separada na tela.

   * [!UICONTROL **Em uma tabela de forma livre**]: cria uma visualização de tabela de forma livre mostrando todos os itens de dimensão principais que vêm entre os dois nós existentes.

1. Selecione a dimensão desejada na lista de dimensões.

   Dependendo do que você escolheu na etapa anterior, os três principais itens de dimensão são adicionados à tela como três nós separados, ou todos os itens de dimensão principais são mostrados em uma tabela de forma livre.

### Nós duplicados

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

A opção de duplicação está disponível para os seguintes objetos na tela:

* Vários nós

Para duplicar nós:

1. Selecione vários nós que deseja duplicar.

1. Clique com o botão direito em um dos nós selecionados e selecione [!UICONTROL **Duplicar**].

## Projetar a jornada

A ordem dos nós e as conexões entre eles afetam os dados da tela de Jornada. As jornadas devem refletir de forma visual e precisa a sequência de eventos sobre a qual você deseja criar relatórios.

Depois que os nós forem adicionados à tela, você poderá reorganizá-los, combiná-los, conectá-los e adicionar restrições de tempo entre eles.

### Reorganizar nós

As jornadas na tela de Jornada consistem em um gráfico flexível de nós e setas que representam qualquer combinação de eventos, itens de dimensão e filtros.

Você pode arrastar nós na tela para reorganizar os eventos e as condições da jornada. Você pode selecionar vários nós mantendo a tecla Command (no Mac) ou Ctrl (no Windows) pressionada.

À medida que você reorganiza a ordem dos nós na jornada, os dados são atualizados de acordo.

### Combinar nós

Um nó combinado na tela do Jornada é um único ponto na jornada do usuário (nó) que contém 2 ou mais componentes unidos por meio da lógica.

#### Criar nós combinados

Você pode executar qualquer um dos seguintes procedimentos para criar nós combinados na tela do Jornada:

* No painel à esquerda, arraste um único componente para um nó na tela.

* No painel à esquerda, arraste vários componentes simultaneamente para um nó na tela.

* No painel esquerdo, arraste vários componentes simultaneamente para uma área em branco da tela de desenho enquanto mantém pressionada a tecla Shift.

* Na tela, selecione os nós que deseja combinar, clique com o botão direito do mouse em um dos nós selecionados e selecione **Combinar**.<!--Is there a limit on how many you can combine? -->

#### Lógica ao combinar nós

A lógica aplicada aos nós quando eles são combinados difere, dependendo dos tipos de componentes que você está combinando, da seguinte maneira:

>[!TIP]
>
>Você pode exibir a lógica de um nó combinado clicando com o botão direito do mouse no nó e selecionando [!UICONTROL **Criar filtro a partir do nó**]. A lógica é mostrada na seção [!UICONTROL **Definição**].


| Tipos de componentes a serem combinados | Lógica (operador) usada |
|---------|----------|
| Métrica + Métrica | Unido com OR |
| item Dimension + item Dimension (da mesma dimensão principal) | Unido com OR |
| item Dimension + item Dimension (de diferentes dimensões principais) | Unido com AND |
| Filter + Filter | Unido com AND |
| Dimension + Métrica, Intervalo de datas ou Filtro | Unido com AND |
| Intervalo de datas + Métrica, Filtro ou Dimension | Unido com AND |
| Filtro + Métrica, Intervalo de datas ou Dimension | Unido com AND |

### Conectar nós

Você pode conectar nós que já estão na tela ou pode conectar um nó ao adicioná-lo à tela.

#### Setas entre nós

Os nós são conectados por uma seta. A direção e a largura da seta têm significado:

* **Direção**: indica a sequência de eventos da jornada

* **Largura**: indica o volume percentual de um nó para outro

#### Lógica ao conectar nós

Ao conectar nós na tela do Jornada, eles são conectados por meio do operador THEN. Isso também é conhecido como [filtragem sequencial](/help/components/filters/seg-sequential-build.md).

Os nós são conectados como um &quot;caminho eventual&quot;, o que significa que os visitantes são contados desde que eventualmente se movam de um nó para outro, independentemente de quaisquer eventos que ocorram entre os dois nós.

Você pode exibir a lógica dos nós conectados clicando com o botão direito do mouse no nó e selecionando [!UICONTROL **Criar filtro do nó**]. A lógica é mostrada na seção [!UICONTROL **Definição**].

#### Conectar nós existentes

O Jornada não pode ser circular, fazendo loopback para nós conectados anteriormente.

Para conectar nós na tela do Jornada:

1. Na tela, passe o mouse sobre o nó que vem primeiro na sequência de jornadas que você deseja conectar a outro nó.

   4 pontos azuis são exibidos em cada lado do nó selecionado.

1. Arraste qualquer um dos 4 pontos azuis para qualquer um dos 4 lados do nó ao qual você deseja se conectar.

   Uma seta é exibida, conectando os 2 nós. Consulte [Setas entre nós](#arrows-between-nodes) para obter mais informações.

#### Conectar nós ao adicionar um nó

Ao adicionar um nó à tela, você pode colocá-lo entre dois nós conectados. O nó é adicionado ao fluxo da jornada entre os dois nós existentes.

Para obter mais informações, consulte [Adicionar nós](#add-nodes).

### Adicionar uma restrição de tempo entre nós

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

Você pode definir uma restrição de tempo entre nós. Quando uma restrição de tempo está em vigor, as pessoas são consideradas como tendo saído da jornada se seguirem a jornada definida, mas levarem mais tempo do que o período de tempo alocado para se moverem entre os nós.

A opção para adicionar uma restrição de tempo está disponível para os seguintes objetos na tela de desenho:

* A seta entre os nós

Para adicionar uma restrição de tempo:

1. Clique com o botão direito do mouse na seta entre 2 nós e selecione [!UICONTROL **Adicionar restrição de tempo**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Gerenciar nós ou setas

### Alterar a cor de um nó ou seta

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

É possível personalizar visualmente uma jornada alterando a cor de qualquer nó ou seta na tela de desenho. Por exemplo, você pode ajustar as cores para indicar um evento desejável ou indesejável.

A opção para alterar a cor está disponível para os seguintes objetos na tela de desenho:

* Nós individuais

* A seta entre os nós

Para alterar a cor de um nó ou seta:

1. Clique com o botão direito do mouse no nó ou na seta cuja cor você deseja alterar.

1. Selecione [!UICONTROL **Alterar cor**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Selecione a cor desejada.

   As seguintes cores estão disponíveis: <!--look into this interaction and color list-->

### Renomear um nó ou uma seta

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

Quando você arrasta um componente para uma visualização da tela de Jornada, ele cria um nó com o mesmo nome do componente. Você pode renomear o nó para corresponder melhor à etapa da jornada que o nó representa.

A opção para renomear está disponível para os seguintes objetos na tela:

* Nós individuais

* A seta entre os nós

Para renomear um nó:

1. Clique com o botão direito do mouse no nó que deseja renomear.

1. Selecione [!UICONTROL **Renomear**].

1. Especifique um novo nome e pressione Enter.<!--is that right?-->

### Aplicar um detalhamento

A opção para aplicar um detalhamento aos seus dados está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* A seta entre os nós

* Várias setas entre nós

Considere o seguinte ao aplicar um detalhamento:

* Os detalhamentos são aplicados à métrica principal. A métrica secundária não é afetada.

* Aplicar um detalhamento não altera a jornada. Em vez disso, ele simplesmente mostra um detalhamento dos dados do nó em que é aplicado.

* Se um nó já tiver um detalhamento, a aplicação de um novo detalhamento substituirá o existente.

* Os dados de detalhamento são atualizados se as alterações forem feitas em um ponto anterior da jornada.

#### Aplicar um detalhamento a um ou mais nós ou setas

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

1. Selecione um ou mais nós aos quais deseja aplicar um detalhamento e clique com o botão direito do mouse em um dos nós selecionados.

   Ou

   Selecione uma ou mais setas entre 2 nós nos quais deseja aplicar o detalhamento e clique com o botão direito do mouse em uma das setas selecionadas.

1. Selecione [!UICONTROL **Detalhamento**].

<!-- 1. Choose where you want to view the breakdown:

        * [!UICONTROL **In Journey canvas**]

        * [!UICONTROL **In a freeform table**]

-->

#### Aplicar um detalhamento a um nó individual

Você pode arrastar uma dimensão do painel esquerdo para o nó na tela em que deseja aplicar o detalhamento.

Para obter mais informações, consulte [Adicionar nós](#add-nodes).

### Criar um público-alvo

A opção para criar um público-alvo está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* A seta entre os nós

* Várias setas entre nós

Ao criar um público-alvo a partir de vários nós ou setas, eles são unidos com o operador OU.

Para criar um público-alvo:

1. Selecione um ou mais nós nos quais deseja criar um público-alvo e clique com o botão direito do mouse em um dos nós selecionados.

   Ou

   Selecione uma ou mais setas entre 2 nós onde deseja criar um público-alvo e clique com o botão direito do mouse em uma das setas selecionadas.

1. Selecione [!UICONTROL **Criar audiência**].

<!-- 1. Choose where you want to create the audience:

        * [!UICONTROL **In Journey canvas**]

        * [!UICONTROL **In a freeform table**]

-->

1. Continue criando e publicando o público-alvo conforme descrito em [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).

### Exibir dados de tendência

>[!AVAILABILITY]
>
>Este recurso ainda não está disponível.

Você pode exibir os dados de tendência em um gráfico de linhas para objetos na tela de Jornada. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

A opção de definir tendência está disponível para os seguintes objetos na tela:

* Nós individuais

* Vários nós

* As setas entre nós

* Várias setas entre nós

Para exibir dados de tendência:

1. Selecione um ou mais nós para os quais deseja exibir dados de tendência e clique com o botão direito do mouse em um dos nós selecionados.

   Ou

   Selecione uma ou mais setas entre dois nós para os quais deseja exibir dados de tendência e clique com o botão direito do mouse em uma das setas selecionadas.

1. Selecione [!UICONTROL **Tendência**].

### Criar um filtro com base em um nó ou seta

Você pode criar um novo filtro com base em um nó ou seta em uma jornada. Depois que o filtro é criado, é possível usá-lo em qualquer lugar do Analysis Workspace.

Os filtros criados a partir da tela de Jornada usam [filtragem sequencial](/help/components/filters/seg-sequential-build.md). Isso significa que o filtro usa o operador THEN para vincular a sequência de eventos (a jornada) pela qual as pessoas fluíram, levando até o nó ou a seta selecionada. Todos os eventos que correspondem ao nó ou à seta selecionada são incluídos no filtro.

Se você criar um filtro com base em um nó que tenha vários caminhos fluindo para ele, todos os caminhos serão incluídos no filtro. Caminhos separados são unidos com o operador OR.

Para criar um filtro:

1. Na tela de desenho, clique com o botão direito do mouse no nó ou na seta que deseja usar para criar o filtro.

1. Selecione [!UICONTROL **Criar filtro a partir do nó**] ou [!UICONTROL **Criar filtro a partir da seta**].

   O Construtor de filtros é exibido. Na seção [!UICONTROL **Definição**], a definição de filtro é criada com base no nó ou na seta selecionada e seu contexto dentro da jornada.

1. Especifique um título para o filtro e faça outras alterações. Para obter mais informações sobre como criar um filtro, consulte [Construtor de filtros](/help/components/filters/filter-builder.md).

1. Selecione [!UICONTROL **Salvar**] para salvar o filtro.

### Excluir nós

É possível excluir um ou mais nós de cada vez em uma jornada. Ao excluir um nó conectado entre dois nós na jornada, os dois nós restantes se tornam conectados diretamente.

Para excluir nós na tela de Jornada:

1. Selecione um ou mais nós que deseja excluir e clique com o botão direito do mouse em um dos nós selecionados.

1. Clique em [!UICONTROL **Excluir**].

### Excluir setas entre nós

É possível excluir uma ou mais setas por vez em uma jornada. Quando você exclui uma seta entre dois nós, os nós não estão mais conectados. Se a seta fizer parte de um caminho mais longo, o caminho será desconectado.

Para excluir setas entre nós na tela de Jornada:

1. Selecione uma ou mais setas entre 2 nós que deseja excluir e clique com o botão direito do mouse em uma das setas selecionadas.

1. Clique em [!UICONTROL **Excluir**].


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Abrir uma jornada do Journey Optimizer


No Journey Optimizer, abra a jornada que deseja analisar na tela do Jornada.

1. Selecione [!UICONTROL **Analisar no CJA**]. <!-- ?? -->
