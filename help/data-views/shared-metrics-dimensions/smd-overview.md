---
title: Visão geral de métricas e dimensões compartilhadas
description: Use a mesma dimensão ou referência de métrica em várias visualizações de dados.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
source-git-commit: 1de8b8f40a7e1be0de0e6cbed5cc57ff834f2377
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# Visão geral de métricas e dimensões compartilhadas

As métricas e dimensões compartilhadas fornecem um local central para gerenciar dimensões e métricas que podem ser usadas em qualquer número de visualizações de dados. Esses componentes são especialmente valiosos para organizações que usam várias visualizações de dados, especialmente se essas visualizações de dados compartilharem configurações de componentes comuns. As alterações feitas em métricas e dimensões compartilhadas se aplicam instantaneamente a todas as visualizações de dados às quais são compartilhadas. Ao editar uma visualização de dados individual, as dimensões e métricas compartilhadas podem ser identificadas por um ícone ![Componente compartilhado](/help/assets/icons/CCLibrary.svg) ao lado do nome do componente.

Embora dimensões e métricas compartilhadas permitam que componentes comuns sejam usados em muitas visualizações de dados, elas não podem ser compartilhadas em conexões.

## Fluxo de trabalho

A maioria das organizações usa o seguinte fluxo de trabalho abrangente para desduplicar e manter dimensões e métricas ao longo do tempo:

1. Importe componentes de cada visualização de dados que pode ser compartilhada entre várias visualizações de dados. Se a mesma dimensão ou métrica existir em várias visualizações de dados, a Adobe recomenda importar todas as instâncias desse componente. Embora essa prática recomendada importe duplicatas, elas são importadas para que possam ser desduplicadas e manter suas respectivas referências a projetos do Workspace.
1. Revise todos os componentes que usam a mesma ID de componente, mas têm configurações de componente diferentes. Para cada grupo de componentes duplicados, selecione as configurações de componente desejadas a serem aplicadas a todos os outros componentes que compartilham essa ID de componente.
1. Revise todos os componentes que usam a mesma ID de componente e também têm as mesmas configurações de componente. Essas dimensões ou métricas podem ser mescladas com facilidade e segurança.

## Gerenciador de [!UICONTROL Métricas e dimensões compartilhadas]

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Visualizações de dados]** > **[!UICONTROL Métricas e dimensões compartilhadas]**

Navegar até essa interface mostra todas as dimensões e métricas atuais disponíveis para compartilhamento em várias visualizações de dados. A parte superior direita contém dois botões para adicionar componentes a essa interface:

* **[!UICONTROL Importar]**: abre uma janela modal que permite selecionar uma visualização de dados e, em seguida, selecionar os componentes a serem disponibilizados para compartilhamento.
* **[!UICONTROL Criar novo]**: abre o [editor de componentes compartilhados](shared-component-editor.md).

Logo abaixo desses dois botões, quatro cartões de visão geral estão visíveis:

![Visualização dos cartões de visão geral](assets/overview-cards.png)

* **Métricas**: o número total de métricas disponíveis para compartilhar entre visualizações de dados para esta conexão. Cada conexão pode conter até 10.000 métricas compartilhadas.
* **Dimensões**: o número total de dimensões disponíveis para compartilhar entre visualizações de dados para esta conexão. Cada conexão pode conter até 10.000 dimensões compartilhadas.
* **Componentes duplicados para revisão**: ao importar componentes entre várias exibições de dados, algumas dimensões ou métricas podem compartilhar a mesma ID de componente. O número neste cartão de visão geral mostra o número total de componentes que têm a mesma ID de componente, mas configurações de componente diferentes. Selecionar **[!UICONTROL Revisão]** habilita um filtro que permite selecionar o componente desejado para agir como uma fonte da verdade para todos os outros componentes com a mesma ID.
* **Componentes disponíveis para mesclagem**: se uma dimensão ou métrica compartilha a mesma ID de componente e as mesmas configurações de componente, eles são efetivamente idênticos e estão prontos para desduplicar. Selecionar **[!UICONTROL Revisão]** habilita um filtro que permite mesclar todos os componentes com a mesma ID de componente em uma única dimensão ou métrica compartilhada.

