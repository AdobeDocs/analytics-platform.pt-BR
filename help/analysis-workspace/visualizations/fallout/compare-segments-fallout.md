---
description: Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos no Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Aplicar segmentos na análise de fallout
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 16%

---


# Aplicar filtros na análise de fallout

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar filtros a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar workflows principais em vários filtros no Analysis Workspace.

>[!IMPORTANT] Os Filtros usados como pontos de verificação no Fallout devem usar um container que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de visitante, os filtros usados como pontos de verificação devem ser filtros baseados em visita ou ocorrência. Com um Fallout de contexto de visita, os filtros usados como ponto de verificação devem ser segmentos baseados em ocorrências. Se você usar uma combinação inválida, o fallout será de 100%. Adicionamos um aviso à visualização de Fallout que será exibida quando você adicionar um filtro incompatível como ponto de contato. Determinadas combinações inválidas de container de filtro resultarão em diagramas de Fallout inválidos, como:

* Usar um filtro baseado em visitante como ponto de contato dentro de uma visualização de Fallout de contexto de visitante
* Usar um filtro baseado em visitante como ponto de contato dentro de uma visualização de Fallout de contexto de visita
* Usar um filtro baseado em visita como um ponto de contato dentro de uma visualização de Fallout de contexto de visita

## Create a filter from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crie um filtro a partir de um ponto de contato específico em que você esteja especialmente interessado e que possa ser útil para aplicar a outros relatórios. You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   O Construtor de filtro é aberto, pré-preenchido com o filtro sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![](assets/segment-builder.png)

1. Dê um título e uma descrição ao filtro e salve-o.

   Agora você pode usar esse filtro em qualquer projeto que desejar.

## Add a filter as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Se você quiser ver, por exemplo, como seus usuários dos EUA tendem e afetam o fallout, basta arrastar o filtro de usuários dos EUA para o fallout:

![](assets/segment-touchpoint.png)

Ou você pode criar um ponto de contato AND arrastando o filtro de usuários dos EUA para outro ponto de verificação.

## Compare filters in fallout {#section_E0B761A69B1545908B52E05379277B56}

É possível comparar um número ilimitado de filtros na visualização de Fallout.

1. Select the segments you want to compare from the [!UICONTROL Filter] rail on the left. Em nosso exemplo, selecionamos dois segmentos: usuários dos EUA e usuários de fora dos EUA.
1. Arraste-os para a área de depósito Filtro na parte superior.

   ![](assets/segment-drop.png)

1. Opcional: você pode manter “Todas as visitas” como contêiner padrão ou excluí-lo.

   ![](assets/seg-compare.png)

1. Agora você pode comparar o fallout entre os dois filtros, como onde um filtro está superando outro ou outros insights.
