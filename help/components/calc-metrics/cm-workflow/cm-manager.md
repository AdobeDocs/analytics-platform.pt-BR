---
description: O Gerenciador de métrica calculada permite compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciador de métricas calculadas
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: a8d33db669259cef470b8514f244c29148f57561
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 5%

---

# Gerenciar métricas calculadas

Você pode compartilhar, filtrar, marcar, aprovar, renomear, copiar, excluir, exportar métricas calculadas e marcar métricas calculadas como favoritas de uma interface de gerenciamento central de [!UICONTROL Métricas calculadas]. Para gerenciar métricas calculadas:


* Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Métricas calculadas]**.


## Gerenciador de métricas calculadas

O gerenciador de métricas calculadas tem os seguintes elementos de interface:


![Interface de filtros](assets/calculated-metrics-manager.png)

### Lista de filtros

A ➊ da lista de filtros exibe todas as métricas calculadas que você possui ou que foram compartilhadas com você. A lista tem as seguintes colunas:

<!-- I think this table incorrectly talks about quick calculated metrics -->

| Coluna | Descrição |
| --- | --- | 
| ![EstruturaEstrela](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) uma métrica calculada. Consulte [Marcar métrica calculada como favorita](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título e descrição]** | Para editar a métrica calculada, selecione o link de título, que abrirá o [Criador de métricas calculadas](cm-build-metrics.md). Uma métrica calculada compartilhada é indicada com ![Compartilhamento](/help/assets/icons/Share.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais essa métrica calculada se aplica. |
| **[!UICONTROL Proprietário]** | Proprietário da métrica calculada. Como usuário, você só verá as anotações que possui ou as anotações que são compartilhadas com você. |
| **[!UICONTROL Tags]** | Lista as tags dessa métrica calculada. |
| **[!UICONTROL Compartilhado com]** | Lista com quantos indivíduos ou grupos você compartilhou a métrica calculada. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar métrica calculada]**. Consulte [Compartilhar métricas calculadas](cm-sharing.md) para obter mais informações. |
| **[!UICONTROL Data de modificação]** | A data e a hora em que a métrica calculada foi modificada pela última vez. |
| **[!UICONTROL Usado em]** | Mostra onde as métricas calculadas estão sendo usadas atualmente e quantas vezes elas estão sendo usadas em cada área. <p>Por exemplo, se a métrica calculada estiver sendo usada em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**]. <p>Selecione o valor desta coluna para ver o detalhamento de onde as métricas calculadas estão sendo usadas (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Scorecards para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens em que as métricas calculadas estão sendo usadas. Por exemplo, para ver a lista de projetos em que estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de instâncias de métricas calculadas que estão sendo usadas nessa área:</p> <ul><li>[!UICONTROL **Projetos**]<p>Contém métricas calculadas que foram [criadas no construtor de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) e que estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém métricas calculadas que foram [criadas como métricas calculadas rápidas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) e que estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Scorecards para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar essa opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do Report Builder</li><li>Último acesso</li><li>ID de usuário IMS acessada pela última vez</li><li>Nome do usuário acessado por último</li></ul></li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações estão disponíveis somente para administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar a exibição desta coluna.</li><li>Essas informações não incluem o uso da API ou da Data Warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas ela tiver uma data [!UICONTROL **Última utilização**], o componente pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
| **[!UICONTROL Última utilização]** | Quando a métrica calculada foi usada pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações em filtros usando o ➋ da barra de ações. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AdicionarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicione outras métricas calculadas, usando o [Criador de métricas calculadas](cm-build-metrics.md). |
| ![Pesquisar](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Quando nenhuma métrica calculada for selecionada na lista, procure por filtros usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Marca]** | Marcar as métricas calculadas selecionadas. Na caixa de diálogo **[!UICONTROL Marcar métrica calculada]**, selecione ou desmarque as marcas da métrica calculada selecionada. Selecione **[!UICONTROL Salvar]** para salvar as marcas das métricas calculadas selecionadas. Consulte [Marcar métricas calculadas](cm-tagging.md) para obter mais informações. |
| ![Compartilhar](/help/assets/icons/Share.svg) **[!UICONTROL Compartilhar]** | Compartilhar as métricas calculadas selecionadas. Na caixa de diálogo **[!UICONTROL Compartilhar métricas calculadas]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento das métricas calculadas selecionadas. Consulte [Compartilhar métricas calculadas](cm-sharing.md) para obter mais informações. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Excluir as métricas calculadas selecionadas. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomear uma única métrica calculada selecionada. Quando selecionada, você pode renomear a métrica calculada em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprove as métricas calculadas selecionadas. Consulte [Aprovar métricas calculadas](cm-approving.md). |
| ![Cópia](/help/assets/icons/Copy.svg) **[!UICONTROL Cópia]** | Copie as métricas calculadas selecionadas. Novas métricas calculadas são criadas com o mesmo nome e sufixo `(Copy)` |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar as métricas calculadas para um arquivo `Calculated  metric List.csv`. |

### Barra de filtros ativa

O ➌ da barra de filtros mostra os filtros ativos aplicados do painel de filtros à lista de métricas calculadas (se houver). Você pode remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel Filtro

Você pode filtrar a lista de métricas calculadas usando o ➍ do painel esquerdo ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. O painel de filtros exibe o tipo de filtro e o número de métricas calculadas que respeitam o filtro específico. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtro.

Consulte [Filtrar a lista de métricas calculadas](cm-filter.md) para obter mais informações.


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a filter), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->