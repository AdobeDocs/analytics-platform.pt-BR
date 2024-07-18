---
description: Saiba como adicionar componentes a um projeto no Analysis Workspace
title: Usar componentes no Analysis Workspace
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 697503bba56f44159df7a2f6a0e60a0a4178266d
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 16%

---

# Usar componentes no Analysis Workspace

Os componentes compõem os dados reais de qualquer projeto no Analysis Workspace. Os componentes consistem em dimensões, métricas, filtros e intervalos de datas. Você pode adicionar componentes a um projeto arrastando-os para visualizações ou painéis.

Para obter informações gerais sobre os tipos de componentes que você pode adicionar, consulte [Visão geral dos componentes](/help/components/overview.md).

>[!TIP]
>
>Para obter informações sobre cada componente, selecione o ícone Informações ao lado do nome de um componente no painel esquerdo do Analysis Workspace.

## Começar a adicionar componentes a um projeto

1. [Crie um projeto no Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md) se você ainda não tiver feito isso.

1. [Adicione um painel](/help/analysis-workspace/c-panels/panels.md) ou [adicione uma visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) ao projeto no Analysis Workspace.

   Se você adicionar um componente a um projeto em branco, uma visualização de tabela de forma livre será criada automaticamente.

1. Clique no ícone **[!UICONTROL Componentes]** no menu esquerdo.

   ![](assets/build-components.png)

1. Role até encontrar ou pesquise o componente que deseja adicionar, e arraste-o até um painel ou visualização dentro do projeto.

1. (Opcional) Arraste um componente para a área de destino do filtro em um cabeçalho do painel.

   Os filtros se aplicam a todo o conteúdo do painel.

   Para obter informações sobre como você pode usar a área de destino do filtro em um painel para filtrar seu painel, consulte [Área de destino](/help/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral dos painéis](/help/analysis-workspace/c-panels/panels.md).

   ![soltar um filtro na área de soltar](assets/filter-dropzone.png)

1. Para obter informações mais detalhadas, continue com uma das seções a seguir, dependendo do tipo de componente que você está adicionando:

   * [Adicionar dimensões a um projeto](#add-dimensions-to-a-project)

   * [Adicionar métricas a um projeto](#add-metrics-to-a-project)

   * [Adicionar filtros a um projeto](#add-filters-to-a-project)

   * [Adicionar intervalos de datas a um projeto](#add-date-ranges-to-a-project)

## Adicionar dimensões a um projeto

[Dimension](/help/components/dimensions/overview.md) são variáveis no Adobe Analytics que normalmente contêm valores de cadeia de caracteres. Por outro lado, as [métricas](/help/components/calc-metrics/calc-metr-overview.md) contêm valores numéricos que se vinculam a uma dimensão. Um relatório básico mostra linhas de valores da sequência de caracteres (dimensão) em relação a uma coluna de valores numéricos (métrica).

1. Comece a adicionar uma dimensão ao seu projeto no Analysis Workspace, conforme descrito em [Comece a adicionar componentes a um projeto](#begin-adding-components-to-a-project).

1. Escolha um dos métodos a seguir para adicionar dimensões e determinar o tipo de dados que deseja analisar:

   * Arraste uma dimensão para uma visualização (como uma tabela de forma livre) no Analysis Workspace.

     ![Adicionar dimensões a um projeto](assets/add-dimensions.png)

   * Arraste uma ou mais dimensões do painel esquerdo para a área de destino do filtro para criar um filtro ad hoc, conforme descrito em [Adicionar filtros a um projeto](#add-filters-to-a-project).

1. (Opcional) Você pode detalhar dimensões e itens de dimensão no Analysis Workspace com outros componentes.

   Para obter mais informações, consulte [Analisar dimensões no Workspace](/help/components/dimensions/t-breakdown-fa.md).

Para obter mais informações sobre como usar dimensões no Analysis Workspace, consulte [Visualizar dimensões](/help/components/dimensions/view-dimensions.md), [Analisar dimensões](/help/components/dimensions/t-breakdown-fa.md) e [Dimensões de separação de tempo](/help/components/dimensions/time-parting-dimensions.md).

## Adicionar métricas a um projeto

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

Para adicionar uma métrica a um projeto no Analysis Workspace:

1. Comece a adicionar uma métrica ao seu projeto no Analysis Workspace, conforme descrito em [Comece a adicionar componentes a um projeto](#begin-adding-components-to-a-project).

1. Escolha um dos seguintes métodos para adicionar uma métrica no Analysis Workspace:

   * Arraste uma métrica para a área de soltar métrica em uma tabela de forma livre vazia para ver a tendência da métrica no período de data do projeto.

     ![Adicionar uma métrica a um projeto](assets/add-metrics.png)

   * Arrastar uma métrica quando uma dimensão estiver presente para ver essa métrica em comparada a cada item de dimensão.

   * Arrastar uma métrica sobre um cabeçalho de métrica já existente para substituí-lo.

   * Arrastar uma métrica ao lado de um cabeçalho para ver ambas as métricas lado a lado.

Para obter mais informações sobre métricas, consulte [Visão geral das métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

## Adicionar filtros a um projeto

[Filtros](/help/components/filters/filters-overview.md) permitem identificar subconjuntos de visitantes com base em características ou interações específicas.

Você pode usar filtros no Analysis Workspace de qualquer uma das seguintes maneiras:

### Adicionar filtros a um painel

Ao adicionar filtros a um painel, eles se aplicam a todo o conteúdo do painel.

Para obter informações sobre como você pode usar a área de destino do filtro em um painel para filtrar seu painel, consulte [Área de destino](/help/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral dos painéis](/help/analysis-workspace/c-panels/panels.md).

### Adicionar filtros a uma coluna em uma tabela de forma livre

Ao adicionar filtros a uma coluna em uma tabela de forma livre, os filtros se aplicam a todo o conteúdo na coluna da tabela.

### Usar filtros ao criar métricas calculadas

No Criador de métrica calculada, é possível aplicar filtros em suas definições de métricas.

Para obter mais informações, consulte [Métricas filtradas](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md).

## Adicionar intervalos de datas a um projeto

[Intervalos de datas](/help/components/date-ranges/custom-date-ranges.md) determinam o intervalo de tempo dos relatórios no Analysis Workspace e podem ser aplicados a um ou mais painéis dentro do projeto.

Cada painel inclui um intervalo de datas por padrão. Há várias maneiras de atualizar um intervalo de datas para um painel. Uma maneira de atualizar um intervalo de datas para um painel no Analysis Workspace é arrastar um componente de intervalo de datas do painel esquerdo:

1. Comece a adicionar um intervalo de datas ao seu projeto no Analysis Workspace, conforme descrito em [Comece a adicionar componentes a um projeto](#begin-adding-components-to-a-project).

1. Arraste um intervalo de datas do painel esquerdo para o intervalo de datas atual na parte superior direita do painel.

   ![descartar um intervalo de datas](assets/daterange-drop.png)

Para obter mais informações sobre como usar calendários e intervalos de datas no Analysis Workspace, consulte [Visão geral do calendário e de intervalos de datas](/help/components/date-ranges/custom-date-ranges.md).
