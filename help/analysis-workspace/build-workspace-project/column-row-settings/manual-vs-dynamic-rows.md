---
title: Valores de dimensão dinâmicos vs estáticos
description: Como interagir com valores de dimensão dinâmicos e estáticos em tabelas.
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 8%

---


# Valores de dimensão dinâmicos vs estáticos em tabelas de forma livre

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Nas tabelas de forma livre, as linhas e colunas podem conter vários valores de componentes nelas. Esses valores podem ser dinâmicos (alterar com o tempo) ou estáticos (não mudar com o tempo), dependendo da análise que você deseja criar.

## Valores de dimensão dinâmicos

Os valores de dimensão dinâmica mudam com o tempo e dependem da métrica que está sendo classificada na tabela de forma livre. Os valores de dimensão dinâmica são preferenciais quando você deseja analisar os itens principais de um determinado período de tempo.

Quando você solta uma dimensão em uma tabela de forma livre, linhas dinâmicas são retornadas. Eles representam os itens principais que correspondem à dimensão de uma determinada métrica e período de tempo. Também é possível soltar uma dimensão em colunas de tabela de forma livre e a dimensão se expande automaticamente para os 5 valores de dimensão principais.

Por exemplo, quando você arrasta a dimensão Tipo de navegador para a tabela, os valores de dimensão Tipo de navegador principais (por exemplo, Microsoft, Apple, Google etc.) retornar dinamicamente às linhas da tabela. Se forem soltos em uma coluna, os 5 valores de dimensão Tipo de navegador principais retornarão dinamicamente.

Os valores de dimensão dinâmica têm a opção de filtro de linha e **não** têm ícones de bloqueio e X presentes.

## Valores de dimensão estática

Valores de dimensão estática não mudam com o tempo; são componentes fixos que são sempre retornados em uma tabela de forma livre. Os valores de dimensão estática são preferenciais quando você deseja sempre analisar o mesmo item, seja campanhas específicas ou dias específicos da semana.

Sempre que você selecionar e soltar manualmente valores de componentes específicos (dimensão, métrica, segmento, intervalo de datas) em uma tabela, o resultado será uma lista estática de linhas ou colunas. Valores de dimensão estática também podem ser criados se você optar por:

* Em linhas, clique com o botão direito do mouse em > [!UICONTROL Exibir somente linhas selecionadas]
* Em colunas, clique com o botão direito do mouse em > [!UICONTROL Tornar o item estático]

Por exemplo, ao arrastar sobre itens específicos do Tipo de navegador, como Microsoft e Apple, esses 2 itens específicos sempre são puxados para a tabela.

Valores de dimensão estática **não** têm a opção de filtro de linha. Em vez disso, os ícones de bloqueio e X estão presentes em cada item. Clique no ícone X para remover esse valor de dimensão da tabela.

## Valores de dimensão mistos

Valores de dimensão de diferentes dimensões podem ser adicionados à mesma tabela. O cabeçalho da linha indica &quot;Dimensões mistas&quot; nesses casos. Esses valores de dimensão são estáticos. Por exemplo, adicionar valores de dimensão específicos da dimensão Tipo de navegador e outros valores de dimensão da dimensão Navegador.

## Total de linhas de forma livre

As linhas dinâmicas e estáticas se comportam de forma diferente na linha de total de forma livre. Por padrão:

* As linhas dinâmicas são somadas nas métricas do lado do servidor e de remoção de duplicados, como visitas ou visitantes
* As linhas estáticas são somadas do lado do cliente e **não** anulam as métricas de duplicado.

[Saiba mais sobre as opções de total](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) do Workspace para linhas dinâmicas e estáticas.
