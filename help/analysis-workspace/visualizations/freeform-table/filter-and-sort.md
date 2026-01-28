---
description: Saiba como filtrar e classificar tabelas de forma livre no Analysis Workspace.
title: Filtrar e Classificar
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 46%

---

# Filtrar e classificar tabelas de forma livre

As tabelas de forma livre do Analysis Workspace são a base para a análise interativa de dados. Sendo assim, elas podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser essencial para encontrar as informações mais importantes de maneira eficiente.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrar tabelas

Os filtros do Analysis Workspace ajudam você a encontrar as informações mais importantes.

>[!NOTE]
>
> Somente itens de dimensão dinâmicos podem ser filtrados conforme descrito nesta seção. Itens de dimensão estáticos não podem ser filtrados. Para obter mais informações, consulte [Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Você pode usar vários métodos para filtrar linhas de uma tabela de forma livre.

* Excluir linhas específicas de uma tabela
* Aplicar filtros a uma tabela
* Usar segmentos de público-alvo

Leia como cada método afeta [os totais das tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Excluir linhas específicas de uma tabela

Você pode excluir rapidamente linhas específicas da tabela sem a necessidade de usar o ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**.

>[!NOTE]
>
>Ao excluir linhas conforme descrito nesta seção, uma regra [!UICONTROL Sempre excluir itens] é adicionada automaticamente na caixa de diálogo de filtro [!UICONTROL Avançado]. Você pode exibir a regra aplicada selecionando o ícone Filtro ![Filtro](/help/assets/icons/Filter.svg) e Avançado [**[!UICONTROL Mostrar avançado]**](#apply-a-simple-or-advanced-filter-to-a-table).

Para excluir linhas específicas de uma tabela de forma livre:

1. Passe o mouse sobre a linha que deseja excluir e selecione ![Fechar](/help/assets/icons/Close.svg).

   Mantenha pressionada a tecla ***Shift*** para selecionar um intervalo de linhas, ou mantenha pressionada a tecla ***Command*** (no Mac) ou a tecla ***Ctrl*** (no Windows) para selecionar várias linhas.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Aplicar filtragem simples ou avançada a uma tabela

Para filtrar dados em tabelas de forma livre:

1. Passe o mouse sobre a coluna que contém os dados que você deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Clique em ![Filtro](/help/assets/icons/Filter.svg) **Filtro** quando ele aparecer.

   ![Tabela de forma livre destacando o ícone Filtro.](assets/table-filter-icon.png)

   As seguintes opções estão disponíveis na caixa de diálogo **[!UICONTROL Pesquisar]**:

   ![Filtro simples](assets/filter-simple.png){width="500"}

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir “Nenhum valor”**] | Selecione esta opção para mostrar uma linha **[!UICONTROL Nenhum valor]** na tabela para dados que não têm valor para a dimensão selecionada. Desmarque esta opção para ocultar as **[!UICONTROL Linhas sem valor]**.<!-- Add at multi dim GA: When tables include multiple dimension columns, you can deselect this option to show data only when it applies to each dimension column in the table.--> |
   | [!UICONTROL **Pesquisar palavra ou frase**] | Especifique uma palavra ou frase pela qual deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas. |


1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As seguintes opções de filtro avançado estão disponíveis:

   ![Filtro simples](assets/filter-advanced.png){width=500}

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir “Nenhum valor”**] | Selecione esta opção para mostrar uma linha **[!UICONTROL Nenhum valor]** na tabela para dados que não têm valor para a dimensão selecionada. Desmarque esta opção para ocultar a linha **[!UICONTROL Nenhum valor]**. |
   | [!UICONTROL **Corresponder**] | Selecione [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.<br/><br/>Escolha [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendem a qualquer um dos critérios de filtro que você especificou. Essa opção normalmente resulta em dados menos refinados. |
   | [!UICONTROL **Critérios**] | Selecione dentre as seguintes opções de filtro:<br/><ul><li>[!UICONTROL **Contém a frase**] (padrão): somente dados que contêm a frase exata que você especificar serão incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Contém qualquer termo**]: somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Contém todos os termos**]: somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Não contém nenhum termo**]: somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Não contém a frase**]: somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Igual**]: somente os dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Não é igual**]: somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Começa com**]: somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Termina com**]: somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </li></ul>Selecione ![Adicionar](/help/assets/icons/Add.svg) [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada para [!UICONTROL **Corresponder**] determina **[!UICONTROL Se todos os critérios são atendidos]** ou **[!UICONTROL Se algum critério é atendido]**. |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecione **[!UICONTROL Aplicar]** para filtrar os dados. Selecione **[!UICONTROL Limpar]** para limpar todos os campos de entrada. Selecione **[!UICONTROL Cancelar]** para cancelar e fechar a caixa de diálogo. <br/>Um ícone colorido de ![Filtro](/help/assets/icons/FilterColored.svg) **Filtro** indica e exibe detalhes quando um filtro é aplicado à tabela.

### Incluir critérios de filtro em dados de tendências em gráficos de sparkline e visualizações de linha {#include-filter-criteria}

Todos os critérios de filtro de pesquisa aplicados à dimensão da tabela para uma tabela de forma livre são sempre incluídos em minigráficos.

Além dos minigráficos, você pode configurar critérios de filtro para serem incluídos em visualizações de linha conectada. (Por padrão, os critérios de filtro não estão incluídos nas visualizações de linha. As visualizações de linha exibem dados para a linha selecionada na tabela conectada. Se nenhuma linha for selecionada, os dados somente para a primeira dimensão da tabela conectada serão mostrados.)

Para obter mais informações sobre minigráficos e visualizações de linha, consulte [Exibir dados de tendência para uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Configurar visualizações de linha para incluir critérios de filtro

1. Selecione o minigráfico no cabeçalho da coluna de métrica.

   Quando a célula do minigráfico é selecionada, ela é exibida em cinza escuro. Isso indica que os critérios de filtro estão incluídos na visualização de linha conectada. Os critérios de filtro são aplicados como um segmento na coluna. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![minigráfico selecionado](assets/table-sparkline-selected.png)

#### Entender quando os totais da coluna podem ser imprecisos

Os totais da coluna podem não ser exatos nos seguintes cenários:

* Quando componentes estáticos são usados na coluna à esquerda e os totais da [coluna são calculados como uma soma das linhas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  Se os itens de linha contiverem dados sobrepostos nesse cenário, os totais da coluna serão imprecisos.

  Por exemplo, se você adicionar segmentos estáticos à coluna esquerda e, em seguida, adicionar Usuários como uma métrica na coluna direita, alguns desses usuários podem fazer parte de mais de um dos segmentos estáticos. Nesse caso, a Workspace não desduplica os usuários para cada segmento estático. Isso pode resultar em um número maior de usuários totais, pois alguns usuários podem ser contados mais de uma vez.

* Ao usar dimensões de vários valores

>[!NOTE]
>
>O gráfico de minigráficos e de linhas ainda reflete os totais precisos nesses cenários.

### Usar segmentos de público-alvo

Consulte [Visão geral da segmentação](/help/components/segments/seg-overview.md) para obter mais detalhes.

## Classificar tabelas

No Analysis Workspace, você pode classificar os dados de uma tabela de forma livre por qualquer coluna, sejam dimensões ou métricas. Você pode até mesmo classificar por várias colunas ao mesmo tempo.

Por padrão, as dimensões são classificadas em ordem crescente e as métricas são classificadas em ordem decrescente.

### Classificar tabelas por uma única coluna

Ao classificar os dados de uma única coluna conforme descrito nesta seção, qualquer [classificação avançada](#sort-tables-by-multiple-columns-advanced-sorting) aplicada à tabela é removida.

Para classificar dados em tabelas por uma única coluna:

1. Passe o mouse sobre o cabeçalho da coluna que você deseja classificar, em seguida, selecione o ícone **Classificar** ![Classificar](/help/assets/icons/SortOrderDown.svg) quando ele aparecer.

   ![Menu suspenso Classificar](assets/sort-dropdown-menu.png)

1. Selecione **[!UICONTROL Crescente]** ou **[!UICONTROL Decrescente]**.

   O ícone de classificação permanece visível quando a classificação é aplicada à coluna. Uma seta indica como os dados são classificados (![Classificar](/help/assets/icons/SortOrderUp.svg) para crescente ou ![Classificar](/help/assets/icons/SortOrderDown.svg) para decrescente).

### Classificar tabelas por várias colunas (Classificação avançada)

{{release-limited-testing-section}}

#### Aplicar classificação a várias colunas

Para classificar dados em tabelas por várias colunas:

1. Passe o mouse sobre o cabeçalho de qualquer coluna que você deseja classificar, em seguida, selecione o ícone **Classificar** ![Classificar](/help/assets/icons/SortOrderDown.svg) quando ele aparecer.

   ![Menu suspenso Classificar](assets/sort-dropdown-menu.png)

1. Selecione **[!UICONTROL Classificação avançada]**.

   ![Caixa de diálogo de classificação avançada](assets/sort-advanced-dialog.png)

1. Na caixa de diálogo Classificação avançada, siga um destes procedimentos:

   * Adicione colunas que ainda não estão sendo classificadas selecionando o botão **[!UICONTROL Adicionar coluna de classificação]**.

   * Remova as colunas que você não deseja mais classificar selecionando o ícone **Remover** ![Remover](/help/assets/icons/Close.svg).

   * Arraste as colunas para cima ou para baixo na lista para ajustar a prioridade de classificação.

     Para obter mais informações, consulte [Prioridade de classificação](#sort-priority).

   * Altere o valor de classificação, selecionando **[!UICONTROL Crescente]** ou **[!UICONTROL Decrescente]** no menu suspenso.

   * Selecione uma coluna diferente selecionando o menu drop-down nome da coluna.

1. Selecione **[!UICONTROL Aplicar]**.

O ícone de classificação permanece visível quando a classificação é aplicada a uma coluna. Uma seta indica como os dados são classificados (![Classificar](/help/assets/icons/SortOrderUp.svg) para crescente ou ![Classificar](/help/assets/icons/SortOrderDown.svg) para decrescente).

![exemplo de multiclassificação](assets/dimensions-multiple-sort.png)

#### Prioridade de classificação

Quando você classifica dados para várias colunas, os dados são classificados de acordo com a prioridade atribuída a cada coluna. A numeração de prioridade é exibida ao lado do ícone de classificação ![SortOrderDown](/help/assets/icons/SortOrderDown.svg)<sup>➊</sup>.

A coluna com a prioridade primária decide a ordem principal; a coluna com a prioridade secundária decide a ordem quando as linhas têm o mesmo valor na coluna primária; a coluna com a prioridade terciária decide a ordem quando as linhas têm o mesmo valor nas colunas primária e secundária; e assim por diante.

Por exemplo, considere uma tabela com as seguintes colunas:

* Dia do mês (dimensão)

* Hora do dia (dimensão)

* Eventos (métrica)

Você pode atribuir uma prioridade de classificação a cada coluna, da seguinte maneira:

| Nome da coluna (componente) | Tipo de componente | Prioridade de classificação |
|---------|----------|---------|
| Dia do mês | Dimensão | 1 |
| Hora do dia | Dimensão | 2 |
| Eventos | Métrica | 3 |

Ao atribuir uma prioridade de classificação a cada coluna, é possível controlar exatamente como os dados são exibidos na tabela. Neste exemplo, as informações são classificadas primeiro por Dia do mês, em seguida por Hora do dia e finalmente por Eventos.

![exemplo de multiclassificação](assets/dimensions-multiple-sort.png)
