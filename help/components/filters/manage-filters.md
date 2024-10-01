---
title: Gerenciar filtros
description: Saiba como gerenciar filtros no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# Gerenciar filtros


Você pode [compartilhar](filters-share.md), [filtrar](filters-filter.md), [marcar](filters-tag.md), [aprovar](filters-approve.md), renomear, [copiar](filters-copy.md), excluir, exportar filtros e marcar filtros como [favoritos](filters-favorite.md) de uma interface de gerenciamento central de [!UICONTROL Filtros]. Para gerenciar filtros:

* Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Filtros]**.


>[!NOTE]
>
>Os filtros rápidos que você cria em um projeto específico do Workspace não aparecem no gerenciador [!UICONTROL Filtros], a menos que você tenha disponibilizado o filtro para todos os seus projetos.
>

## Gerenciador de filtros

O gerenciador de Filtros tem os seguintes elementos de interface:

![Interface de filtros](assets/filters-manager.png)

### Lista de filtros

A ➊ da lista de filtros exibe todos os filtros que você possui, os filtros que foram segmentados para todos os seus projetos e os filtros que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![EstruturaEstrela](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um filtro. Ver [Marcar filtro como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título e descrição]** | Para editar o filtro, selecione o link de título, que abre o [Construtor de filtros](filter-builder.md). Um filtro compartilhado é indicado com ![Compartilhamento](/help/assets/icons/Share.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais esse filtro se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário do filtro. Como usuário, você só verá os filtros que possui ou as anotações compartilhadas com você. |
| **[!UICONTROL Tags]** | As tags para esse filtro. |
| **[!UICONTROL Compartilhado com]** | Com quantos indivíduos ou grupos você compartilhou o filtro. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar Componente]**. Consulte [Compartilhar filtros](filters-share.md) para obter mais informações. |
| **[!UICONTROL Data de modificação]** | A data e a hora da última modificação do filtro. |
| **[!UICONTROL Usado em]** | Mostra onde os filtros estão sendo usados atualmente e quantas vezes eles estão sendo usados em cada área. <p>Por exemplo, se o filtro estiver sendo usado em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**].</p> <p>Selecione o valor desta coluna para ver o detalhamento de onde os filtros estão sendo usados (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Scorecards para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens em que os filtros estão sendo usados. Por exemplo, para ver a lista de projetos em que estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de ocorrências de filtros que estão sendo usados nessa área:</p>  <ul><li>[!UICONTROL **Projetos**]<p>Contém filtros que foram [criados no construtor de filtros](/help/components/filters/filter-builder.md#) e estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém filtros que foram [criados como filtros rápidos](/help/components/filters/quick-filters.md) e estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Scorecards para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar essa opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do Report Builder</li><li>Último acesso</li><li>ID de usuário IMS acessada pela última vez</li><li>Nome do usuário acessado por último</li></ul></li></ul><p>Essas informações ajudam a determinar se um componente é valioso para os usuários em sua organização, onde o componente é usado e se ele precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações estão disponíveis somente para administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar a exibição desta coluna.</li><li>Essas informações não incluem o uso da API ou da Data Warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas o componente tiver uma data [!UICONTROL **Última utilização**], ele poderá ter sido usado em uma análise sem ter sido salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
| **[!UICONTROL Última utilização]** | Quando o filtro foi usado pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações em filtros usando o ➋ da barra de ações. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AdicionarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicionar outro filtro, usando o [Construtor de filtros](filter-builder.md). |
| ![Pesquisar](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Quando nenhum filtro estiver selecionado na lista, procure por filtros usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Marca]** | Marcar os filtros selecionados. Na caixa de diálogo **[!UICONTROL Filtro de Marca]**, selecione ou desmarque as marcas dos filtros selecionados. Selecione **[!UICONTROL Salvar]** para salvar as marcas dos filtros selecionados. Consulte [Filtros de marca](/help/components/filters/filters-tag.md) para obter mais informações. |
| ![Compartilhar](/help/assets/icons/Share.svg) **[!UICONTROL Compartilhar]** | Compartilhar os filtros selecionados. Na caixa de diálogo **[!UICONTROL Compartilhar Filtro]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento dos filtros selecionados. Consulte [Compartilhar filtros](filters-share.md) para obter mais informações. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Excluir os filtros selecionados. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomeie um único filtro selecionado. Quando selecionada, você pode renomear o filtro em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprove os filtros selecionados. Consulte [Aprovar filtros](filters-approve.md) para obter mais informações. |
| ![Cópia](/help/assets/icons/Copy.svg) **[!UICONTROL Cópia]** | Copie o filtro selecionado. Novos filtros são criados com o mesmo nome e sufixo `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar os filtros para um arquivo `Filters List.csv`. |

### Barra de filtros ativa

O ➌ da barra de filtros mostra os filtros ativos aplicados do painel de filtros para a lista de filtros (se houver). Você pode remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel Filtro

Você pode filtrar a lista de filtros usando o ➍ do painel esquerdo ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. O painel de filtros exibe o tipo de filtro e o número de filtros que respeitam o filtro específico. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtro.

Consulte [Filtrar a lista de filtros](filters-filter.md) para obter mais informações.
