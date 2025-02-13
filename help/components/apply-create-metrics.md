---
description: Há duas formas de utilizar as métricas no Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 14%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Utilização de métricas no Analysis Workspace

As métricas são flexíveis em seu uso no Analysis Workspace. Arraste uma métrica para uma Tabela de forma livre vazia para ver a tendência da métrica no período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver essa métrica em comparação com cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente a substitui e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:


* **Métricas padrão**: exemplos de métricas padrão são Pessoas, Sessões, Eventos.

  Ao contrário do Adobe Analytics, o Customer Journey Analytics permite definir métricas padrão de maneira flexível no escopo de uma conexão e de uma visualização de dados.

   * **Pessoas**: a métrica Pessoas no Customer Journey Analytics é a contagem distinta das IDs de pessoa. Dependendo do que você escolher como a ID de pessoa ao configurar conjuntos de dados em sua conexão, a métrica de Pessoas pode ter significados diferentes.
   * **Sessões**: a métrica Sessões no Customer Journey Analytics é o que você define como parte da configuração das Configurações de sessões na sua visualização de dados. Consulte [Configurações da sessão](/help/data-views/session-settings.md).
   * **Eventos**: a métrica Eventos no Customer Journey Analytics é composta pelos eventos que fazem parte de qualquer conjunto de dados de evento configurado como parte da conexão.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): métricas definidas pelo usuário baseadas em métricas padrão, números estáticos ou funções algorítmicas.

* **Modelos de métrica calculada** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : métricas definidas por Adobe que se comportam de forma semelhante às métricas calculadas. Você pode usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar a lógica. Consulte [Métricas calculadas padrão](calc-metrics/cm-workflow/../default-calcmetrics.md).

Você pode ver se uma métrica foi aprovada ![ícone Aprovado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou não. Para obter mais detalhes sobre uma métrica, passe o mouse sobre a métrica e selecione ![Ícone de informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Informações do componente](use-components-in-workspace.md#component-info) para obter mais informações.



## Métricas calculadas

Métricas calculadas permitem configurar facilmente como as métricas se relacionam entre si usando operadores simples ou funções estatísticas. Consulte [Visão geral das métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter mais informações.

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

+++

-->

## Comparar métricas com diferentes modelos de atribuição

Se você deseja comparar um modelo com outro de maneira fácil e rápida para uma métrica, selecione **[!UICONTROL Comparar modelos de atribuição]** no menu de contexto para uma métrica.

![realce do painel do Workspace Comparar modelos de atribuição](assets/compare-attribution.png)

Esse atalho permite comparar modelos de atribuição de maneira rápida e fácil.
