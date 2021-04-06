---
description: Você pode criar filtros de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho importantes em vários filtros no Analysis Workspace.
keywords: fallout e filtros, filtros na análise de fallout, comparar filtros no fallout
title: Aplicar filtros na análise de fallout
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# Aplicar filtros na análise de fallout

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode criar filtros de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho importantes em vários filtros no Analysis Workspace.

>[!IMPORTANT]
>
>Os filtros usados como pontos de verificação no Fallout devem usar um contêiner que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de visitante, os filtros usados como pontos de verificação devem ser filtros baseados em visita ou ocorrência. Com um Fallout de contexto de visita, os filtros usados como ponto de verificação devem ser filtros baseados em ocorrências. Se você usar uma combinação inválida, o fallout será de 100%. Adicionamos um aviso à visualização de Fallout que será exibida quando você adicionar um filtro incompatível como ponto de contato. Determinadas combinações inválidas de contêineres de filtro resultarão em diagramas de Fallout inválidos, como:

* Usar um filtro com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto de visitante
* Usar um filtro com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas
* Usar um filtro baseado em visitas como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas

## Crie um filtro a partir de um ponto de contato {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crie um filtro a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Para fazer isso, clique com o botão direito do mouse no ponto de contato e selecione **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   O Construtor de filtros é aberto, pré-preenchido com o filtro sequencial pré-criado que corresponde ao ponto de contato selecionado:

   ![](assets/segment-builder.png)

1. Dê um título e uma descrição ao filtro e salve-o.

   Agora você pode usar esse filtro em qualquer projeto que desejar.

## Adicionar um filtro como ponto de contato {#section_17611C1A07444BE891DC21EE8FC03EFC}

Se você quiser ver, por exemplo, a tendência de seus usuários dos EUA e afetar o fallout, basta arrastar o filtro de usuários dos EUA para o fallout:

![](assets/segment-touchpoint.png)

Ou você pode criar um ponto de contato AND arrastando o filtro de usuários dos EUA para outro ponto de verificação.

## Comparar filtros no fallout {#section_E0B761A69B1545908B52E05379277B56}

Você pode comparar um número ilimitado de filtros na visualização de Fallout.

1. Selecione os filtros que deseja comparar no painel [!UICONTROL Filtro] à esquerda. No nosso exemplo, selecionamos dois filtros: Usuários dos EUA e usuários não dos EUA.
1. Arraste-os até a área de soltar Filtro na parte superior.

   ![](assets/segment-drop.png)

1. Opcional: você pode manter “Todas as visitas” como contêiner padrão ou excluí-lo.

   ![](assets/seg-compare.png)

1. Agora é possível comparar o fallout nos dois filtros, como quando um filtro está superando outro ou outros insights.
