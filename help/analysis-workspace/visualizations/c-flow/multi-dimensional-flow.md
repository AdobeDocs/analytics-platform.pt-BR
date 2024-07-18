---
description: Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.
title: Fluxos interdimensionais
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 73%

---

# Fluxos interdimensionais

Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.

Um rótulo de dimensão na parte superior de cada coluna de Fluxo torna mais intuitivo o uso de várias dimensões em uma visualização de fluxo:

![Um fluxo interdimensional destacando várias dimensões, incluindo Produto, Página, Versão do Sistema Operacional e Tempo Gasto.](assets/flow.png)

Vamos analisar dois casos de uso: um de aplicativo e um da web.

## Caso de uso 1: aplicativo

A dimensão de [!UICONTROL Nome da ação] foi adicionada ao fluxo, com os principais itens retornados sendo [!UICONTROL ItemAdded]:

![Um fluxo mostrando o Item Adicionado.](assets/multi-dimensional-flow.png)

Para explorar a interação entre telas/páginas e ações neste aplicativo, você pode arrastar a dimensão de página a diferentes locais, dependendo do que você deseja explorar:

* Arraste-o para uma área (dentro do retângulo com margens pretas exibido) para **substituir** os resultados principais nos finais:

  ![Um fluxo mostrando a dimensão Página arrastada para as várias áreas.](assets/multi-dimensional-flow2.png) ![Diagrama de fluxo mostrando os itens arrastados.](assets/multi-dimensional-flow3.png)

* Arraste para o espaço branco no final (observe o colchete preto) para **adicionar à** visualização:

  ![Um fluxo mostrando a dimensão Página arrastada para o espaço em branco no final.](assets/multi-dimensional-flow4.png)

Aqui está o resultado se você decidir substituir o item ItemScaled na coluna da direita com a dimensão de Página. Os principais resultados são substituídos para os principais resultados para a dimensão de Página:

![Um fBaixo mostrando os resultados da dimensão Página no topo da lista.](assets/multi-dimensional-flow5.png)

Agora você pode ver como os clientes se movem pelas ações e páginas. Você pode explorar o fluxo, clicando em diferentes nós:

![Um fluxo mostrando Itens Adicionados, Itens Arrastados e Modo de Exibição Principal.](assets/multi-dimensional-flow6.png)

É isso que acontece ao adicionar outra dimensão de Nome de ação no final da visualização:

![Um fluxo mostrando o Nome da Ação adicionado.](assets/multi-dimensional-flow7.png)

Isso permitirá insights aprofundados e possíveis alterações ao aplicativo que você está analisando.

## Caso de uso 2: web

Este caso de uso mostra como você pode analisar quais campanhas impulsionam a maioria das entradas em um site.

Arraste a dimensão de Nome da campanha para um novo fluxo:

![Um fluxo mostrando a dimensão Nome da Campanha arrastado para um novo fluxo.](assets/multi-dimensional-flow8.png)

Agora, quero saber para quais páginas essas campanhas estão impulsionando tráfego, então, arrasto a dimensão de Página à direita dos resultados de fluxo para adicionar à visualização:

![Um fluxo mostrando a dimensão Página arrastada à direita dos resultados do fluxo.](assets/multi-dimensional-flow9.png)
