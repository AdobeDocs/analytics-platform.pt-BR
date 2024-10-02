---
title: Gerenciar anotações
description: Como gerenciar anotações no Espaço de trabalho.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 8%

---

# Gerenciar anotações

Você pode compartilhar, filtrar, marcar, aprovar, copiar, excluir anotações e marcar anotações como favoritas de uma interface de gerenciamento central de [!UICONTROL Anotações]. Para gerenciar anotações:

* Selecione **[!UICONTROL Componentes]** na interface principal e **[!UICONTROL Anotações]**.


>[!NOTE]
>
>As anotações criadas em um projeto específico do Workspace não aparecem no gerenciador [!UICONTROL Anotações], a menos que você tenha disponibilizado a anotação para todos os seus projetos.
>

## Gerenciador de anotações

O Gerenciador de anotações tem os seguintes elementos de interface:

![Interface de anotações](assets/annotations-manager.png)

### Lista de anotações

A ➊ Lista de anotações exibe todas as anotações que você possui, as anotações que foram segmentadas para todos os seus projetos e as anotações que foram compartilhadas com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- | 
| ![EstruturaEstrela](/help/assets/icons/StarOutline.svg) | Selecione para favorecer ![Star](/help/assets/icons/Star.svg) ou desfavorecer ![StarOutline](/help/assets/icons/StarOutline.svg) uma anotação. |
| **[!UICONTROL Título e descrição]** | Fornecidos no Construtor de anotações. Para editar o título e a descrição, selecione o link de título - abre o [Construtor de anotações](/help/components/annotations/create-annotations.md#annotation-builder). Uma anotação compartilhada é indicada com ![Compartilhamento](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Visualização de dados]** | As visualizações de dados às quais essa anotação se aplica. |
| **[!UICONTROL Proprietário]** | O proprietário da anotação. Como usuário, você só verá as anotações que possui ou as anotações que são compartilhadas com você. |
| **[!UICONTROL Intervalo de datas aplicado]** | A data ou o intervalo de datas ao qual essa anotação se aplica. |
| **[!UICONTROL Tags]** | As tags para essa anotação. |
| **[!UICONTROL Compartilhado com]** | Os indivíduos ou grupos com os quais você compartilhou a anotação. Selecione para abrir a caixa de diálogo **[!UICONTROL Compartilhar Componente]**. |
| **[!UICONTROL Data de modificação]** | Exibe a data e a hora em que a anotação foi modificada pela última vez. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar quais colunas deseja exibir.

### Barra de ação

É possível executar ações em anotações usando a barra de ações ➋. A barra de ação contém as seguintes ações:

| Ícone | Ação | Descrição |
|:--:|---|---|
| ![AdicionarCírculo](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Adicionar]** | Adicione outra anotação, usando o [Construtor de anotações](create-annotations.md#annotation-builder). |
| ![Pesquisar](/help/assets/icons/Search.svg) | [!UICONTROL *Pesquisar por título*] | Quando nenhuma anotação for selecionada na lista, pesquise por anotações usando esse campo de pesquisa. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marcar as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Componente de Marca]**, selecione ou desmarque as marcas das anotações selecionadas. Selecione **[!UICONTROL Salvar]** para salvar as marcas das anotações selecionadas. |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartilhar]** | Compartilhar as anotações selecionadas. Na caixa de diálogo **[!UICONTROL Compartilhar Componente]**, você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar pessoas físicas ou grupos* ou selecionar **[!UICONTROL Organização]** ou **[!UICONTROL Grupos]**. Selecione **[!UICONTROL Salvar]** para salvar os detalhes de compartilhamento das anotações selecionadas. Consulte [Compartilhar anotações](#share-annotations) para obter mais detalhes. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Excluir as anotações selecionadas. Será solicitada uma confirmação. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomear uma única anotação selecionada. Quando selecionada, você pode renomear a anotação em linha. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copiar as anotações selecionadas. Novas anotações são criadas com o mesmo nome e sufixo (Copiar) |
| ![ArquivoCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar as anotações para um arquivo `Annotations List.csv`. |

### Barra de filtros ativa

O ➌ da barra de filtros mostra os filtros ativos (se houver). Você pode remover um filtro rapidamente usando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se mais de um filtro for especificado, você poderá remover todos os filtros usando **[!UICONTROL Remover tudo]**.

### Painel Filtro

Você pode filtrar anotações usando o ➍ do painel esquerdo **[!UICONTROL Filtro]**. O painel de filtros exibe o tipo de filtro e o número de anotações que respeitam o filtro. Selecione ![Filtro](/help/assets/icons/Filter.svg) para alternar a exibição do painel de filtro.

Para filtrar a lista de filtros:

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) para abrir o painel Filtros. Se você precisar de mais espaço para a lista de Filtros, poderá selecionar ![Filtro](/help/assets/icons/Filter.svg) mais uma vez para fechar o painel.
1. Você pode filtrar as anotações usando qualquer uma das [seções de filtro](#filter-sections) disponíveis.

   >[!INFO]
   >
   >*Itens* referem-se aos itens de anotação exibidos na [Lista de anotações](manage-annotations.md#annotations-list).
   > 

#### Filtrar seções

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


A [Lista de anotações](manage-annotations.md#annotations-list) é atualizada automaticamente com base na sua configuração de filtro. Você pode ver os filtros configurados na [Barra de filtros ativa](manage-annotations.md#active-filter-bar).


## Editar anotações

É possível editar uma anotação de duas maneiras:

* Em um projeto do Workspace, use o ícone [Informações do componente](/help/components/use-components-in-workspace.md#component-info).

* Na lista [[!UICONTROL Anotações]](#annotations-list), selecione o título da anotação.

Você usa o [Construtor de anotações](/help/components/annotations/create-annotations.md#annotation-builder) para editar a anotação.

## Compartilhar anotações

O seguinte se aplica ao compartilhar anotações ou trabalhar com anotações compartilhadas com você:

* As anotações somente de projeto em um projeto que você compartilha com outros usuários são exibidas para esses usuários. Os usuários não podem editar ou excluir essas anotações somente de projeto.
* Se você salvar uma anotação e compartilhá-la diretamente com um usuário, esse usuário poderá editar e excluir a anotação somente se tiver direitos de administrador.

* Se um projeto for compartilhado com você, as anotações criadas nesse projeto serão exibidas somente nesse projeto. Se uma anotação for compartilhada diretamente com você, ela será exibida em todos os projetos nos quais pode ser exibida.

## Anotações e fusos horários

Todas as anotações são criadas com um carimbo de data e hora, mas sem informações de hora ou fuso horário. No momento do relatório, é usado o fuso horário da visualização de dados configurada para o painel.
