---
title: Saiba como gerenciar públicos-alvo criados no Customer Journey Analytics
description: Saiba como gerenciar públicos-alvo no Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# Gerenciar públicos-alvo

Os públicos podem ser gerenciados no Customer Journey Analytics usando **[!UICONTROL Componentes]** > **[!UICONTROL Públicos]**.

O gerenciamento de públicos-alvo criados anteriormente permite:

* **Agendar ou cancelar o agendamento** de atualização automática de público-alvo. A expiração máxima na programação é de 1 ano.
* **Renovar um cronograma de atualização de público** quando estiver prestes a expirar. Públicos que estão prestes a expirar são tratados de forma semelhante aos relatórios agendados que se encontram na mesma situação: o administrador recebe um email um mês antes da expiração programada.
* Exibir o **intervalo de atualização** e a **última vez que um público-alvo foi atualizado**
* Obter informações sobre o **tempo necessário para produzir um público-alvo** do Customer Journey Analytics. E o tempo necessário para que o público-alvo apareça na Real-time Customer Platform para fins de ativação.
* Veja se os públicos-alvo no Customer Journey Analytics estão **sendo usados ativamente pela Real-time Customer Platform**. Ou (idealmente) qualquer aplicativo Experience Platform que consuma os públicos-alvo criados pelo Customer Journey Analytics.

Se você tiver acesso de [Visualização de público-alvo](/help/technotes/access-control.md#user-level-access), poderá visualizar públicos-alvo. Se você tiver acesso de [Criação de público](/help/technotes/access-control.md#user-level-access), poderá editar e excluir públicos. A [lista de Públicos-alvo](#audiences-list) mostra os públicos-alvo.

## Lista de públicos-alvo

A ➊ da lista Públicos-alvo exibe colunas para:

| Coluna | Descrição |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando um ou mais públicos-alvo são selecionados, uma barra de ação azul é exibida na parte inferior da interface Públicos-alvo. Consulte [Ações](#actions) para obter mais detalhes. |
| **[!UICONTROL Título e descrição]** | O título e a descrição inseridos ao criar o público-alvo. |
| **[!UICONTROL Visualização de dados]** | A visualização de dados na qual esse público-alvo foi criado. |
| **[!UICONTROL Tamanho do público-alvo]** | O número total de pessoas neste público-alvo. |
| **[!UICONTROL Proprietário]** | O proprietário do público-alvo: a pessoa que criou o público-alvo. |
| **[!UICONTROL Frequência de atualização]** | O intervalo de atualização configurado quando o público foi criado. |
| **[!UICONTROL Tags]** | Qualquer tag aplicada a esse público-alvo. |
| **[!UICONTROL Status de publicação]** | Pode mostrar ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ready]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL In progress]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**. |
| **[!UICONTROL Última atualização]** | Carimbo de data e hora quando o público-alvo foi atualizado pela última vez. |
| **[!UICONTROL Última modificação]** | Carimbo de data e hora quando o público-alvo foi editado ou modificado pela última vez. |

Você pode usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar quais colunas exibir. Pesquisar um público usando ![Pesquisar](/help/assets/icons/Search.svg).

Para editar um público:

1. Selecione o título do público-alvo. Use a caixa de diálogo **[!UICONTROL Editar projeto de público-alvo]** para atualizar o público. Consulte [Construtor de público-alvo](publish.md#audience-builder) para obter mais detalhes.

1. Selecione **[!UICONTROL Republicar]** para republicar a audiência.


## Ações

As ações a seguir são comuns no Gerenciador de projetos programados. Você pode selecionar ações no menu de contexto:

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![Rótulos](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Marque os públicos selecionados. Na caixa de diálogo **[!UICONTROL Atualizar marcas: *nome do público-alvo *]**, selecione marcas no menu suspenso ou digite uma ou mais marcas novas. Selecione**[!UICONTROL Salvar ]**para salvar. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua os públicos selecionados. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomeie o público selecionado. Use a caixa de diálogo **[!UICONTROL Renomear: *nome do público-alvo *]**para renomear o público-alvo e selecione**[!UICONTROL Salvar ]**para salvar. |

As seguintes ações estão disponíveis na barra de ação azul ao selecionar um ou mais projetos agendados.

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![Fechar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selecionado]** | Selecione para desmarcar os públicos selecionados. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua os públicos selecionados. |
| ![ArquivoCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar os públicos selecionados para um arquivo chamado `audiences.csv`. |

## Filtro

Você pode filtrar a [Lista de públicos-alvo](#audiences-list) usando a ➋ do painel de filtro. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

O painel de filtro consiste nas seções a seguir.

### Visualização de dados

| Visualização de dados | Descrição |
|---|---|
| ![Proprietários](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | A seção **[!UICONTROL Visualização de dados]** permite filtrar visualizações de dados. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) para procurar exibições de dados que deseja usar para filtrar.</li><li>É possível selecionar mais de uma visualização de dados.</li></ul> |

### Proprietários

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) para procurar proprietários que deseja usar para filtrar.</li><li>É possível selecionar mais de um proprietário. </li></ul> |

## Frequência de atualização

| Frequência de atualização | Descrição |
|---|---|
| ![Frequência de atualização](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | A seção **[!UICONTROL Refresh frequency]** permite filtrar a frequência de atualização. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) para pesquisar a frequência de atualização que deseja usar para filtrar.</li><li>Somente as frequências de atualização definidas para os públicos-alvo <br/> na [lista de Públicos-alvo](#audiences-list) são mostradas como opções disponíveis.</li></ul> |


### Tags

| Tags | Descrição |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar em tags. <ul><li>Você usa a ![Pesquisa](/help/assets/icons/Search.svg) para procurar as tags que deseja usar para filtrar. |
