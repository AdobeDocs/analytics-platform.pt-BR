---
description: É possível criar filtros desde de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho principais em vários filtros no Analysis Workspace.
keywords: fallout e filtros; filtros na análise de fallout; comparar filtros no fallout
title: Aplicar filtros na análise de fallout
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Aplicar filtros na análise de fallout

É possível criar filtros desde de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho principais em vários filtros no Analysis Workspace.

>[!IMPORTANT]
>
>Os filtros usados como pontos de verificação no Fallout devem usar um contêiner que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de visitante, os filtros usados como pontos de verificação devem ser filtros baseados em visita ou ocorrência. Com um Fallout de contexto de visita, os filtros usados como ponto de verificação devem ser filtros baseados em ocorrências. Se você usar uma combinação inválida, o fallout será de 100%. Adicionamos um aviso à visualização de Fallout que será exibida quando você adicionar um filtro incompatível como ponto de contato. Determinadas combinações inválidas de contêineres de filtro resultarão em diagramas de Fallout inválidos, por exemplo:

* Usar um filtro com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto do visitante
* Usar um filtro com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas
* Usar um filtro com base em visitas como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas

## Criar um filtro a partir de um ponto de contato {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crie um filtro a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Você faz isso clicando com o botão direito do mouse no ponto de contato e selecionando **[!UICONTROL Criar filtro desde o ponto de contato]**.

   ![](assets/segment-from-touchpoint.png)

   O Construtor de filtro abre, pré-preenchido com o filtro sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![](assets/segment-builder.png)

1. Atribua um título e uma descrição ao filtro e salve-o.

   Agora, você pode usar este filtro em qualquer projeto.

## Adicionar um filtro como ponto de contato {#section_17611C1A07444BE891DC21EE8FC03EFC}

Se quiser ver, por exemplo, a tendência dos seus usuários dos EUA e como eles afetam o fallout, basta arrastar o filtro de usuários dos EUA ao fallout:

![](assets/segment-touchpoint.png)

Ou, você pode criar um ponto de contato AND, arrastando o filtro de usuários dos EUA ao outro ponto de verificação.

## Comparar filtros no fallout {#section_E0B761A69B1545908B52E05379277B56}

É possível comparar um número ilimitado de filtros na visualização de Fallout.

1. Selecione os filtros que deseja comparar, no painel [!UICONTROL Filtro] à esquerda. Em nosso exemplo, selecionamos dois filtros: usuários dos EUA e usuários de fora dos EUA.
1. Arraste-os à área de Filtro na parte superior.

   ![](assets/segment-drop.png)

1. Opcional: você pode manter “Todas as visitas” como o contêiner padrão ou excluí-lo.

   ![](assets/seg-compare.png)

1. Agora você pode comparar o fallout nos dois filtros, como onde um filtro supera o outro ou outros insights.
