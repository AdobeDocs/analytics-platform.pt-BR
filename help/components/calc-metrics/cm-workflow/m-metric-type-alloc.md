---
description: Saiba mais sobre tipo de métrica e atribuição.
title: Atribuição E Tipo De Métrica
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 98%

---

# Tipo de métrica e atribuição

Você pode configurar o tipo de métrica e o [modelo de atribuição](#attribution-models) para uma métrica em uma definição de métrica calculada.

1. Selecione a ![Configuração](/help/assets/icons/Setting.svg) no componente de métrica.
1. Na caixa de diálogo pop-up:

   ![Tipo de métrica e atribuição](assets/cm-type-alloc.png)

   * Especifique o **[!UICONTROL Tipo de métrica]**:

     | Tipo de métrica | Definição |
     |---|---|
     | **[!UICONTROL Padrão]** | Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item da linha.  <p>Por exemplo, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Pedidos]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessões]** pega os pedidos de um item da linha específico e divide pelo número de sessões desse item de linha específico. |
     | **[!UICONTROL Total geral]** | Use o **[!UICONTROL Total geral]** para informar o período de relatórios em cada item da linha. Se uma fórmula consistir em uma única métrica de total geral, a métrica calculada exibirá o mesmo número de total geral em cada item da linha. As métricas de total geral são úteis quando você deseja criar métricas calculadas que se comparam aos dados totais. <p>Por exemplo, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Pedidos]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total de sessões]** mostra a proporção de pedidos com relação a todas as sessões, não apenas as sessões com o item da linha específico. Neste exemplo, você especifica **[!UICONTROL Total geral]** para a métrica ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sessões]** em sua métrica calculada, que a transformará automaticamente em ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total de sessões]**. |

   * Especifique a **[!UICONTROL atribuição]**.

      1. Você também pode:

         * Desabilitar a opção **[!UICONTROL Usar modelo de atribuição não padrão]** para usar o modelo de atribuição de coluna padrão, que é Último contato, com uma janela de pesquisa de 30 dias.
         * Habilitar a opçã o **[!UICONTROL Usar modelo de atribuição não padrão]**. Na caixa de diálogo **[!UICONTROL Modelo de atribuição de coluna]**,

            * Selecione um **[!UICONTROL Modelo]** nos [modelos de atribuição](#attribution-models).
            * Selecione um **[!UICONTROL Container]** nas opções de [container](#container).
            * Selecione uma **[!UICONTROL Janela de retrospectiva]** nas opções da [janela de retrospectiva](#lookback-window). Se você selecionar **[!UICONTROL Hora personalizada]**, poderá definir o período em **[!UICONTROL Minuto(s)]** até **[!UICONTROL Trimestre(s)]**.

      1. Selecione **[!UICONTROL Aplicar]** para aplicar o modelo de atribuição não padrão. Selecione Cancelar para cancelar.

     Se você já tiver definido um modelo de atribuição não padrão, selecione **[!UICONTROL Editar]** para modificar a seleção.

Consulte [Exemplo](#example) para ver um exemplo de uso de um modelo de atribuição, container e janela de pesquisa.


## Modelos de atribuição {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Usar modelo de atribuição não-padrão"
>abstract="Habilite um modelo de atribuição não padrão para a métrica selecionada."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modelo"
>abstract="Selecione um modelo de atribuição para a métrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Último contato"
>abstract="100% do crédito vai para o último valor de dimensão visto por um visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primeiro contato"
>abstract="100% do crédito vai para o primeiro valor de dimensão visto por um visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="O crédito é distribuído uniformemente em todos os valores de dimensão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participação"
>abstract="100% de crédito para cada valor de dimensão visto por um visitante.<br/>Os totais da coluna estão exagerados."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Mesmo contato"
>abstract="O crédito é fornecido somente para valores de dimensão que ocorrem no mesmo evento que a conversão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Mesmo contato"
>abstract="O crédito é fornecido somente para valores de dimensão que ocorrem no mesmo evento que a conversão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="Forma de U"
>abstract="40% do crédito é atribuído ao primeiro valor de dimensão, 40% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="60% do crédito é atribuído ao valor da última dimensão, 20% ao primeiro, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="60% do crédito é atribuído ao valor da última dimensão, 20% ao primeiro, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J invertido"
>abstract="60% do crédito é atribuído ao primeiro valor de dimensão, 20% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J invertido"
>abstract="60% do crédito é atribuído ao primeiro valor de dimensão, 20% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Declínio de tempo"
>abstract="Os valores de dimensão mais próximos do tempo a uma conversão recebem mais crédito."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizado"
>abstract="Defina sua própria posição com base na ponderação de atribuição."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizado"
>abstract="Defina sua própria posição com base na ponderação de atribuição."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorítmico"
>abstract="O crédito é determinado dinamicamente em um algoritmo estatístico."

{{attribution-models-details}}


## Container {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Container"
>abstract="Selecione um container para definir o escopo desejado da atribuição."

{{attribution-container}}


## Janela de pesquisa {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Janela de pesquisa"
>abstract="Essa configuração determina a janela de atribuição de dados que será aplicada a cada conversão."

{{attribution-lookback-window}}




## Exemplo

{{attribution-example}}

>[!MORELIKETHIS]
>
>[Configurações de componentes de atribuição](/help/data-views/component-settings/attribution.md)
>&#x200B;>[Métrica de participação](participation-metric.md)
>

