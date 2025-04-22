---
title: Gerenciar segmentos
description: Saiba como gerenciar segmentos no Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: f0786cfa74453693078c7d30d647a96bf1d98d07
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 33%

---

# Gerenciar segmentos


Você pode [compartilhar](filters-share.md), [segmentar](filters-filter.md), [marcar](filters-tag.md), [aprovar](filters-approve.md), renomear, [copiar](filters-copy.md), excluir, exportar segmentos e marcar segmentos como [favoritos](filters-favorite.md) de uma interface de gerenciamento de [!UICONTROL segmento] central. Para gerenciar segmentos:

* Selecione **[!UICONTROL Componentes]** na interface principal e, em seguida, **[!UICONTROL Segmentos]**.


>[!NOTE]
>
>Os segmentos rápidos criados em um projeto específico do Workspace não aparecem no gerenciador de [!UICONTROL Segmento], a menos que você tenha disponibilizado o segmento para todos os seus projetos.
>

## Gerenciador de segmentos

O Gerenciador de segmentos tem os seguintes elementos de interface:

![Interface de segmento](assets/filters-manager.png)

### Lista de segmentos

A lista de segmentos ➊ exibe todos os segmentos que você possui, os segmentos que foram segmentados para todos os seus projetos e os segmentos que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) um segmento. Ver [Marcar segmento como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título e descrição]** | Para editar o segmento, selecione o link de título, que abre o [Construtor de segmentos](filter-builder.md). Um segmento compartilhado é indicado com ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais esse segmento se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário do segmento. Como usuário, você só pode ver os segmentos que possui ou as anotações compartilhadas com você. |
| **[!UICONTROL Tags]** | As tags desse segmento. |
| **[!UICONTROL Compartilhado com]** | Com quantos indivíduos ou grupos você compartilhou o segmento. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar componente]**. Consulte [Compartilhar segmentos](filters-share.md) para obter mais informações. |
| **[!UICONTROL Data de modificação]** | A data e a hora em que o segmento foi modificado pela última vez. |
| **[!UICONTROL Usado em]** | Mostrar onde os segmentos estão sendo usados no momento e quantas vezes eles estão sendo usados em cada área. <p>Por exemplo, se o segmento estiver sendo usado em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**].</p> <p>Selecione o valor desta coluna para ver o detalhamento de onde os segmentos estão sendo usados (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Scorecards para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens em que os segmentos estão sendo usados. Por exemplo, para ver a lista de projetos nos quais eles estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de instâncias de segmentos sendo usadas nessa área:</p>  <ul><li>[!UICONTROL **Projetos**]<p>Contém segmentos que foram [criados no construtor de segmentos](/help/components/filters/filter-builder.md#) e estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém segmentos que foram [criados como segmentos rápidos](/help/components/filters/quick-filters.md) e estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Cartões de pontuação para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar esta opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do criador de relatórios</li><li>Último acesso</li><li>ID do usuário do IMS que acessou pela última vez</li><li>Nome do usuário que acessou pela última vez</li></ul></li></ul><p>Essas informações ajudam a determinar se um componente é relevante para os usuários na sua organização, onde o componente está sendo usado e se o componente precisa ser excluído ou modificado. </p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Estas informações estão disponíveis apenas para os administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar a exibição desta coluna.</li><li>Estas informações não incluem o uso da API ou do data warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas o componente tiver uma data da [!UICONTROL **Última utilização**], ele pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>É possível usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com estas informações para ajudar a acompanhar e entender melhor como os componentes estão sendo usados na sua organização.</p> |
| **[!UICONTROL Última utilização]** | Quando o segmento foi usado pela última vez. |

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível agir em segmentos usando a barra de ação ➋. A barra de ação contém as seguintes ações:

| Ação | Descrição |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** | Adicione outro segmento, usando o [Construtor de segmentos](filter-builder.md). |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *Pesquisar por título*] | Quando nenhum segmento for selecionado na lista, pesquise por segmentos usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Marcar os segmentos selecionados. Na caixa de diálogo **[!UICONTROL Segmento de Marca]**, selecione ou desmarque as marcas dos segmentos selecionados. Selecione **[!UICONTROL Salvar]** para salvar as marcas dos segmentos selecionados. Consulte [Marcar segmentos](/help/components/filters/filters-tag.md) para obter mais informações. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartilhar]** | Compartilhar os segmentos selecionados. Na caixa de diálogo **[!UICONTROL Compartilhar Segmento]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento dos segmentos selecionados. Consulte [Compartilhar segmentos](filters-share.md) para obter mais informações. |
| ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** | Excluir os segmentos selecionados. Uma confirmação será solicitada. |
| ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Renomear]** | Renomeie um único segmento selecionado. Quando selecionada, você pode renomear o segmento em linha. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprovar]** | Aprove os segmentos selecionados. Consulte [Aprovar segmentos](filters-approve.md) para obter mais informações. |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL Copiar]** | Copie o segmento selecionado. Novos segmentos são criados com o mesmo nome e sufixo `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** | Exportar os segmentos para um arquivo `Segments List.csv`. |

### Barra de filtros ativos

O ➌ da barra de filtros mostra os segmentos ativos aplicados a partir do painel de filtros para a lista de segmentos (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel de filtro

Você pode filtrar a lista de segmentos usando o ➍ do painel esquerdo ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. O painel de filtro exibe o tipo de filtro e o número de segmentos que respeitam o filtro específico. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel Filtro.

Consulte [Filtrar a lista de segmentos](filters-filter.md) para obter mais informações.
