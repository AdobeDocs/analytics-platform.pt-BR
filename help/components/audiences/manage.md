---
title: Saiba como gerenciar públicos-alvo criados no Customer Journey Analytics
description: Saiba como gerenciar públicos-alvo no Customer Journey Analytics
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 4717a85b9a3c7dc2cbdd8c625ebb5862cbfccd58
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 97%

---

# Gerenciar públicos publicados

Os públicos podem ser gerenciados no Customer Journey Analytics usando **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo]**.

## Entenda as tarefas de gerenciamento de público-alvo

O gerenciamento de públicos-alvo criados anteriormente permite:

* **Agendar ou cancelar o agendamento** de atualização automática de público-alvo. A expiração máxima na programação é de 1 ano.
* **Renovar um cronograma de atualização de público-alvo** quando estiver prestes a expirar. Públicos-alvos que estão prestes a expirar são tratados de forma semelhante aos relatórios agendados que se encontram na mesma situação: o administrador recebe um email um mês antes da expiração programada.
* Exibir o **intervalo de atualização** e a **última vez que um público-alvo foi atualizado**
* Obtenha insights sobre o **tempo necessário para produzir um público-alvo** no Customer Journey Analytics. E a quantidade de tempo que levou para que o público-alvo aparecesse na Real-time Customer Platform para fins de ativação.
* Veja se os públicos-alvo no Customer Journey Analytics estão **sendo usados ativamente pela Real-time Customer Platform**. Ou (de preferência) qualquer aplicativo da Experience Platform que consuma os públicos-alvo criados pelo Customer Journey Analytics.

Se você tiver acesso de [Exibição de público-alvo](/help/technotes/access-control.md#user-level-access), poderá exibir públicos-alvo. Se você tiver acesso para [criação de público-alvo](/help/technotes/access-control.md#user-level-access), será possível editar e excluir públicos-alvo.

## Visualizar públicos-alvo na lista de públicos-alvo

A lista de públicos-alvo ➊ mostra os públicos-alvo existentes.

![Gerenciador de públicos-alvo](assets/audiences-manager.png)

Para ver a lista de públicos-alvo:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo publicados]**.

1. (Opcional) Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar quais colunas exibir.

1. (Opcional) Pesquise um público-alvo usando a opção ![Pesquisar](/help/assets/icons/Search.svg).

   As colunas a seguir fornecem informações sobre cada público-alvo:

   | Coluna | Descrição |
   | --- | --- |
   | ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando um ou mais públicos-alvo são selecionados, uma barra de ação azul é exibida na parte inferior da interface Públicos-alvo. Consulte [Ações](#actions) para obter mais detalhes. |
   | **[!UICONTROL Título e descrição]** | O título e a descrição inseridos ao criar o público-alvo. |
   | **[!UICONTROL Visualização de dados]** | A visualização de dados na qual esse público-alvo foi criado. |
   | **[!UICONTROL Tamanho do público-alvo]** | O número total de pessoas neste público-alvo. |
   | **[!UICONTROL Proprietário]** | O proprietário do público-alvo: a pessoa que o criou. |
   | **[!UICONTROL Frequência de atualização]** | O intervalo de atualização configurado quando o público-alvo foi criado. |
   | **[!UICONTROL Tags]** | Qualquer tag aplicada a esse público-alvo. |
   | **[!UICONTROL Status de publicação]** | Pode mostrar ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Pronto]**, ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Em andamento]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Erro]**. |
   | **[!UICONTROL Última atualização]** | Carimbo de data e hora da última atualização do público-alvo. |
   | **[!UICONTROL Última modificação]** | Carimbo de data e hora da última edição ou modificação do público-alvo. |

## Editar públicos-alvo

É possível editar as configurações de um público-alvo a qualquer momento. Após editar um público-alvo (seja um público-alvo único ou recorrente), é necessário publicá-lo novamente.

Para editar um público-alvo:

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Públicos-alvo publicados]**.

   A página Públicos-alvo é exibida.

1. Selecione o título do público-alvo que deseja editar.

   A caixa de diálogo **[!UICONTROL Editar público-alvo]** é exibida.

1. É possível atualizar qualquer um dos campos disponíveis do público-alvo. Para obter informações sobre os campos que você pode atualizar, consulte [Construtor de públicos-alvo](/help/components/audiences/publish.md#audience-builder) no artigo [Criar e publicar públicos-alvo](/help/components/audiences/publish.md).

1. Selecione **[!UICONTROL Republicar]**.

## Ações

As ações a seguir são comuns no Gerenciador de projetos agendados. Você pode selecionar ações no menu de contexto:

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![Rótulos](/help/assets/icons/Labels.svg) | **[!UICONTROL Tag]** | Marque os públicos-alvo selecionados. Na caixa de diálogo **[!UICONTROL Atualizar tags: *nome do público-alvo *]**, selecione as tags no menu suspenso ou digite uma ou mais tags. Selecione **[!UICONTROL Salvar ]** para salvar. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua os públicos-alvo selecionados. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomeie o público-alvo selecionado. Use a caixa de diálogo **[!UICONTROL Renomear: *nome do público-alvo *]** para renomear o público-alvo e selecione **[!UICONTROL Salvar ]** para salvar. |

As seguintes ações estão disponíveis na barra de ação azul ao selecionar um ou mais projetos agendados.

| Ícone | Ação | Descrição |
|:---:|---|---|
| ![Fechar](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selecionado]** | Selecione para desmarcar os públicos-alvo selecionados. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua os públicos-alvo selecionados. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar para CSV]** | Exportar os públicos-alvo selecionados para um arquivo chamado `audiences.csv`. |

## Filtrar a lista de públicos-alvo

Você pode filtrar a [Lista de públicos-alvo](#audiences-list) usando o painel de filtros ➋. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

![Gerenciador de públicos-alvo](assets/audiences-manager.png)

O painel de filtro consiste nas seções a seguir.

### Visualização de dados

| Visualização de dados | Descrição |
|---|---|
| ![Proprietários](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | A seção **[!UICONTROL Exibição de dados]** permite filtrar exibições de dados. <ul><li>Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) para procurar exibições de dados que deseja usar para filtrar.</li><li>É possível selecionar mais de uma visualização de dados.</li></ul> |

### Proprietários

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) para procurar proprietários que deseja usar para filtrar.</li><li>É possível selecionar mais de um proprietário. </li></ul> |

## Frequência de atualização

| Frequência de atualização | Descrição |
|---|---|
| ![Frequência de atualização](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | A seção **[!UICONTROL Frequência de atualização]** permite filtrar por frequência de atualização. <ul><li>Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) para pesquisar a frequência de atualização que deseja usar para filtrar.</li><li>Somente as frequências de atualização definidas para os públicos-alvo<br/> na [Lista de públicos-alvo](#audiences-list) são mostradas como opções disponíveis.</li></ul> |


### Tags

| Tags | Descrição |
|---|---|
| ![Tags](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar por tags. <ul><li>Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) para procurar as tags que deseja usar para filtrar. |
