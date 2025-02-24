---
description: Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.
title: Fluxos interdimensionais
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 1eeba4dc9de52f2890cf25794e767f199a4aa04c
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# Fluxos interdimensionais

Um fluxo interdimensional permite examinar os caminhos do usuário em várias dimensões. Este artigo mostra como usar esse fluxo para dois casos de uso: interações e eventos de aplicativos móveis e como campanhas direcionam visitas da Web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interações e eventos do aplicativo móvel

A dimensão [!UICONTROL Nome da tela] é usada neste fluxo de exemplo para ver como os usuários usam as várias telas (cenas) no aplicativo. A tela superior retornada é **[!UICONTROL luma: content: ios: en: home]**, que é a página inicial do aplicativo:

![Um fluxo mostrando o Item Adicionado.](assets/flowapp.png)

Para explorar a interação entre telas e tipos de evento (como adicionar ao carrinho, compras e outros) neste aplicativo, arraste e solte a dimensão **[!UICONTROL Tipos de evento]**:

* Sobre qualquer etapa disponível no fluxo, para substituir essa dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para as várias áreas.](assets/flowapp-replace.png)

* Fora da visualização de fluxo atual, para adicionar a dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para o espaço em branco no final.](assets/flowapp-add.png)

A visualização de fluxo abaixo mostra o resultado da adição da dimensão **[!UICONTROL Tipos de evento]**. A visualização fornece insights sobre como os usuários de aplicativos móveis se movem por várias telas no aplicativo antes de adicionar produtos ao carrinho, fechar o aplicativo, receber uma oferta e muito mais.

![Um fBaixo mostrando os resultados da dimensão Página no topo da lista.](assets/flowapp-result.png)

## Como as campanhas impulsionam as visitas da Web

Você deseja analisar quais campanhas direcionam visitas ao site. Você cria uma visualização de fluxo com o **[!UICONTROL Nome da campanha]** como a dimensão

![Dimensão do nome da campanha da Web de fluxo](assets/flowweb.png)

Substitua a última dimensão **[!UICONTROL Nome da Campanha]** pela dimensão **[!UICONTROL Nome da Página Formatada]** e adicione outra dimensão **[!UICONTROL Nome da Página Formatada]** ao final da visualização de fluxo.

![Nome da campanha da Web de fluxo e dimensão da página da Web](assets/flowweb-replace.png)

Você pode passar o mouse sobre qualquer um dos fluxos para ver mais detalhes. Por exemplo, quais campanhas resultaram em um check-out no carrinho.

![Focalizar o nome da campanha da Web de fluxo e a dimensão da página da Web](assets/flowweb-hover.png)