Todas as dimensões e métricas compartilhadas são exibidas abaixo dos quatro cartões de visão geral.

![Visualização de dimensões e métricas disponíveis](assets/shared-metrics-dimensions.png)

* **Filtro**: selecione o ícone ![Filtrar](../../assets/icons/Filter.svg) para mostrar ou ocultar os filtros disponíveis. Os seguintes filtros estão disponíveis:
   * **[!UICONTROL Tipo de componente]**: exibir somente dimensões ou métricas.
   * **[!UICONTROL Conjunto de Dados]**: exibir somente componentes nos quais o conjunto de dados esteja incluído nas visualizações de dados nas quais um componente está compartilhado.
   * **[!UICONTROL Visualização de dados]**: visualizar somente componentes compartilhados com essa visualização de dados.
   * **[!UICONTROL Criado por]**: exibir somente componentes criados por um determinado usuário.
   * **[!UICONTROL Duplicatas]**: exibir somente componentes que tenham a mesma identificação de componente que outro componente. Esses filtros são idênticos à revisão de componentes por meio dos cartões de visão geral.
* **Pesquisa**: use o ícone ![Pesquisar](../../assets/icons/Search.svg) para procurar um componente por nome.
* **[!UICONTROL Conexão]**: um menu suspenso que altera a [conexão](/help/connections/overview.md). As dimensões e métricas compartilhadas são sempre específicas para uma única conexão.
* **[!UICONTROL Personalizar tabela]**: selecione o ícone ![Personalizar tabela](/help/assets/icons/ColumnSetting.svg) para mostrar ou ocultar colunas na tabela. As opções disponíveis incluem:
   * **[!UICONTROL Nome do campo]**: o nome da dimensão ou métrica compartilhada. Este campo está sempre visível.
   * **[!UICONTROL Tipo]**: indica se o componente é uma dimensão ou uma métrica. Este campo está sempre visível.
   * **[!UICONTROL Tipo de conjunto de dados]**: o tipo de conjunto de dados. A maioria dos conjuntos de dados é de eventos.
   * **[!UICONTROL Compartilhado para visualização de dados]**: todas as visualizações de dados nas quais este componente é compartilhado. Este campo está sempre visível. Selecione o link para abrir uma modal que lista todas as visualizações de dados nas quais esse componente está disponível.
   * **[!UICONTROL Conjuntos de dados]**: todos os conjuntos de dados incluídos em cada visualização de dados à qual este componente é compartilhado. Selecione o link para abrir uma modal que lista todos os conjuntos de dados do componente.
   * **[!UICONTROL Criado por]**: o nome da pessoa que criou ou importou o componente para a interface de métricas e dimensões compartilhadas.
   * **[!UICONTROL Tipo de esquema]**: o formato em que os dados são armazenados. Os exemplos incluem `string`, `double` ou `boolean`.
   * **[!UICONTROL ID do Componente]**: a ID do componente da dimensão ou métrica. Todos os componentes que compartilham a mesma ID de componente nessa interface devem ser revisados e desduplicados.
   * **[!UICONTROL Esquema]**: o caminho do esquema para a dimensão ou métrica. Por exemplo, `web.webPageDetails.URL`.
   * **[!UICONTROL Descrição]**: a [descrição](/help/data-views/component-settings/overview.md) do componente.
   * **[!UICONTROL Rótulos de contexto]**: os [rótulos de contexto](/help/data-views/component-settings/overview.md) do componente.
   * **[!UICONTROL Incluir/Excluir valores]**: lista o número de regras conforme especificado em [Incluir/excluir valores](/help/data-views/component-settings/include-exclude-values.md).
   * **[!UICONTROL Rótulos de uso de dados]**: os [rótulos de uso de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview) para o campo de esquema.
   * **[!UICONTROL Obsoleto]**: indica se o sinalizador obsoleto está definido.
   * **[!UICONTROL Formato]**: o formato em que os valores aparecem. Os booleanos normalmente aparecem como `True | False`, as métricas normalmente aparecem como `Decimal`, etc.
   * **[!UICONTROL Desduplicação de métrica]**: as configurações de [Desduplicação de métrica](/help/data-views/component-settings/metric-deduplication.md) do componente.
   * **[!UICONTROL Comportamento]**: as configurações [Comportamento](/help/data-views/component-settings/behavior.md) do componente.
   * **[!UICONTROL Atribuição]**: as configurações de [Atribuição](/help/data-views/component-settings/attribution.md) do componente.
   * **[!UICONTROL Nenhuma opção de valor]**: as [Nenhuma opção de valor](/help/data-views/component-settings/no-value-options.md) do componente.
   * **[!UICONTROL Classificação de valor]**: as configurações de [Classificação de valor](/help/data-views/component-settings/value-bucketing.md) do componente.
   * **[!UICONTROL Persistence]**: as configurações [Persistence](/help/data-views/component-settings/persistence.md) do componente.
   * **[!UICONTROL Minúsculas]**: indica se o componente está habilitado para minúsculas com base nas configurações [Comportamento](/help/data-views/component-settings/behavior.md) do componente.
   * **[!UICONTROL Substring]**: as configurações de [Substring](/help/data-views/component-settings/substring.md) do componente.
   * **[!UICONTROL Grupo de dados de resumo]**: as configurações do [grupo de dados de resumo](/help/data-views/component-settings/summary-data-group.md) do componente.
   * **[!UICONTROL Data de criação]**: a data de criação ou de importação do componente.
   * **[!UICONTROL Última modificação]**: se o componente foi modificado depois de ter sido criado, a data em que foi modificado pela última vez.
