---
title: Saiba como gerenciar públicos-alvo criados no Customer Journey Analytics
description: Saiba como gerenciar públicos-alvo no Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 65dcbf63d9e155cb7e04bf9a550151a37b8457e6
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 18%

---

# Gerenciar públicos-alvo

Os públicos podem ser gerenciados no Customer Journey Analytics usando **[!UICONTROL Componentes]** > **[!UICONTROL Públicos]**.

## Entender as tarefas de gerenciamento de público

O gerenciamento de públicos-alvo criados anteriormente permite:

* **Agendar ou cancelar o agendamento** de atualização automática de público-alvo. A expiração máxima na programação é de 1 ano.
* **Renovar um cronograma de atualização de público** quando estiver prestes a expirar. Públicos que estão prestes a expirar são tratados de forma semelhante aos relatórios agendados que se encontram na mesma situação: o administrador recebe um email um mês antes da expiração programada.
* Exibir o **intervalo de atualização** e a **última vez que um público-alvo foi atualizado**
* Obtenha o insight no **tempo necessário para produzir um público-alvo** do Customer Journey Analytics. E o tempo necessário para que o público-alvo apareça na Real-time Customer Platform para fins de ativação.
* Veja se os públicos-alvo no Customer Journey Analytics estão **sendo usados ativamente pela Real-time Customer Platform**. Ou (idealmente) qualquer aplicativo do Experience Platform que consuma os públicos-alvo criados pelo Customer Journey Analytics.

Se você tiver acesso de [Visualização de público-alvo](/help/technotes/access-control.md#user-level-access), poderá visualizar públicos-alvo. Se você tiver acesso de [Criação de público](/help/technotes/access-control.md#user-level-access), poderá editar e excluir públicos.

## Exibir públicos-alvo na lista de Públicos-alvo

A ➊ Lista de públicos mostra os públicos existentes.

![Gerenciador de públicos-alvo](assets/audiences-manager.png)

Para exibir a lista Público-alvo:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo]**.

1. (Opcional) Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar quais colunas exibir.

1. (Opcional) Pesquise por um público usando ![Pesquisa](/help/assets/icons/Search.svg).

   As seguintes colunas estão disponíveis com informações sobre cada público:

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

## Editar públicos

É possível editar as configurações de um público-alvo a qualquer momento. Ao editar um público-alvo (seja um público-alvo único ou recorrente), é necessária uma republicação.

Para editar um público:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo]**.

   A página Públicos-alvo é exibida.

1. Selecione o título do público-alvo que deseja editar.

   A caixa de diálogo **[!UICONTROL Editar público-alvo]** é exibida.

1. Você pode atualizar qualquer um dos campos disponíveis para o público-alvo. Para obter informações sobre os campos que você pode atualizar, consulte o [Construtor de público-alvo](/help/components/audiences/publish.md#audience-builder) no artigo, [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).

1. Selecione **[!UICONTROL Republicar]**.

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
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar os públicos selecionados para um arquivo chamado `audiences.csv`. |

## Filtrar a lista de públicos

Você pode filtrar a [Lista de públicos-alvo](#audiences-list) usando a ➋ do painel de filtro. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

![Gerenciador de públicos-alvo](assets/audiences-manager.png)

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
