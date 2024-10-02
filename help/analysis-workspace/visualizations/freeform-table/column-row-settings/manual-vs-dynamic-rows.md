---
title: Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre
description: Como interagir com itens de dimensão dinâmicos e estáticos em tabelas
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 50%

---

# Itens de dimensão dinâmicos e estáticos em tabelas de forma livre

Nas tabelas de forma livre, as linhas e colunas podem conter vários valores de componentes. Esses valores podem ser dinâmicos (mudam com o tempo) ou estáticos (não mudam com o tempo), dependendo da análise que você deseja criar.

## Itens de dimensão dinâmicos

Os itens de dimensão dinâmicos mudam com o tempo e dependem da métrica que está sendo classificada na tabela de forma livre. Os itens de dimensão dinâmicos são usados quando você deseja analisar os itens principais de um determinado período.

Ao soltar uma dimensão em uma tabela de forma livre, linhas dinâmicas são retornadas. As linhas dinâmicas representam os itens principais que correspondem à dimensão de uma determinada métrica e período. Também é possível soltar uma dimensão em colunas de tabela de forma livre. A dimensão se expande automaticamente para os 5 itens de dimensão principais.

Por exemplo, ao arrastar a dimensão Tipo de navegador para a tabela, os principais itens de dimensão Tipo de navegador (por exemplo, Microsoft, Apple, Google etc.) retornam dinamicamente às linhas da tabela. Se forem soltos em uma coluna, os 5 principais itens de dimensão Tipo de navegador retornarão dinamicamente.

Os itens de dimensão dinâmicos têm a opção de filtro de linha ![Filtro](/help/assets/icons/Filter.svg) e um ![Fechamento](/help/assets/icons/Close.svg), e **não** têm um bloqueio ![BloqueioFechado](/help/assets/icons/LockClosed.svg) presente. <!--do they have the lock icon? --> Ao clicar em ![Fechar](/help/assets/icons/Close.svg) ao lado de um item de dimensão dinâmico, um filtro é aplicado automaticamente. Para obter mais informações sobre como aplicar filtros a tabelas, consulte [Filtro e tabelas de classificação](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Uma Tabela de Forma Livre que destaca o ícone de filtro.](assets/dynamic-items.png)

## Itens de dimensão estáticos

Os itens de dimensão estáticos não mudam com o tempo; são componentes fixos que são sempre retornados em uma tabela de forma livre. Os itens de dimensão estáticos são usados quando você deseja sempre analisar o mesmo item, sejam campanhas específicas ou dias específicos da semana.

Sempre que você selecionar e soltar manualmente valores de componentes específicos (dimensão, métrica, filtro, intervalo de datas) em uma tabela, o resultado será uma lista estática de linhas ou colunas.

Por exemplo, ao arrastar sobre itens específicos Tipo de navegador, como Microsoft e Apple, esses 2 itens específicos sempre são puxados para a tabela.

Itens de dimensão estáticos também podem ser criados se você optar por selecionar **[!UICONTROL Exibir somente linhas selecionadas]** no menu de contexto para linhas selecionadas.

Os itens de dimensão estáticos **não** têm a opção de filtro de linha. Em vez disso, um ![LockClosed](/help/assets/icons/LockClosed.svg) e ![Close](/help/assets/icons/Close.svg) estão presentes em cada item. Selecione ![Fechar](/help/assets/icons/Close.svg) para remover esse item de dimensão da tabela.

![Uma Tabela de Forma Livre mostrando o Tipo de Navegador e a linha Microsoft com um ícone de bloqueio observação: Este item de dimensão é estático e não será alterado com o tempo.](assets/static-items.png)

## Itens de dimensão mistos

Itens de dimensão de diferentes dimensões podem ser adicionados à mesma tabela. O cabeçalho da linha diz **[!UICONTROL Dimension]** misto nestes casos. Esses itens de dimensão são estáticos. Por exemplo, adicionar itens de dimensão específicos da dimensão Grupo de navegadores e outros itens de dimensão da dimensão Nome do navegador.

![Uma Tabela de Forma Livre que destaca a coluna Dimension mista.](assets/mixed-dimensions.png)

## Total de linhas de forma livre

As linhas dinâmicas e estáticas se comportam de maneira diferente na linha total de forma livre. Por padrão:

* As linhas dinâmicas são somadas no lado do servidor e deduplicam métricas como sessões ou pessoas.
* As linhas estáticas são somadas no lado do cliente e **não** deduplicam as métricas. Para calcular o total de linhas do lado do servidor, altere a configuração de linha para **Mostrar total geral**. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=pt-BR)
