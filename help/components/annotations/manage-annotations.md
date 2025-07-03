---
title: Gerenciar anotações
description: Saiba como gerenciar anotações no Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 91%

---

# Gerenciar anotações

Você pode compartilhar, filtrar, marcar, aprovar, copiar, excluir anotações e adicioná-las aos favoritos utilizando a interface de gerenciamento central [!UICONTROL Anotações]. Para gerenciar anotações:

* Selecione **[!UICONTROL Componentes]** na interface principal e clique em **[!UICONTROL Anotações]**.


>[!NOTE]
>
>As anotações criadas em um projeto específico do espaço de trabalho não aparecem no gerenciador [!UICONTROL Anotações], a menos que você tenha disponibilizado ela para todos os seus projetos.
>

## Gerenciador de anotações

O Gerenciador de anotações tem os seguintes elementos de interface:

![Interface de anotações](assets/annotations-manager.png)

### Lista de anotações

A lista de anotações ➊ exibe todas as anotações que você possui, as anotações que foram segmentadas para todos os seus projetos e as anotações que foram compartilhadas com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione ![Estrela](/help/assets/icons/Star.svg) para adicionar ou ![StarOutline](/help/assets/icons/StarOutline.svg) para remover uma anotação dos favoritos. |
| **[!UICONTROL Título e descrição]** | Fornecidos no Criador de anotações. Para editar o título e a descrição, clique no link de título para abrir o [Criador de anotações](/help/components/annotations/create-annotations.md#annotation-builder). Uma anotação compartilhada é indicada pelo ícone ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais essa anotação se aplica. |
| **[!UICONTROL Proprietário]** | O(a) proprietário(a) da anotação. Como usuário, você só vê as anotações que possui ou as que são compartilhadas com você. |
| **[!UICONTROL Intervalo de datas aplicado]** | A data ou o intervalo de datas ao qual essa anotação se aplica. |
| **[!UICONTROL Tags]** | As tags dessa anotação. |
| **[!UICONTROL Compartilhado com]** | As pessoas ou grupos com os quais você compartilhou a anotação. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar componente]**. |
| **[!UICONTROL Data de modificação]** | Mostra a data e a hora em que a anotação foi modificada pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações em anotações usando a barra de ações ➋. A barra de ação contém as seguintes ações:

| Ícone | Ação | Descrição |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Adicionar]** | Adicione outra anotação usando o [Criador de anotações](create-annotations.md#annotation-builder). |
| ![Pesquisar](/help/assets/icons/Search.svg) | [!UICONTROL *Pesquisar por título*] | Se nenhuma anotação for selecionada na lista, pesquise por anotações usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marque as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Componente de tag]**, marque ou desmarque as tags das anotações selecionadas. Clique em **[!UICONTROL Salvar]** para salvar as tags das anotações selecionadas. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartilhar]** | Compartilhe as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Compartilhar componente]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *pesquisar indivíduos ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Clique em **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento das anotações selecionadas. Consulte [Compartilhar anotações](#share-annotations) para obter mais detalhes. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclui as anotações selecionadas. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomeia uma única anotação selecionada. Quando selecionada, você pode renomear a anotação em linha. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copia as anotações selecionadas. Novas anotações são criadas com o mesmo nome e sufixo (Copiar) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exporta as anotações para um arquivo `Annotations List.csv`. |

### Barra de filtros ativos

A barra de filtros ➌ mostra os filtros ativos (se houver). É possível remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel de filtro

Você pode filtrar anotações usando o **[!UICONTROL Filtro]** no painel esquerdo ➍. O painel de filtros exibe o tipo de filtro e o número de anotações que se enquadram no filtro. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtros.

Para filtrar a lista de filtros:

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se você precisar de mais espaço para a lista de filtros, selecione ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. É possível filtrar as anotações usando qualquer uma das [seções de filtro](#filter-sections) disponíveis.

   >[!INFO]
   >
   >Os *itens* referem-se às anotações exibidas na [Lista de anotações](manage-annotations.md#annotations-list).
   > 

#### Seções de filtro

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


A [Lista de anotações](manage-annotations.md#annotations-list) é atualizada automaticamente com base na sua configuração de filtro. É possível ver os filtros configurados na [Barra de filtros ativos](manage-annotations.md#active-filter-bar).


## Editar anotações

É possível editar uma anotação de duas formas:

* Em um projeto do espaço de trabalho, use o ícone [Informações do componente](/help/components/use-components-in-workspace.md#component-info).

* Na lista [[!UICONTROL Anotações]](#annotations-list), selecione o título da anotação.

Use o [Criador de anotações](/help/components/annotations/create-annotations.md#annotation-builder) para editar a anotação.

## Compartilhar anotações

O seguinte se aplica ao compartilhar anotações ou trabalhar com anotações que foram compartilhadas com você:

* As anotações somente de projeto pertencentes a um projeto que você compartilhou com outros usuários também aparecem para esses usuários. Os usuários não podem editar ou excluir essas anotações somente de projeto.
* Se você salvar uma anotação e compartilhá-la diretamente com um usuário, esse usuário poderá editar e excluir a anotação somente se tiver direitos de admin.

* As anotações criadas em um projeto que foi compartilhado com você aparecerão somente nesse projeto. Se a anotação for compartilhada diretamente com você, ela aparecerá em todos os projetos nos quais ela pode ser exibida.

## Anotações e fusos horários

Todas as anotações são criadas com um carimbo de data e hora, mas sem informações de hora ou fuso horário. Durante a geração do relatório, utiliza-se o fuso horário da visualização de dados configurada para o painel.
