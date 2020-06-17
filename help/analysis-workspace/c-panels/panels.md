---
description: 'null'
title: Visão geral dos painéis
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 79%

---


# Visão geral dos painéis

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Um painel é uma coleção de tabelas e visualizações. Você pode acessar painéis usando o ícone superior esquerdo no Workspace. Os painéis são úteis quando você deseja organizar seus projetos de acordo com períodos de tempo, unidades comerciais, geografia etc. Estes quatro tipos de painéis estão disponíveis no Analysis Workspace para Customer Journey Analytics:

* [Painel em branco](blank-panel.md)
* [Painel Quick Insights](quickinsight.md)
* [Painel de atribuição](attribution.md)
* [Painel de forma livre](freeform-panel.md)

Insights rápidos, painéis em branco e de forma livre são ótimos locais para start de sua análise, enquanto o painel QI de atribuição se presta a análises mais avançadas. Um `"+"` botão está disponível em projetos para que você possa adicionar painéis em branco a qualquer momento.

The default starting panel is the Freeform panel, but you can make the [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) your default as well.

## filtros suspensos em painéis

A área de soltar do painel agora tem recursos suspensos de filtragem. Esses filtros permitem interagir com os dados do projeto de forma controlada para fazer análises mais detalhadas, simplificar seus projetos e/ou compartilhar insights com outras pessoas.

Um exemplo de um projeto simplificado: suponhamos que você tenha várias versões de um projeto/painel para fazer relatórios específicos de país. Agora, você pode retrair esses projetos/painéis em um único painel, e adicioná-lo em um detalhamento de países em vez de filtrar entre conjuntos de dados diferentes.

![](assets/dropdowns.png)

Lembre-se:

* É possível soltar vários componentes (ou itens de dimensão) e alternar entre eles em uma lista suspensa para filtrar os conteúdos do painel.
* Além disso, você pode criar várias listas suspensas no mesmo painel.
* Você pode personalizar o título da lista suspensa ao clicar no título e modificá-lo, ou remover o título ao clicar no x ao lado dele.
* É possível criar filtros suspenso usando qualquer tipo de componente: dimensões, intervalos de datas, segmentos e métricas. Observe que os intervalos de datas suspensos sempre substituirão os intervalos de datas do painel.
* Mantemos as cores do componente do painel à esquerda: amarelo para itens suspensos da dimensão, verde para métricas, azul para segmentos e roxo para intervalos de datas.
* A área de soltar itens ainda criará segmentos a nível de ocorrência para itens arrastados como segmentos. É possível modificá-los como de costume ao clicar no ícone de informações (i) ao lado do segmento, em seguida no ícone de edição em forma de lápis e editá-los no Construtor de segmento.

**Para criar e usar filtros suspensos:**

1. Selecione quaisquer itens no painel à esquerda e, **mantendo pressionada a tecla**, solte-os na área de soltar do painel.

   ![](assets/create_dropdown.png)

   Isso os transformará em uma lista suspensa, em vez de em um segmento. (Também é possível adicionar segmentos sem manter a tecla pressionada.)

   ![](assets/dropdown.png)

1. Selecione uma das opções na lista suspensa para alterar os dados no painel abaixo. (Também é possível optar por não filtrar os dados do painel ao selecionar **[!UICONTROL Nenhum filtro]**.)
1. Por exemplo, se você também quiser dividir os dados por canal de marketing, você pode adicionar outra lista suspensa chamada “Canal de marketing”:

   ![](assets/mc_dropdown.png)

