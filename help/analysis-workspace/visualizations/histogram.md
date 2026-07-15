---
description: Saiba como usar um histograma, que é semelhante a um gráfico de barras, mas agrupa números em intervalos (grupos).
title: Histograma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
autotag-review: '2026-05-19T08:31:33.712Z'
TQID: 'https://experienceleague.adobe.com/X9T4RpAiJ8uL0clPhyjffdl02kwd-k2Jv3O5t6iHfss'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 494
ht-degree: 68%

---

# Histograma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Histograma"
>abstract="Crie uma visualização de histograma para representar a distribuição de dados numéricos em grupos de intervalos."


>[!BEGINSHADEBOX]

_Este artigo documenta a visualização de Histograma em_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consulte [Histograma](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram) da versão_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


A visualização em ![Histograma ](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]** é semelhante à visualização em [!UICONTROL Barras], mas agrupa os números em intervalos (compartimentos). O Analytics automatiza o agrupamento de números em intervalos, mas você pode alterar as configurações em [Configurações avançadas](#advanced-settings).

## Usar

Para criar um histograma:

1. Adicionar uma visualização de ![Histograma](/help/assets/icons/Histogram.svg) **[!UICONTROL Histograma]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
1. Arraste uma métrica da lista de componentes **[!UICONTROL Métricas]** ou selecione uma métrica do menu suspenso [!UICONTROL *Adicionar uma métrica*].
1. Selecione **[!UICONTROL Mostrar configurações avançadas]**. Consulte [Configurações avançadas](#advanced-settings)
1. Selecione **[!UICONTROL Criar]**.

>[!NOTE]
>
>Os histogramas são compatíveis apenas com métricas padrão, não calculadas.

No exemplo abaixo, um histograma é usado para agrupar sessões para o número de pessoas. O histograma mostra que a maioria das pessoas tem entre 16 e 21 sessões para o intervalo de datas selecionado.

![Histograma](assets/histogram.png)

## Configurações avançadas

Como parte da visualização, configurações específicas do histograma estão disponíveis.

| Configurações do histograma | Descrição |
|---|---|
| **[!UICONTROL Grupo inicial]** | Determina com qual bloco o histograma começa. &quot;1&quot; é o padrão. Você pode definir números iniciais de 0 até o infinito (sem números negativos). |
| **[!UICONTROL Grupos de métricas]** | Permite aumentar/diminuir o número de intervalos de dados (compartimentos). O número máximo de grupos é 50. |
| **[!UICONTROL Tamanho do grupo de métricas]** | Permite definir o tamanho de cada intervalo. Por exemplo, você pode alterar o tamanho do intervalo de uma exibição de página para duas exibições de página. |
| **[!UICONTROL Método de contagem]** | Selecione da **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Grupo de Compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Pessoa]**, **[!UICONTROL Sessão]**, **[!UICONTROL Evento]** ou **[!UICONTROL Objeto]**. Por exemplo, visualizações de página por conta [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, visualizações de página por sessão, visualizações de página por pessoa ou visualizações de página por evento. Ao selecionar **[!UICONTROL Objeto]**, selecione o [contêiner personalizado](/help/data-views/create-dataview.md#containers-1) para análise de subevento. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exemplos**:

| Grupo inicial | Grupos de métricas | Tamanho do grupo de métricas | Resultado |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Histograma, compartimento inicial 1, compartimentos de métrica 5, tamanho do compartimento de métrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Histograma, compartimento inicial 0, compartimentos de métrica 3, tamanho do compartimento de métrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painelConfigurações de visualizaçãoMenu de contexto de visualizaçãoUsando histogramas para identificar valores de dados inesperados](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

