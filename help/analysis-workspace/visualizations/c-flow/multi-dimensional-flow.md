---
description: Entenda como um fluxo interdimensional permite examinar os caminhos do usuário em várias dimensões.
title: Fluxos interdimensionais
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 89%

---

# Fluxos interdimensionais

Um fluxo interdimensional permite examinar os caminhos do usuário em várias dimensões. Este artigo mostra como usar esse fluxo para dois casos de uso: interações e eventos de aplicativos móveis e como campanhas direcionam visitas da Web

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Interações e eventos de aplicativos móveis

A dimensão [!UICONTROL Nome da tela] é usada neste fluxo de exemplo para ver como os usuários utilizam as várias telas (cenas) no aplicativo. A tela superior retornada é **[!UICONTROL luma: content: ios: en: home]**, que é a página inicial do aplicativo:

![Um fluxo mostrando o item adicionado.](assets/flowapp.png)

Para observar a interação entre telas e tipos de evento (como adições ao carrinho, compras e outros) neste aplicativo, arraste e solte a dimensão **[!UICONTROL Tipos de evento]**:

* Sobre qualquer etapa disponível no fluxo, para substituir essa dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para as várias áreas.](assets/flowapp-replace.png)

* Fora da visualização de fluxo atual, para adicionar a dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para o espaço em branco no final.](assets/flowapp-add.png)

A visualização de fluxo abaixo mostra o resultado de adicionar a dimensão **[!UICONTROL Tipos de evento]**. A visualização fornece informações sobre a navegação de usuários de aplicativos móveis pelas telas do aplicativo antes de adicionar produtos ao carrinho, fechar o aplicativo, receber uma oferta e mais.

![Um fluxo mostrando os resultados da dimensão Página na parte superior da lista.](assets/flowapp-result.png)

## Como as campanhas impulsionam visitas da web

Você deseja analisar quais campanhas impulsionam visitas para o site. Para isso, você cria uma visualização de fluxo com o **[!UICONTROL Nome da campanha]** como a dimensão

![Fluxo da dimensão Nome da campanha da web](assets/flowweb.png)

Você substitui a última dimensão **[!UICONTROL Nome da campanha]** pela dimensão **[!UICONTROL Nome da página formatada]** e adiciona outra dimensão **[!UICONTROL Nome da página formatada]** ao final da visualização de fluxo.

![Fluxo da dimensão Nome da campanha da web e Página da web](assets/flowweb-replace.png)

É possível passar o mouse sobre qualquer um dos fluxos para ver mais detalhes. Por exemplo, quais campanhas resultaram em um check-out do carrinho.

![Fluxo da dimensão Nome da campanha da web e detalhes da página da web](assets/flowweb-hover.png)
