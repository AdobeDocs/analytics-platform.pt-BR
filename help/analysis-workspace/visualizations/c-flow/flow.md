---
description: Saiba mais sobre o recurso Fluxo que mostra os caminhos do cliente pelos seus sites e aplicativos.
title: Visão geral do Fluxo
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 50%

---

# Fluxo {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="Fluxo"
>abstract="Crie uma visualização para exibir o fluxo de pessoas de um ponto de verificação para o próximo."

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="Fluxo"
>abstract="Analise o fluxo de visitas ou visitantes de um ponto de contato para o próximo.<br/><br/>**Parâmetros **<br/>**Começa com**: adicione uma dimensão, item de dimensão ou métrica para ver os principais pontos de contato após a ocorrência do componente selecionado.<br/>**Contém**: adicione uma dimensão ou item de dimensão para ver os principais pontos de contato antes e depois da ocorrência do componente selecionado.<br/>**Termina com**: adicione uma dimensão, item de dimensão ou métrica para ver os principais pontos de contato antes da ocorrência do componente selecionado.<br/>**Dimensão de definição de caminho**: adicione uma dimensão para usar como caminho conduzindo ou saindo do componente selecionado."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artigo documenta a visualização de Fluxo em **Customer Journey Analytics**.<br/>Consulte [Fluxo](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow) para a versão **Adobe Analytics**deste artigo.*

>[!ENDSHADEBOX]


A visualização de ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL Fluxo]** mostra os caminhos do cliente pelos seus sites e aplicativos.

Com a visualização, é possível:

* Visualize a jornada do cliente em seu site ou aplicativo.
* Analise onde os clientes vão antes e depois de pontos de verificação especificados, como entrada, uma dimensão específica ou saída.
* Crie filtros ao designar um ponto específico em um determinado caminho

+++ Assista a uma demonstração em vídeo da visualização de Fluxo.

>[!VIDEO](https://video.tv.adobe.com/v/346063/?quality=12)

{{videoaa}}

+++

## Fluxos interdimensionais

É possível mostrar o [fluxo entre dimensões](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md). Por exemplo, você pode combinar páginas e departamentos em um diagrama. Neste caso, seu fluxo pode ir da página inicial à página Masculino e, então, para o departamento de Sapatos.

Cada coluna pode exibir uma dimensão diferente. Arraste uma dimensão e solte em uma área para adicioná-la ao diagrama.

>[!MORELIKETHIS]
>
>[Configurar uma visualização de fluxo](/help/analysis-workspace/visualizations/c-flow/create-flow.md).
>

## Escolha entre as visualizações da tela de Fluxo, Fallout ou Jornada

A visualização de Fluxo tem semelhanças com a [visualização de Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) e a [visualização da tela de Jornada](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md), mas com diferenças importantes.

### Entender as diferenças

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Quando usar o Fluxo

As visualizações de fluxo são mais adequadas para:

* Análise ad hoc exploratória para o próximo ponto de contato imediato no caminho. (Use a tela de Jornada para jornadas com uma sequência predefinida de páginas ou aquelas que usam um caminho eventual.)

* Jornadas não lineares com vários pontos de entrada e caminhos. (Use a tela de Jornada para jornadas com uma sequência predefinida de páginas.)

Use [a tabela acima](#understand-the-differences) para entender as diferenças entre as telas de Fluxo, Fallout e Jornada.
