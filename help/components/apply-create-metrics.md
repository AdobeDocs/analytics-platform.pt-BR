---
description: Entenda o que são métricas e como usá-las no Adobe Analytics.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 8%

---

# Métricas

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

## Utilização de métricas no Analysis Workspace

As métricas são flexíveis em seu uso no Analysis Workspace. Arraste uma métrica para uma Tabela de forma livre vazia para ver a tendência da métrica no período do projeto. Você também pode arrastar uma métrica quando uma dimensão estiver presente para ver como essa métrica se compara a cada item de dimensão. Arrastar uma métrica para cima de um cabeçalho de métrica existente substitui a métrica existente, e arrastar uma métrica ao lado de um cabeçalho permite ver ambas as métricas lado a lado.

Para obter informações sobre como adicionar métricas e outros tipos de componentes ao Analysis Workspace, consulte [Usar componentes no Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipos de métricas

A Adobe oferece vários tipos de métricas para uso no Analysis Workspace:


* **Métricas padrão**: exemplos de métricas padrão são Pessoas, Sessões, Eventos, Contas do [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}.

  Ao contrário do Adobe Analytics, o Customer Journey Analytics permite definir métricas padrão de maneira flexível no escopo de uma conexão e de uma visualização de dados.  Consulte [Métricas padrão](#standard-metrics) para obter a lista completa de métricas padrão.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): [Métricas definidas pelo usuário](/help/components/calc-metrics/calc-metr-overview.md) que são baseadas em métricas padrão, números estáticos ou funções algorítmicas.

* **Modelos de métrica calculada** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : métricas definidas pela Adobe que se comportam de forma semelhante às métricas calculadas. Você pode usá-los como estão nos projetos do Workspace ou salvar uma cópia para personalizar a lógica. Consulte [Métricas calculadas padrão](calc-metrics/cm-workflow/../default-calcmetrics.md).

Você pode ver se uma métrica foi aprovada ![ícone Aprovado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) ou não. Para obter mais detalhes sobre uma métrica, passe o mouse sobre a métrica e selecione ![Ícone de informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Informações do componente](use-components-in-workspace.md#component-info) para obter mais informações.


## Métricas padrão

A lista completa de métricas padrão no Customer Journey Analytics:
{{standard-metrics}}


## Criar métricas calculadas

Métricas calculadas permitem configurar como as métricas se relacionam entre si, usando operadores simples ou funções estatísticas. Consulte [Visão geral das métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obter mais informações.

Há várias maneiras de criar métricas calculadas. O método escolhido determina se a métrica calculada estará disponível na lista de componentes em todos os projetos ou somente no projeto em que foi criada.

### Criar métricas calculadas para todos os projetos

Você pode usar o [construtor de métrica calculada](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) para [criar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-workflow.md). Quando criadas dessa forma, as métricas calculadas ficam disponíveis na lista de componentes e podem ser usadas em projetos em toda a organização.

### Criar métricas calculadas para um único projeto

Você pode criar rapidamente uma métrica calculada que esteja disponível somente para o projeto em que foi criada.

Para criar uma métrica calculada para um único projeto:

1. No Analysis Workspace, abra o projeto em que deseja criar a métrica calculada.

1. Em uma tabela de forma livre, clique com o botão direito do mouse no cabeçalho da coluna de uma única coluna.

   Ou

   Selecione duas colunas enquanto mantém pressionada a tecla Shift e clique com o botão direito do mouse em uma das colunas selecionadas.

1. Selecione **[!UICONTROL Criar métrica a partir da seleção]**

   ![Destaque do painel do Workspace Criar a partir da seleção](assets/create-metric-from-selection.png)

1. Para criar uma métrica calculada somente para este projeto, escolha entre as opções disponíveis.

   Quando uma única coluna é selecionada, as seguintes opções estão disponíveis:

   * [!UICONTROL **Média**]: cria uma nova coluna que mostra o valor médio no conjunto de elementos de dimensão para a coluna. Este valor de coluna usa a função [Média](/help/components/calc-metrics/cm-functions.md#mean).

   * [!UICONTROL **Mediana**]: cria uma nova coluna que mostra o valor mediano no conjunto de elementos de dimensão para a coluna. Este valor de coluna usa a função [Mediana](/help/components/calc-metrics/cm-functions.md#median).

   * [!UICONTROL **Coluna máx**]: cria uma nova coluna que mostra o maior valor no conjunto de elementos de dimensão para a coluna. Este valor de coluna usa a função [Máximo de Colunas](/help/components/calc-metrics/cm-functions.md#column-maximum).

   * [!UICONTROL **Coluna mín**]: cria uma nova coluna que mostra o menor valor no conjunto de elementos de dimensão para a coluna. Este valor de coluna usa a função [Mínimo de Coluna](/help/components/calc-metrics/cm-functions.md#column-minimum).

   * [!UICONTROL **Soma da coluna**]: cria uma nova coluna que adiciona todos os valores numéricos de uma métrica em uma coluna (entre os elementos de uma dimensão). Este valor de coluna usa a função [Soma de Coluna](/help/components/calc-metrics/cm-functions.md#column-sum).

   Quando duas colunas são selecionadas, as seguintes opções estão disponíveis:

   * [!UICONTROL **Dividir**]: cria uma nova coluna que divide os valores das duas colunas selecionadas.

   * [!UICONTROL **Subtrair**]: cria uma nova coluna que subtrai os valores das duas colunas selecionadas.

   * [!UICONTROL **Adicionar**]: cria uma nova coluna que adiciona os valores das duas colunas selecionadas.

   * [!UICONTROL **Multiplicar**]: cria uma nova coluna que multiplica os valores das duas colunas selecionadas.

   * [!UICONTROL **Alteração de porcentagem**]: cria uma nova coluna que mostra a alteração de porcentagem entre as duas colunas selecionadas.


## Comparar métricas com diferentes modelos de atribuição

Para comparar um modelo de atribuição rapidamente com outro para uma métrica, selecione **[!UICONTROL Comparar modelos de atribuição]** no menu de contexto para uma métrica.

![realce do painel do Workspace Comparar modelos de atribuição](assets/compare-attribution.png)

Esse atalho permite comparar um modelo de atribuição a outro sem arrastar uma métrica e configurá-la duas vezes.


