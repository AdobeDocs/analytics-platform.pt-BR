---
title: Gerenciar intervalos de datas
description: Compartilhar, renomear ou excluir intervalos de datas no Analysis Workspace.
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: 01f862997503cb36502145eddb47873bc7cb28fe
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 9%

---

# Gerenciar intervalos de datas


Você pode compartilhar, filtrar, marcar, aprovar, copiar, compartilhar e excluir intervalos de datas e marcar intervalos de datas como favoritos em uma interface de gerenciamento central de [!UICONTROL Intervalos de datas]. Para gerenciar intervalos de datas:

* Selecione **[!UICONTROL Componentes]** na interface principal e, em seguida, selecione **[!UICONTROL Intervalos de datas]**.


## Gerenciador de intervalos de datas

O gerenciador de Intervalos de datas tem os seguintes elementos de interface:

![Interface de intervalos de datas](assets/date-ranges-manager.png)

### Lista de intervalos de datas

A lista de intervalos de datas ➊ exibe todos os intervalos de datas. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![EstruturaEstrela](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um intervalo de datas. |
| **[!UICONTROL Título e descrição]** | Para editar o título e a descrição, selecione o link de título, que abre o [Criador de intervalo de datas](/help/components/date-ranges/create.md#date-range-builder). |
| **[!UICONTROL Proprietário]** | O proprietário do intervalo de datas. |
| **[!UICONTROL Tags]** | As tags para esse intervalo de datas. |
| **[!UICONTROL Compartilhado com]** | Os indivíduos ou grupos com os quais você compartilhou o intervalo de datas. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar intervalo de datas]**. |
| **[!UICONTROL Data de modificação]** | Exibe a data e a hora em que o intervalo de datas foi modificado pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível agir em intervalos de datas usando a ➋ da barra de ação. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AdicionarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicione outro intervalo de datas, usando o [Construtor de intervalo de datas](create.md#date-range-builder). |
| ![Pesquisar](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Quando nenhum intervalo de datas for selecionado na lista, procure intervalos de datas usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Marca]** | Marcar os intervalos de datas selecionados. Na caixa de diálogo **[!UICONTROL Intervalo de datas da marca]**, selecione ou desmarque as marcas para os intervalos de datas selecionados. Selecione **[!UICONTROL Salvar]** para salvar as marcas para os intervalos de datas selecionados. |
| ![Compartilhar](/help/assets/icons/Share.svg) **[!UICONTROL Compartilhar]** | Compartilhar os intervalos de datas selecionados. Na caixa de diálogo **[!UICONTROL Compartilhar Intervalo de datas]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento dos intervalos de datas selecionados. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Exclua os intervalos de datas selecionados. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomeie um único intervalo de datas selecionado. Quando selecionado, você pode renomear o intervalo de datas em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprove os intervalos de datas selecionados. |
| ![Cópia](/help/assets/icons/Copy.svg) **[!UICONTROL Cópia]** | Copiar os intervalos de datas selecionados. Novos intervalos de datas são criados com o mesmo nome e sufixo (Copiar) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar os intervalos de datas selecionados para um arquivo `Date ranges List.csv`. |

### Barra de filtros ativa

O ➌ da barra de filtros mostra os filtros ativos (se houver). Você pode remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, use **[!UICONTROL Remover tudo]** para remover todos os filtros.

### Painel Filtro

Você pode filtrar intervalos de datas usando a ➍ do painel esquerdo ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. O painel de filtro exibe o tipo de filtro e o número de intervalos de datas que respeitam o filtro. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtro.

Para filtrar a lista de filtros:

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se você precisar de mais espaço para a lista de Filtros, poderá selecionar ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. Você pode filtrar os intervalos de datas usando qualquer uma das [seções de filtro](#filter-sections) disponíveis.

   >[!INFO]
   >
   >*Itens* referem-se aos itens do intervalo de datas exibidos na [lista de intervalos de datas](#date-ranges-list).
   > 

#### Filtrar seções

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


A [lista de intervalos de datas](#date-ranges-list) é atualizada automaticamente com base na sua configuração de filtro. Você pode ver os filtros configurados na [Barra de filtros ativa](#active-filter-bar).


## Editar intervalos de datas

Você edita um intervalo de datas de duas maneiras:

* Em um projeto do Workspace, use o ícone [Informações do componente](/help/components/use-components-in-workspace.md#component-info).

* Na lista [[!UICONTROL Intervalos de datas]](#date-ranges-list), selecione o título do intervalo de datas.

Você usa o [Criador de intervalo de datas](/help/components/date-ranges/create.md#date-range-builder) para editar o intervalo de datas.




Use o gerenciador de intervalo de datas para compartilhar, renomear ou excluir intervalos de datas. Para acessar o gerenciador de datas:

1. Faça logon em [analytics.adobe.com](https://analytics.adobe.com) usando suas credenciais da Adobe ID.
1. Navegue até [!UICONTROL Componentes] > [!UICONTROL Intervalos de datas].


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->