---
description: É possível criar filtros desde de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho principais em vários filtros no Analysis Workspace.
keywords: fallout e filtros; filtros na análise de fallout; comparar filtros no fallout
title: Aplicar filtros na análise de fallout
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 45%

---

# Aplicar filtros na análise de fallout

É possível criar filtros desde de um ponto de contato, adicionar filtros como ponto de contato e comparar fluxos de trabalho principais em vários filtros no Analysis Workspace.

>[!IMPORTANT]
>
>Os filtros usados como pontos de verificação no Fallout devem usar um contêiner que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de pessoa, os filtros usados como pontos de verificação devem ser filtros baseados em visitas ou eventos. Com um Fallout de contexto de visita, os filtros usados como ponto de verificação devem ser filtros baseados em eventos. Se você usar uma combinação inválida, o fallout será de 100%. Você vê um aviso para a visualização de Fallout ao adicionar um filtro incompatível como ponto de contato. Determinadas combinações inválidas de contêineres de filtro geram diagramas de Fallout inválidos, como:

* Usar um filtro com base em pessoas como um ponto de contato dentro de uma visualização de Fallout de contexto de pessoas
* Usar um filtro com base em pessoas como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas
* Usar um filtro com base em visitas como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas

## Criar um filtro a partir de um ponto de contato

1. Crie um filtro a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Clique com o botão direito no ponto de contato e selecione **[!UICONTROL Criar filtro a partir do ponto de contato]**.

   ![O menu suspenso Ponto de Contato com a opção Criar segmento a partir do ponto de contato realçada.](assets/fallout-createfilter.png)

   O [!UICONTROL Construtor de filtros] abre, preenchido previamente com o filtro sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![O Construtor de Filtros exibe o filtro sequencial pré-preenchido e pré-construído.](assets/fallout-definefilter.png)

1. Atribua um título e uma descrição ao filtro e salve-o.

   Agora, você pode usar este filtro em qualquer projeto.

## Adicionar um filtro como ponto de contato

Se quiser ver, por exemplo, a tendência dos seus usuários dos EUA e como eles afetam o fallout, basta arrastar o filtro de usuários dos EUA ao fallout:

![O filtro Usuários dos EUA foi selecionado e realçado para arrastar para o fallout.](assets/fallout-addfilter.png)

Ou, você pode criar um ponto de contato AND, arrastando o filtro de usuários dos EUA ao outro ponto de verificação.

## Comparar filtros no fallout

É possível comparar um número ilimitado de filtros na visualização de Fallout.

1. Selecione os filtros que deseja comparar, no painel [!UICONTROL Filtro] à esquerda. No exemplo, três filtros são selecionados: *Detalhes do voo: Versão da página A*, *Detalhes do voo: Versão da página B* e *Detalhes do voo: Versão da página C*.
1. Arraste os três filtros até a área de Filtro na parte superior da visualização.


1. Opcional: Você pode manter *Todas as visitas* como o contêiner padrão ou excluir o contêiner.

   ![O Fallout mostra Todas as Visitas juntamente com os dois filtros arrastados na etapa anterior.](assets/fallout-multiplefilters.png)

1. Agora é possível comparar o fallout nos três filtros, como em que um filtro está com desempenho melhor que outro ou em outros insights.
