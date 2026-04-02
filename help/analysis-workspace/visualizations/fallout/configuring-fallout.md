---
description: Saiba como configurar e especificar os pontos de contato para criar uma sequência de fallout multidimensional.
title: Configurar Uma Visualização De Fallout
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 295e4c9b3b9dff5ba650456c3f62817b30fe1e3d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 39%

---

# Configurar uma visualização de fallout {#configure-fallout-visualization}


Você pode especificar **pontos de contato** para criar uma sequência de fallout multidimensional. Em muitos casos, um ponto de contato é uma página no site. No entanto, os pontos de contato não estão limitados a páginas. Por exemplo, é possível adicionar eventos, como unidades, bem como usuários únicos e visitas de retorno. Também é possível adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interna.

Você pode até mesmo adicionar segmentos em um ponto de contato. Por exemplo, você pode querer comparar segmentos, como usuários do iOS e do Android. Arraste os segmentos desejados para o topo do fallout e as informações sobre os segmentos serão adicionadas ao relatório de fallout. Se quiser mostrar apenas esses segmentos, você pode remover a linha de base Todas as pessoas.

As visualizações de fallout não têm limitação sobre o número de pontos de contato que podem ser adicionados ou o número de componentes que podem ser usados.

É possível definir o caminho em dimensões, métricas e segmentos. Por exemplo, suponha que alguém esteja olhando para `shoes, shirt` em uma página e na próxima página esteja olhando para `shirt, socks`. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

## Usar

1. Adicione uma visualização de ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL fallout]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Arraste um componente para o menu suspenso **[!UICONTROL Adicionar ponto de contato]**.

   >[!TIP]
   >
   >Você pode adicionar uma única página ao relatório de fallout, em vez da dimensão inteira. Clique na seta para a direita ![ChevronRight](/help/assets/icons/ChevronRight.svg) na dimensão de página para escolher uma página específica, como **[!UICONTROL página inicial]**, para adicionar ao relatório de Fallout.

   ![A página inicial da dimensão Página inicial arrastada para o campo Adicionar ponto de contato.](assets/fallout-drag.png)

1. Continue a adicionar pontos de contato até concluir a sequência.

   Os números circulados, na área em cinza da barra, apresentam o fallout entre os pontos de contato (e não o fallout geral daquele ponto). Os números circulados na parte verde da barra mostram o fallthrough bem-sucedido do ponto de contato anterior para o ponto de contato atual.

   ![Visualização Fallout](assets/fallout-visualization.png)

   Ao adicionar pontos de contato, siga um destes procedimentos:

   * Combine vários componentes arrastando um ou mais componentes adicionais em um único ponto de contato.

     >[!NOTE]
     >
     >Para unir vários segmentos, utilize o operador AND, mas para unir vários itens, como itens de dimensão e métricas, utilize OR.

   * Reordenar pontos de contato arrastando-os para um nível diferente na hierarquia de fallout.

   * Combine dois pontos de contato arrastando um ponto de contato para o outro. Solte o ponto de contato quando você vir a palavra **[!UICONTROL Combinar]**.

   * Restringir pontos de contato individuais ao próximo evento (em vez de *eventualmente*) dentro do caminho. Abaixo de cada ponto de contato, há um seletor com as opções **[!UICONTROL Caminho eventual]** e **[!UICONTROL Próximo evento]**, conforme mostrado aqui:

     | Opção | Descrição |
     |---|---|
     | **[!UICONTROL Caminho eventual]** (padrão) | Contagem de pessoas que *eventualmente* chegarão na próxima página do caminho, mas não necessariamente no próximo evento. |
     | **[!UICONTROL Próximo evento]** | São contadas as pessoas que chegarão à próxima página do caminho no próximo evento. |

   * Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre esse nível. As informações incluem o nome do ponto de contato, a contagem de pessoas e a taxa de sucesso. Você também pode comparar a taxa de sucesso com outros pontos de contato.

## Configurações  {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Container de fallout"
>abstract="Selecione um container para analisar a definição de caminho. Essa seleção ajuda a entender o engajamento e restringe a análise ao container selecionado."

Como parte da visualização, há configurações específicas disponíveis.

| Container de fallout | Descrição |
|--- |--- |
| **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]** | Alterne entre [!UICONTROL Sessão] e [!UICONTROL Pessoa] para analisar a definição de caminho da pessoa. O padrão é [!UICONTROL Pessoa]. Essas configurações ajudam você a entender o engajamento de pessoas (em sessões) ou restringir a análise a uma única sessão. |


## Menu de contexto

Como parte da visualização, há opções específicas do menu de contexto disponíveis.

### Acessar o menu de contexto

Você pode acessar o menu de contexto de uma das seguintes maneiras:

* Passe o mouse sobre um ponto de contato na visualização e selecione **[!UICONTROL Clique para analisar]**.

  ![Acessar menu de contexto a partir do cursor](assets/fallout-tooltip-analyze.png)

* Clique com o botão direito do mouse em um ponto de contato na visualização.

  ![Opções de fallout](assets/fallout-options.png)

### Opções do menu de contexto

As seguintes opções de menu de contexto estão disponíveis:

| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Tendência de ponto de contato]** | Veja os dados de tendência de um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-construídos. |
| **[!UICONTROL Tendência de ponto de contato (%)]** | Calcula a tendência da porcentagem total de fallout. |
| **[!UICONTROL Tendência de todos os pontos de contato (%)]** | Exibe a tendência de todas as porcentagens de pontos de contato do fallout (exceto **[!UICONTROL Todas as pessoas]**, se incluso) no mesmo gráfico. |
| **[!UICONTROL Detalhar o fallthrough neste ponto de contato]** | Visualize o que as pessoas fizeram entre dois pontos de contato (este e o próximo) se continuaram até o próximo ponto de contato. Isso cria uma tabela de forma livre mostrando suas dimensões. É possível substituir dimensões e outros elementos da tabela. Por exemplo, uma tabela rotulada como **[!UICONTROL Fallthrough: Todas as pessoas > Página é igual a qualquer página inicial]** e contém **[!UICONTROL Página]** como a dimensão e **[!UICONTROL Pessoas]** segmentadas pelo [segmento rápido somente de projeto](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: Todas as pessoas > Página é igual a qualquer página inicial]** como a métrica. Inspecione o segmento para entender como o segmento de fallthrough é determinado. |
| **[!UICONTROL Detalhar fallout neste ponto de contato]** | Veja o que as pessoas que não entraram na funnel fizeram imediatamente após a etapa selecionada. Isso cria uma tabela de forma livre mostrando suas dimensões. É possível substituir dimensões e outros elementos da tabela. Por exemplo, uma tabela rotulada como **[!UICONTROL Fallout: Pessoas > Página é igual a qualquer página inicial]** e contém **[!UICONTROL Página]** como a dimensão e **[!UICONTROL Pessoas]** segmentadas pelo [segmento rápido somente de projeto](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: Todos os Visitantes > Página é igual a qualquer um do segmento inicial]** como a métrica. Inspecione o segmento para entender como o segmento de fallout é determinado. |
| **[!UICONTROL Criar segmentos a partir do ponto de contato]** | Crie um novo segmento a partir do ponto de contato selecionado. |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto da visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

