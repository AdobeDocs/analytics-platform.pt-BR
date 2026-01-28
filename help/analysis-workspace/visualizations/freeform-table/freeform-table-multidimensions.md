---
title: Incluir várias dimensões em uma tabela de forma livre
description: Saiba como incluir várias dimensões em uma tabela de forma livre
feature: Visualizations
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# Incluir várias colunas de dimensão em uma tabela de forma livre

{{release-limited-testing}}

É possível incluir até 5 colunas de dimensão em uma tabela de forma livre, permitindo visualizar vários itens de dimensão lado a lado. Cada linha de itens de dimensão se comporta como um único item de dimensão concatenado.

Aplique filtros, classificações, detalhamentos e muito mais a tabelas de forma livre com várias colunas de dimensão para criar uma análise mais profunda e personalizada.

## Itens de dimensão concatenados

Quando você [adiciona várias colunas de dimensão a uma tabela de forma livre](#add-multiple-dimension-columns), cada linha de itens de dimensão se comporta como um único item de dimensão concatenado. Essa funcionalidade permite visualizar dados de métrica para combinações específicas de dimensões.

Por exemplo, considere uma tabela de forma livre onde as colunas da dimensão são _Cidade_, _Tipo de Dispositivo_ e _Dia do Mês_ e a métrica é _Eventos_. Os três itens de dimensão na primeira linha desta tabela se tornam um único item de dimensão concatenado mostrando que houve 2.056 eventos que ocorreram em Mumbai a partir de telefones celulares no 30º dia do mês.

| Dimension: cidade | Dimension: Tipo de dispositivo | Dimension: Dia do mês | Métrica: Eventos |
|---------|----------|---------|---------|
| Mumbai | Celular | 30 | 2.056 |
| Nova York | Tablet | 31 | 1.761 |
| Bangalore | Área de trabalho | 1 | 1.666 |
| Délhi | Celular | 14 | 1.396 |

A seguir, veja como essa tabela aparece no Analysis Workspace:

![Exemplo de multidimensão](assets/multi-dim-example.png)

## Adicionar várias colunas de dimensão

É possível adicionar várias colunas de dimensão, uma de cada vez ou em massa.

1. No Analysis Workspace, crie uma tabela de forma livre.

   Para obter mais informações, consulte [Adicionar visualizações a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) em [Visão geral das visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Adicionar dimensões à tabela de forma livre. É possível adicionar dimensões uma de cada vez ou adicionar várias dimensões de uma vez.

   * Arraste as dimensões, uma de cada vez, para a tabela de forma livre. Coloque colunas de dimensão adicionais à esquerda ou à direita de colunas de dimensão existentes na tabela. Uma linha azul vertical **[!UICONTROL Adicionar]** é exibida onde a nova coluna será criada.

     ![Arrastar dimensões individuais](assets/dimensions-add-individually.png)

   * Selecione até 5 dimensões no menu do componente e arraste-as para a tabela de forma livre. As dimensões são adicionadas à tabela da esquerda para a direita na ordem em que são selecionadas.

     Para selecionar várias dimensões, mantenha pressionada a tecla ***Command*** (no Mac) ou a tecla ***Ctrl*** (no Windows).

     ![Arrastar várias dimensões](assets/dimensions-add-multiple.png)

1. Exibir cada linha da tabela como um único item de dimensão. Para obter mais informações, consulte [Itens de dimensão concatenados](#concatenated-dimension-items).

## Filtrar e classificar tabelas

É possível aplicar filtragem e classificação às colunas em uma tabela de forma livre. Você pode classificar os dados de uma tabela de forma livre por qualquer coluna, sejam dimensões ou métricas. Você pode até mesmo classificar por várias colunas ao mesmo tempo.

Para obter informações, consulte [Filtrar e classificar tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Várias colunas e detalhamentos de dimensão

O Analysis Workspace fornece as seguintes maneiras de adicionar várias dimensões em uma tabela de forma livre:

* Incluir várias colunas de dimensão (conforme descrito neste artigo)

* [Adicionar detalhamentos](/help/components/dimensions/t-breakdown-fa.md)

Ambos os métodos permitem analisar dimensões em relação a outras dimensões. No entanto, há diferenças importantes e ambos os métodos podem ser usados na mesma tabela para uma análise ainda mais profunda.

### Diferenças entre colunas de dimensão e detalhamentos

Várias colunas de dimensão permitem:

* Concatene itens de dimensão em linhas distintas de dados em várias dimensões.

* Inclua itens de dimensão em linhas concatenadas somente quando os itens de dimensão se aplicarem a cada coluna de dimensão na tabela. Para fazer isso, use o filtro de coluna para desmarcar a configuração **[!UICONTROL Incluir &quot;Nenhum valor&quot;]** em cada coluna de dimensão.

  Para obter mais informações, consulte [Classificar tabelas por várias colunas (Classificação avançada)](#sort-tables-by-multiple-columns-advanced-sorting).

* Classifique dados por várias colunas de dimensão e métrica para ver dados mais personalizados.

  Para obter mais informações, consulte [Classificar tabelas por várias colunas (Classificação avançada)](#sort-tables-by-multiple-columns-advanced-sorting)

Os detalhamentos permitem:

* Detalhar um item de dimensão na tabela de forma livre por uma dimensão secundária. É possível exibir até 400 itens de dimensão para a dimensão secundária.

### Adicionar detalhamentos a uma tabela com várias colunas de dimensão

Quando você adiciona um detalhamento a uma tabela que tem várias colunas de dimensão, o detalhamento se aplica ao item de dimensão concatenado (em todas as colunas de dimensão) na linha em que você o adiciona.

![exemplo de detalhamento de várias classificações](assets/dimensions-multiple-sort-breakdown.png)

Além disso, é possível adicionar várias colunas de dimensão em um detalhamento. Cada linha de itens de dimensão no detalhamento também se comporta como um único item de dimensão concatenado.

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

Para obter mais informações sobre como adicionar um detalhamento, consulte [Detalhar dimensões](/help/components/dimensions/t-breakdown-fa.md).

## Crie um segmento com base em um item de dimensão que abrange várias colunas de dimensão

Quando você cria um segmento com base em um item de dimensão que abrange várias colunas de dimensão, cada item de dimensão é incluído na definição do segmento, com operadores And unindo-os.

Para obter informações sobre como criar um segmento, consulte [Criar segmentos](/help/components/segments/seg-create.md).

## Dimensões não suportadas {#unsupported}

As combinações de dimensão a seguir não são compatíveis, e o Analysis Workspace proíbe que elas sejam adicionadas ou mostra uma mensagem de erro após serem adicionadas:

* Várias dimensões que são de campos que fazem referência a diferentes [matrizes de objetos](/help/use-cases/object-arrays.md) usadas juntas na mesma tabela de forma livre.

  Várias dimensões são permitidas juntas na mesma tabela de forma livre se referenciarem a mesma matriz de objetos.

