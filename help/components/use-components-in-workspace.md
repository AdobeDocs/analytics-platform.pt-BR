---
description: Saiba como usar componentes em um projeto do Analysis Workspace
title: Usar componentes em um projeto
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 100%

---

# Usar componentes em um projeto

Os componentes representam os dados reais de qualquer projeto no Analysis Workspace. Os componentes consistem em dimensões, métricas, segmentos e intervalos de datas. Você pode adicionar componentes a um projeto arrastando-os para visualizações ou painéis.

Consulte a [Visão geral dos componentes](/help/components/overview.md) para obter mais informações sobre os tipos de componentes que você pode adicionar.

>[!TIP]
>
>Para obter informações sobre cada componente, use ![InfoOutline](/help/assets/icons/InfoOutline.svg). Consulte [Informações do componente](#component-info) para obter mais informações

## Adicionar componentes a um projeto

1. [Crie um projeto no Analysis Workspace](/help/analysis-workspace/build-workspace-project/create-projects.md).

1. [Adicione um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel) ou [uma visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) ao projeto no Analysis Workspace. Se você adicionar um componente a um projeto em branco, uma visualização de tabela de forma livre será criada.

1. Selecione ![Preparar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** no painel de botões. Você verá todos os componentes disponíveis no painel esquerdo. Consulte [Interface](/help/analysis-workspace/home.md#interface) para obter mais detalhes.

1. Role a tela até encontrar ou pesquise o componente que deseja adicionar e arraste-o até um painel ou visualização dentro do projeto.

1. Opcionalmente, é possível arrastar um componente para a zona de destino de segmentos no cabeçalho de um painel. Ao usar o recurso de arrastar e soltar, o componente é definido como um segmento e aplicado a todo o conteúdo dentro do painel.
Para obter informações sobre como usar a zona de destino do segmento em um painel para segmentar o painel, consulte [Zona de destino](/help/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral de painéis](/help/analysis-workspace/c-panels/panels.md).

1. Para obter mais informações, consulte as seguintes seções:

   * [Adicionar dimensões a um projeto](#add-dimensions-to-a-project)

   * [Adicionar métricas a um projeto](#add-metrics-to-a-project)

   * [Adicionar segmentos a um projeto](#add-segments-to-a-project)

   * [Adicionar intervalos de datas a um projeto](#add-date-ranges-to-a-project)

### Adicionar dimensões a um projeto

[Dimensões](/help/components/dimensions/overview.md) são variáveis no Customer Journey Analytics que normalmente contêm valores de string. Por outro lado, as [métricas](/help/components/calc-metrics/calc-metr-overview.md) contêm valores numéricos que se vinculam a uma dimensão. Um relatório básico mostra linhas de valores da sequência de caracteres (dimensão) em relação a uma coluna de valores numéricos (métrica).

1. Comece adicionando uma dimensão ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).

1. Escolha um dos métodos a seguir para adicionar dimensões e determinar o tipo de dados que deseja analisar:

   ![Adicionar uma dimensão](/help/components/assets/add-dimension.gif)

   * Arraste uma dimensão para uma visualização (como uma tabela de forma livre) no Analysis Workspace.

   * Arraste uma ou mais dimensões do painel esquerdo para a zona de destino de segmentos para criar um segmento rápido, conforme descrito em [Adicionar segmentos a um projeto](#add-filters-to-a-project).

1. Opcionalmente, é possível detalhar dimensões e itens de dimensão no Analysis Workspace com outros componentes. Para obter mais informações, consulte [Analisar dimensões no Workspace](/help/components/dimensions/t-breakdown-fa.md).

Para obter mais informações sobre como usar dimensões no Analysis Workspace, consulte [Visualizar dimensões](/help/components/dimensions/view-dimensions.md), [Detalhar dimensões](/help/components/dimensions/t-breakdown-fa.md) e [Dimensões com separação de tempo](/help/components/dimensions/time-parting-dimensions.md).

### Adicionar métricas a um projeto

As métricas permitem quantificar os pontos de dados no Analysis Workspace. Elas são usadas com mais frequência como colunas em uma visualização e são vinculadas a dimensões.

Para adicionar uma métrica a um projeto no Analysis Workspace:

1. Comece a adicionar uma métrica ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).



1. Escolha um dos seguintes métodos para adicionar uma métrica no Analysis Workspace:

   ![Adicionar uma métrica](/help/components/assets/add-metric.gif)

   * Arraste uma métrica para a zona de destino de métricas em uma tabela de forma livre vazia para ver a tendência dessa métrica ao longo do período do projeto.

   * Arraste uma métrica quando houver uma dimensão presente para analisar essa métrica em cada item de dimensão.

   * Arrastar uma métrica sobre um cabeçalho de métrica existente para substituí-lo.

   * Arraste uma métrica para o lado esquerdo ou direito de um cabeçalho de métrica existente para adicionar a nova métrica.

   * Arraste uma métrica acima ou abaixo de um cabeçalho de métrica existente para criar uma sobreposição de métrica.


Para obter mais informações sobre métricas, consulte [Métricas](/help/components/apply-create-metrics.md).

### Adicionar segmentos a um projeto

[Segmentos](/help/components/segments/seg-overview.md) permitem identificar subconjuntos de pessoas, sessões ou eventos com base em características ou interações específicas.

Você pode usar segmentos no Analysis Workspace de qualquer uma das seguintes maneiras:

* Adicionar segmentos a um painel
Ao adicionar segmentos a um painel, os segmentos se aplicam a todo o conteúdo do painel.
Para obter informações sobre como usar a zona de destino de segmentos em um painel para segmentar o painel, consulte [Zona de destino](/help/analysis-workspace/c-panels/panels.md#drop-zone) na [Visão geral de painéis](/help/analysis-workspace/c-panels/panels.md).

* Adicionar segmentos a uma visualização
Ao adicionar segmentos a uma coluna em uma tabela de forma livre, os segmentos se aplicam a todo o conteúdo na coluna da tabela. Você também pode adicionar segmentos como parte de uma visualização de fallout.

* Usar segmentos em componentes
Ao definir componentes como [métricas calculadas](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md), [anotações](/help/components/annotations/create-annotations.md#annotation-builder) ou até mesmo [segmentos](/help/components/segments/seg-builder.md), você pode usar segmentos como parte da definição.


### Adicionar intervalos de datas a um projeto

[Intervalos de datas](/help/components/date-ranges/overview.md) determinam o intervalo de tempo do relatório no Analysis Workspace e podem ser aplicados a um ou mais painéis em um projeto e também a algumas visualizações (como a tabela de forma livre).

Cada painel inclui um intervalo de datas por padrão. Há várias maneiras de atualizar um intervalo de datas para um painel. Uma maneira de atualizar um intervalo de datas para um painel no Analysis Workspace é arrastar um componente de intervalo de datas do painel esquerdo:

1. Opcionalmente, é possível adicionar um intervalo de datas ao seu projeto no Analysis Workspace, conforme descrito em [Adicionar componentes a um projeto](#add-components-to-a-project).

1. Arraste e solte um intervalo de datas do painel esquerdo no:

   * Intervalo de datas atual, para modificar o intervalo de datas do painel.

     ![Soltar um intervalo de datas](assets/add-date-range.gif)

   * Uma métrica ou dimensão em uma visualização de tabela de forma livre. Consulte [Usar intervalos de datas](/help/components/date-ranges/overview.md#use-date-ranges) para obter mais informações.

Para obter mais informações sobre como usar e gerenciar intervalos de datas no Analysis Workspace, consulte [Visão geral sobre intervalos de datas](/help/components/date-ranges/overview.md).

## Informações de componentes

Passe o mouse sobre qualquer componente para exibir ![Mais informações](/help/assets/icons/InfoOutline.svg). Quando selecionado, um pop-up é exibido com informações adicionais sobre o componente.

![Informações de componentes](assets/component-info.png)

Com base no seu controle de acesso, você pode:

* Acessar a definição do ![Marcador](/help/assets/icons/Bookmark.svg) [!UICONTROL Dicionário de dados] do componente.
* Acessar o construtor de componentes ![Editar](/help/assets/icons/Edit.svg) ou a visualização de dados em que o componente está definido.
