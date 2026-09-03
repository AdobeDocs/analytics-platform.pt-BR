---
title: Itens Dinâmicos E Estáticos Do Dimension
description: Saiba como usar itens de dimensão dinâmicos versus estáticos em tabelas de forma livre no Analysis Workspace.
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
TQID: https://experienceleague.adobe.com/q9X-MNr4r3Xrs16gAgH6-F3yrRDJP73xfXdd8BcFg84
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 77%

---

# Itens de dimensão dinâmicos e estáticos

Nas tabelas de forma livre, as linhas e colunas podem conter vários valores de componentes. Esses valores podem ser dinâmicos (mudam com o tempo) ou estáticos (não mudam com o tempo), dependendo da análise que você deseja criar.

## Itens de dimensão dinâmicos

Os itens de dimensão dinâmicos mudam com o tempo e dependem da métrica que está sendo classificada na tabela de forma livre. Os itens de dimensão dinâmicos são usados quando você deseja analisar os itens principais de um determinado período.

Ao soltar uma dimensão em uma tabela de forma livre, linhas dinâmicas são retornadas. As linhas dinâmicas representam os principais itens correspondentes à dimensão de uma determinada métrica e período. Também é possível soltar uma dimensão em colunas de tabela de forma livre. A dimensão se expande automaticamente para os 5 itens de dimensão principais.

Por exemplo, ao arrastar a dimensão Tipo de navegador para a tabela, os principais itens de dimensão Tipo de navegador (por exemplo, Microsoft, Apple, Google etc.) retornam dinamicamente às linhas da tabela. Se forem soltos em uma coluna, os 5 principais itens da dimensão Tipo de navegador retornarão dinamicamente.

Os itens de dimensão dinâmicos têm a opção de filtro de linha ![Filtro](/help/assets/icons/Filter.svg) e um ![Fechamento](/help/assets/icons/Close.svg), e **não** têm um bloqueio ![BloqueioFechado](/help/assets/icons/LockClosed.svg) presente. <!--do they have the lock icon? --> Ao clicar em ![Fechar](/help/assets/icons/Close.svg) ao lado de um item de dimensão dinâmico, um filtro é aplicado automaticamente. Para obter mais informações sobre como aplicar filtros a tabelas, consulte [Filtrar e classificar tabelas](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Uma tabela de forma livre com destaque para o ícone de filtro.](assets/dynamic-items.png)

## Itens de dimensão estáticos

Os itens de dimensão estáticos não mudam com o tempo; são componentes fixos que são sempre retornados em uma tabela de forma livre. Os itens de dimensão estáticos são usados quando você deseja sempre analisar o mesmo item, sejam campanhas específicas ou dias específicos da semana.

Sempre que você selecionar e soltar manualmente valores de componentes específicos (dimensão, métrica, segmento, intervalo de datas) em uma tabela, o resultado será uma lista estática de linhas ou colunas.

Por exemplo, ao arrastar sobre itens específicos de Tipo de navegador, como Microsoft e Apple, esses 2 itens específicos sempre são puxados para a tabela.

Também é possível criar itens de dimensão estáticos por selecionar a opção **[!UICONTROL Exibir somente linhas selecionadas]** no menu de contexto das linhas selecionadas.

Os itens de dimensão estáticos **não** têm a opção de filtro para linhas. Em vez disso, um ![LockClosed](/help/assets/icons/LockClosed.svg) e ![Fechar](/help/assets/icons/Close.svg) estão presentes em cada item. Selecione ![Fechar](/help/assets/icons/Close.svg) para remover esse item de dimensão da tabela.

![Uma tabela de forma livre exibindo o Tipo de navegador e a linha Microsoft com uma observação sobre o ícone de bloqueio: este item de dimensão é estático e não será alterado com o tempo.](assets/static-items.png)

## Itens de dimensão mistos

Itens de dimensão de diferentes dimensões podem ser adicionados à mesma tabela. Nesses casos, o cabeçalho da linha indica **[!UICONTROL Dimensões mistas]**. Esses itens de dimensão são estáticos. Por exemplo, adicionar itens específicos da dimensão Grupo do navegador e outros itens da dimensão Nome do navegador.

![Uma tabela de forma livre com destaque para a coluna Dimensões mistas.](assets/mixed-dimensions.png)

## Total de linhas de forma livre

As linhas dinâmicas e estáticas se comportam de maneira diferente na linha total de forma livre. Por padrão:

* As linhas dinâmicas são somadas no lado do servidor e removem a duplicação de métricas, como sessões ou pessoas.
* As linhas estáticas são somadas no lado do cliente e **não** deduplicam as métricas. Para calcular o total de linhas do lado do servidor, altere a configuração de linha para **Mostrar total geral**. [Saiba mais](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)