* **[!UICONTROL Histórico de trabalhos]**: se você importar ou compartilhar um grande número de componentes, um trabalho será criado automaticamente. Selecione o ícone ![Histórico](/help/assets/icons/History.svg) para abrir uma janela modal que mostre todas as instâncias de importação de dimensões e métricas de visualizações de dados individuais. Se nenhuma das ações de importação ou compartilhamento for grande o suficiente para acionar um trabalho, esse botão não aparecerá.

## Editar componentes ou compartilhar componentes em visualizações de dados

Use a caixa de seleção ao lado de um componente para revelar todas as ações disponíveis que você pode realizar. Várias seleções são aceitas.

![Visualização das ações disponíveis](assets/smd-actions.png)

* ![Ícone de lápis](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**: abra as dimensões e métricas selecionadas no [editor de componentes compartilhados](shared-component-editor.md), que permite ajustar suas [configurações de componentes](/help/data-views/component-settings/overview.md). Quando você seleciona vários componentes para editar, todos eles são abertos no editor de componentes. Você pode deslocar os componentes com o botão + clique no editor de componentes para editar o mesmo campo para vários componentes.
* ![Ícone Compartilhar](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartilhar no(s) modo(s) de exibição de dados]**: abre uma janela que mostra todos os modos de exibição de dados disponíveis na conexão selecionada. Marque a caixa de seleção para cada visualização de dados na qual você deseja disponibilizar este componente e selecione **[!UICONTROL Compartilhar]**.
* ![Ícone Cancelar compartilhamento](/help/assets/icons/SaveTo.svg) **[!UICONTROL Cancelar compartilhamento das visualizações de dados]**: abre uma janela que mostra todas as visualizações de dados com as quais este componente está compartilhado no momento. Marque a caixa de seleção para cada exibição de dados da qual você deseja remover a disponibilidade deste componente e selecione **[!UICONTROL Cancelar compartilhamento]**.
* ![Ícone de duplicado](/help/assets/icons/Copy.svg) **[!UICONTROL Duplicado]**: cria uma cópia dos componentes selecionados. Uma nova ID de componente é gerada para componentes duplicados.
* ![Ícone Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]**: remove os componentes selecionados da interface. Se os componentes selecionados forem compartilhados com qualquer visualização de dados, eles não serão compartilhados.
