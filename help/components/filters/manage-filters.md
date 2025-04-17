---
title: Gerenciar filtros
description: Saiba como gerenciar filtros no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '884'
ht-degree: 100%

---

# Gerenciar filtros


Você pode [compartilhar](filters-share.md), [filtrar](filters-filter.md), [marcar](filters-tag.md), [aprovar](filters-approve.md), renomear, [copiar](filters-copy.md), excluir, exportar filtros e marcar filtros como [favoritos](filters-favorite.md) a partir de uma interface de gerenciamento central de [!UICONTROL filtros]. Para gerenciar filtros:

* Selecione **[!UICONTROL Componentes]** na interface principal e clique em **[!UICONTROL Filtros]**.


>[!NOTE]
>
>Os filtros rápidos criados em um projeto específico do Workspace não aparecem no gerenciador de [!UICONTROL filtros], a menos que você os tenha disponibilizado para todos os seus projetos.
>

## Gerenciador de filtros

O gerenciador de filtros tem os seguintes elementos da interface:

![Interface de filtros](assets/filters-manager.png)

### Lista de filtros

A lista de filtros ➊ exibe todos os filtros que você possui, os filtros que foram adicionados ao escopo de todos os seus projetos e os filtros que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione ![Star](/help/assets/icons/Star.svg) para adicionar ou ![StarOutline](/help/assets/icons/StarOutline.svg) para remover um filtro dos favoritos. Consulte [Marcar filtro como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título e descrição]** | Para editar o filtro, clique no link do título para abrir o [Criador de filtros](filter-builder.md). Um filtro compartilhado é indicado pelo ícone de ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais o filtro em questão se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário do filtro. Como usuário, você só vê os filtros que você possui ou os que são compartilhados com você. |
| **[!UICONTROL Tags]** | As tags do filtro em questão. |
| **[!UICONTROL Compartilhado com]** | Com quantos indivíduos ou grupos o filtro foi compartilhado. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar componente]**. Consulte [Compartilhar filtros](filters-share.md) para mais informações. |
| **[!UICONTROL Data de modificação]** | A data e a hora da última modificação do filtro. |
| **[!UICONTROL Usado em]** | Mostra onde os filtros estão sendo usados atualmente e quantas vezes eles estão sendo usados em cada área. <p>Por exemplo, se o filtro estiver sendo usado em 40 projetos e 2 alertas, o valor desta coluna será exibido como [!UICONTROL **42 componentes**].</p> <p>Selecione o valor desta coluna para ver os detalhes de onde os filtros estão sendo usados (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Cartões de pontuação para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens nos quais os filtros estão sendo usados. Por exemplo, para ver a lista de projetos nos quais eles estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra a quantidade de ocorrências de filtros que estão sendo usados em cada área:</p>  <ul><li>[!UICONTROL **Projetos**]<p>Contém filtros que foram [criados no construtor de filtros](/help/components/filters/filter-builder.md#) e estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém filtros que foram [criados como filtros rápidos](/help/components/filters/quick-filters.md) e estão disponíveis somente em um projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Cartões de pontuação para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar esta opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do criador de relatórios</li><li>Último acesso</li><li>ID do usuário do IMS que acessou pela última vez</li><li>Nome do usuário que acessou pela última vez</li></ul></li></ul><p>Essas informações ajudam a determinar se um componente é relevante para os usuários na sua organização, onde o componente está sendo usado e se o componente precisa ser excluído ou modificado. </p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Estas informações estão disponíveis apenas para os administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar a exibição desta coluna.</li><li>Estas informações não incluem o uso da API ou do data warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas o componente tiver uma data da [!UICONTROL **Última utilização**], ele pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>É possível usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com estas informações para ajudar a acompanhar e entender melhor como os componentes estão sendo usados na sua organização.</p> |
| **[!UICONTROL Última utilização]** | Quando o filtro foi usado pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações relacionadas aos filtros por meio da barra de ação ➋. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicione outro filtro por meio do [Criador de filtros](filter-builder.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Se nenhum filtro for selecionado na lista, procure filtros por meio deste campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Marcar os filtros selecionados. Na caixa de diálogo **[!UICONTROL Marcar filtro]**, marque ou desmarque as tags dos filtros selecionados. Clique em **[!UICONTROL Salvar]** para salvar as tags dos filtros selecionados. Consulte [Marcar filtros](/help/components/filters/filters-tag.md) para mais informações. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartilhar]** | Compartilhar os filtros selecionados. Na caixa de diálogo **[!UICONTROL Compartilhar filtro]**, você pode ![Search](/help/assets/icons/Search.svg) *Pesquisar indivíduos ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Clique em **[!UICONTROL Salvar]** para salvar os detalhes do compartilhamento dos filtros selecionados. Consulte [Compartilhar filtros](filters-share.md) para mais informações. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Excluir os filtros selecionados. Uma confirmação será solicitada. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomear um filtro selecionado. Quando selecionado, você pode renomear o filtro em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprovar os filtros selecionados. Consulte [Aprovar filtros](filters-approve.md) para mais informações. |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copiar]** | Copiar os filtros selecionados. Novos filtros são criados com os mesmos nome e sufixo `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar os filtros para um arquivo `Filters List.csv`. |

### Barra de filtros ativos

A barra de filtros ➌ mostra os filtros ativos aplicados a partir do painel de filtros à lista de filtros (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel de filtro

Você pode filtrar a lista de filtros por meio do painel esquerdo ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]** ➍ . O painel de filtros exibe o tipo de filtro e a quantidade de filtros que se enquadram no filtro específico. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtros.

Consulte [Filtrar a lista de filtros](filters-filter.md) para mais informações.
