---
title: Painel de atribuição
description: Como usar e interpretar o painel de atribuição no Analysis Workspace.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 84%

---


# Painel de atribuição

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

O painel de atribuição é uma maneira fácil para criar uma análise comparando vários modelos de atribuição. É um recurso no [Attribution IQ](../attribution/overview.md) que oferece um espaço de trabalho dedicado para usar e comparar modelos de atribuição.

## Criar um painel de atribuição

1. Clique no ícone do painel à esquerda.
1. Arraste o Painel de atribuição para seu projeto do Analysis Workspace.

   ![Novo painel de atribuição](assets/Attribution_Panel_1.png)

1. Adicione uma métrica que você deseja atribuir e adicione qualquer dimensão ao atributo. Os exemplos incluem Canais de marketing ou dimensões personalizadas, como promoções internas.

   ![Selecionar dimensão e métrica](assets/attribution_panel2.png)

1. Selecione os [modelos de atribuição e a janela de pesquisa](../attribution/models.md) que você deseja comparar.

1. O painel Atribuição retorna um conjunto avançado de dados e visualizações que comparam a atribuição da dimensão e da métrica selecionadas.

   ![Visualizações de atribuição](assets/attr_panel_vizs.png)

## Visualizações de atribuição

* **Métrica total**: o número total de conversões que ocorreram ao longo da janela de tempo do relatório. Essas são as conversões atribuídas pela dimensão selecionada.
* **Gráfico de barras de comparação de atribuição de métrica**: compara visualmente as conversões atribuídas em cada um dos itens de dimensão da dimensão selecionada. Cada cor da barra representa um modelo de atribuição distinto.
* **Tabela de forma livre de atribuição de métrica**: mostra os mesmos dados que o gráfico de barras, representado como uma tabela. Selecionar diferentes colunas ou linhas nesta tabela filtra o gráfico de barras, bem como várias outras visualizações no painel. Esta tabela atua de forma semelhante a qualquer outra Tabela de forma livre no Workspace - permitindo que você adicione componentes como métricas, segmentos ou detalhamentos.
* **Gráfico de sobreposição Dimension**: Um diagrama Venn mostrando os três principais itens de dimensão e a frequência com que eles participam em conjunto em uma conversão. Por exemplo, o tamanho da sobreposição de bolha indica a frequência com que as conversões ocorreram quando um visitante foi exposto a ambos os itens de dimensão. Selecionar outras linhas na tabela de Forma livre adjacente atualizará a visualização para refletir a seleção.
* **Pontos de contato de marketing por jornada**: um histograma que indica o número de pontos de contato que um visitante teve na janela de pesquisa. Isso é útil para descobrir o impacto da atribuição de multitoque em seu conjunto de dados. Se quase todos os visitantes tiverem apenas um único ponto de contato, modelos de atribuição diferentes provavelmente mostrarão dados semelhantes.
* **Detalhe de desempenho do canal de marketing**: permite comparar até três modelos de atribuição visualmente usando um gráfico de dispersão
* **Fluxo do canal de marketing**: permite ver em quais canais há mais interação e em que ordem isso ocorre na jornada de um visitante
