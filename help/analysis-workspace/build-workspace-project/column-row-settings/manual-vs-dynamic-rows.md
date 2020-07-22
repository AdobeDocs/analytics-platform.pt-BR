---
title: Itens de dimensão dinâmicos vs estáticos
description: Como interagir com itens de dimensão dinâmicos e estáticos em tabelas.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 8%

---


# Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Nas tabelas de forma livre, as linhas e colunas podem conter vários valores de componentes nelas. Esses valores podem ser dinâmicos (alterar com o tempo) ou estáticos (não mudar com o tempo), dependendo da análise que você deseja criar.

## Itens de dimensão dinâmicos

Os itens de dimensão dinâmicos mudam com o tempo e dependem da métrica que está sendo classificada na tabela de forma livre. Os itens de dimensão dinâmica são preferidos quando você deseja analisar os itens principais de um determinado período de tempo.

Quando você solta uma dimensão em uma tabela de forma livre, linhas dinâmicas são retornadas. Eles representam os itens principais que correspondem à dimensão de uma determinada métrica e período de tempo. Também é possível soltar uma dimensão em colunas de tabela de forma livre e a dimensão se expande automaticamente para os 5 itens de dimensão principais.

Por exemplo, quando você arrasta a dimensão Tipo de navegador para a tabela, os itens de dimensão Tipo de navegador principais (por exemplo, Microsoft, Apple, Google etc.) retornar dinamicamente às linhas da tabela. Se forem soltos em uma coluna, os 5 itens de dimensão Tipo de navegador principais retornarão dinamicamente.

Os itens de dimensão dinâmica têm a opção de filtro de linha e **não** têm ícones de bloqueio e X presentes.

## Itens de dimensão estática

Os itens de dimensão estática não mudam com o tempo; são componentes fixos que são sempre retornados em uma tabela de forma livre. Os itens de dimensão estática são preferidos quando você deseja sempre analisar o mesmo item, sejam campanhas específicas ou dias específicos da semana.

Sempre que você selecionar e soltar manualmente valores de componentes específicos (dimensão, métrica, segmento, intervalo de datas) em uma tabela, o resultado será uma lista estática de linhas ou colunas. Os itens de dimensão estática também podem ser criados se você optar por:

* Em linhas, clique com o botão direito do mouse em > [!UICONTROL Exibir somente linhas selecionadas]
* Em colunas, clique com o botão direito do mouse em > [!UICONTROL Tornar o item estático]

Por exemplo, ao arrastar sobre itens específicos do Tipo de navegador, como Microsoft e Apple, esses 2 itens específicos sempre são puxados para a tabela.

Os itens de dimensão estática **não** têm a opção de filtro de linha. Em vez disso, os ícones de bloqueio e X estão presentes em cada item. Clique no ícone X para remover esse item de dimensão da tabela.

## Itens de dimensão mistos

Itens de dimensão de diferentes dimensões podem ser adicionados à mesma tabela. O cabeçalho da linha indica &quot;Dimensões mistas&quot; nesses casos. Esses itens de dimensão são estáticos. Por exemplo, adicionar itens de dimensão específicos da dimensão Tipo de navegador e outros itens de dimensão da dimensão Navegador.

## Total de linhas de forma livre

As linhas dinâmicas e estáticas se comportam de forma diferente na linha de total de forma livre. Por padrão:

* As linhas dinâmicas são somadas nas métricas do lado do servidor e de remoção de duplicados, como visitas ou visitantes
* As linhas estáticas são somadas do lado do cliente e **não** anulam as métricas de duplicado.

[Saiba mais sobre as opções de total](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) do Workspace para linhas dinâmicas e estáticas.
