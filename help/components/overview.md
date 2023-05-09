---
title: Quais são os componentes no Customer Journey Analytics?
description: Saiba quais componentes o CJA oferece e como usá-los no relatórios.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: d431e781eb18eb3f4904094972c218a9e80980d9
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 62%

---

# Visão geral dos componentes

Os componentes são recursos do Customer Journey Analytics que podem ser usados em relatórios ou complementar os recursos dos relatórios. Você pode gerenciar esses componentes usando as seguintes etapas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando as credenciais da Adobe ID.
2. Acesse [!UICONTROL Componentes] > [!UICONTROL Componentes] no menu de cabeçalho.

Você pode gerenciar os seguintes componentes:

* [**Anotações**](/help/components/annotations/overview.md): Comunique nuances e insights de dados contextuais à sua organização.
* [**Filtros:**](filters/filters-overview.md) exclua partes dos dados para se concentrar em itens de dimensão comuns
* [**Métricas calculadas:**](calc-metrics/calc-metr-overview.md) use métricas e fórmulas como novos componentes para usar nos relatórios
* [**Intervalos de datas:**](date-ranges/overview.md) personalize e refine os intervalos de datas nas ofertas do Analysis Workspace
* [**Projetos:**](/help/analysis-workspace/home.md) organize e mantenha seus projetos no Analysis Workspace

## Componentes do Analysis Workspace

Os componentes do Analysis Workspace são métricas, dimensões, filtros e granularidades de tempo que você pode arrastar e soltar em um projeto. Os componentes personalizados que você criou são adicionados a esses painéis, como intervalos de data personalizados.

Para acessar o painel Componentes, clique no ícone **[!UICONTROL Componentes]** no painel à esquerda. Você pode alternar entre Painéis (Painel em branco, [Painel de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Quick Insights](/help/analysis-workspace/c-panels/quickinsight.md) ou painel do [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md)), [Visualizações](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e Componentes usando os ícones do painel esquerdo ou usando [teclas de atalho](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/components.png)

Consulte [Criar um projeto](/help/analysis-workspace/home.md) para obter informações sobre como usar os Componentes em um projeto.

## Ações dos componentes

Há várias maneiras de gerenciar componentes (individualmente ou ao selecionar mais de um). Clique com o botão direito em um componente ou clique em **[!UICONTROL Ações]** na parte superior da lista de componentes.

>[!NOTE]
>
>Essas ações não se aplicam aos componentes de Tempo.

| Ação de componente | Descrição |
| --- | --- |
| Tag | Organize ou gerencie componentes aplicando tags. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos] |
| Marcar como favorito | Adicione o componente à sua lista de favoritos. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos]. |
| Aprovar | Aprove o componente para torná-lo canônico. Em seguida, ele é exibido no respectivo gerenciador de componente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros] ou [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Projetos] |
| Compartilhar | Aplicado somente a filtros. |
| Excluir | Aplicado somente a filtros. |

Assista ao vídeo Criar métricas, filtros e datas:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Gerenciar componentes {#actions}

Você pode gerenciar componentes diretamente no painel esquerdo.

1. Clique com o botão direito do mouse em um componente.

   Ou

   Selecione um componente e depois selecione o **Ação** Ícone (3 pontos) na parte superior da lista de componentes.

   >[!TIP]
   >
   >   Você pode selecionar vários componentes mantendo a tecla Shift pressionada ou mantendo a tecla Command (no Mac) ou Ctrl (no Windows) pressionada.


   ![](assets/component-actions.png)

   | Ação do componente | Descrição |
   |--- |--- |
   | [!UICONTROL **Tag**] | Organize ou gerencie componentes aplicando tags. Em seguida, você pode pesquisar por tag no painel esquerdo clicando no filtro ou digitando #. As tags também atuam como filtros nos gerenciadores de componentes. |
   | [!UICONTROL **Marcar como favorito**] | Adicione o componente à sua lista de favoritos. Como tags, você pode pesquisar por Favoritos no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Aprovar**] | Marque os componentes como Aprovado para avisar aos usuários que o componente é aprovado pela organização. Como tags, você pode pesquisar por Aprovado no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
   | [!UICONTROL **Compartilhar**] | Compartilhe componentes com usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |
   | [!UICONTROL **Excluir**] | Exclua componentes que não são mais necessários. Essa opção está disponível somente para componentes personalizados, como filtros ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos Gerenciadores de componentes. Por exemplo, a variável [Gerenciar filtros](/help/components/filters/manage-filters.md).

## Pesquisar, filtrar e classificar a lista de componentes

Você pode pesquisar, filtrar e classificar a lista de componentes no painel esquerdo do Analysis Workspace para localizar rapidamente um componente específico.

### Pesquisar a lista de componentes

1. Selecione o **Componentes** ícone ![Ícone Componentes](assets/components-icon.png) no painel esquerdo.

1. No campo de pesquisa , comece a digitar o nome do componente que deseja usar no projeto.

   O tipo de componente pode ser identificado por cor e ícone. **Dimension** ![Ícone Dimension](assets/dimension-icon.png) são laranja, **Filtros** ![Ícone Filtro](assets/segment-icon.png) são azuis, **Intervalos de datas** ![Ícone de intervalo de datas](assets/date-range-icon.png) são roxas e **Métricas** ![Ícone Métrica](assets/default-metric-icon.png) são verdes. O ícone Adobe ![Ícone Adobe](assets/default-calc-metric-icon.png) indica um modelo de métrica calculada ou um modelo de filtro, e o ícone da calculadora ![Ícone Calculadora](assets/calculated-metric-icon-created.png) indica uma métrica calculada criada por um administrador do Analytics em sua organização.

1. Selecione o componente quando ele for exibido na lista suspensa.

### Filtrar a lista de componentes

1. Selecione o **Componentes** ícone ![Ícone Componentes](assets/components-icon.png) no painel esquerdo.

1. Selecione o **Filtro** ícone ![Ícone do Filtro do dicionário de dados](assets/components-filter-icon.png).

   Ou

   Digite o sinal de número (#) no campo de pesquisa.

1. Selecione qualquer uma das seguintes opções de filtro para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Gerenciar componentes](#manage-components). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. |
   | [!UICONTROL **Filtros**] | Mostrar somente componentes que são Filtros. |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |

1. (Opcional) Para aprimorar a lista, é possível classificar a lista de componentes, conforme descrito em [Classificar a lista de componentes](#sort-the-component-list).

### Classificar a lista de componentes

1. (Opcional) Aplique quaisquer filtros à lista de componentes, conforme descrito em [Filtrar a lista de componentes](#filter-the-component-list).

1. Selecione o **Componentes** ícone ![Ícone Componentes](assets/components-icon.png) no painel esquerdo.

1. Selecione o **Classificar** ícone ![Ícone Classificar componentes](assets/component-sort-icon.png)e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}

## Permissões de acesso a componentes

No Analysis Workspace, os administradores podem [preparar](/help/analysis-workspace/curate-share/curate.md) quais componentes são expostos aos usuários nos relatórios.
