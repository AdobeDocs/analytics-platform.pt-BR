---
description: Saiba como usar a visualização de fluxo no Analysis Workspace.
title: Visão geral do fluxo
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 74%

---

# Visão geral do Fluxo {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Fluxo"
>abstract="Crie uma visualização para exibir o fluxo de pessoas de um ponto de verificação para o próximo."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Fluxo"
>abstract="Analise o fluxo de visitas ou visitantes de um ponto de contato para o próximo. Especifique um componente (métrica, dimensão ou item) para começar e terminar. Como opção, você pode definir configurações avançadas para personalizar ainda mais a visualização."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta a Visualização de fluxo no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulte [Fluxo](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) para a versão_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]


O recurso ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Fluxo]** mostra os caminhos do cliente pelos seus sites e aplicativos.

Com a visualização, é possível:

* Visualizar a jornada do cliente pelo seu site ou aplicativo.
* Analisar aonde os clientes vão antes e depois de pontos de verificação específicos, como a entrada, uma dimensão específica ou a saída.
* Crie segmentos designando um ponto específico em um caminho escolhido.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Criar uma visualização de fluxo](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"} para assistir a um vídeo de demonstração.

{{videoaa}}

>[!ENDSHADEBOX]


## Fluxos interdimensionais

É possível mostrar o [fluxo entre dimensões](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Por exemplo, você pode combinar páginas e departamentos em um diagrama. Nesse caso, seu fluxo pode ir da página inicial para a página Homens e, em seguida, para o departamento de Sapatos.

Cada coluna poderia mostrar uma dimensão diferente. Arraste uma dimensão e solte-a em uma área designada para adicionar essa dimensão ao diagrama.

>[!MORELIKETHIS]
>
>[Configurar uma visualização de fluxo](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Escolha entre as visualizações de fluxo, fallout ou tela da jornada

A visualização de fluxo tem semelhanças com a [visualização de fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e a [visualização da tela da jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), mas com diferenças importantes.

### Entenda as diferenças

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando usar o fluxo

As visualizações de fluxo são mais adequadas para:

* Análise ad hoc exploratória para o próximo ponto de contato imediato no caminho. (Use a tela da jornada no caso de jornadas com uma sequência predefinida de páginas ou que usam um caminho eventual.)

* Jornadas não lineares com vários pontos de entrada e caminhos. (Use a tela da jornada no caso de jornadas com uma sequência predefinida de páginas.)

Use [a tabela acima](#understand-the-differences) para entender as diferenças entre fluxo, fallout e tela da jornada.
