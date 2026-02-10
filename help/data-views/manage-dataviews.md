---
title: Gerenciar visualizações de dados
description: Saiba como gerenciar visualizações de dados.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: c7cf7250f30e2f6023aa7690391aea149ba12eff
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 10%

---

# Gerenciar visualizações de dados


Depois de [criar ou editar uma ou mais visualizações de dados](/help/data-views/create-dataview.md), você poderá gerenciá-las em **[!UICONTROL Visualizações de dados]**.

Selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]** no menu principal do Customer Journey Analytics.

A interface de **[!UICONTROL Visualizações de dados]** mostra uma tabela de todas as visualizações de dados disponíveis.

![Interface de visualizações de dados](/help/data-views/assets/data-views.png)

As seguintes colunas e ícones estão disponíveis na tabela:

| Coluna ou ícone | Descrição |
| --- | --- |
| **[!UICONTROL Nome]** | O nome da visualização dos dados. |
| ![Informações](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | Para exibir informações sobre a exibição de dados, selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) ao lado do nome da exibição de dados.<br/>Uma janela pop-up exibe detalhes sobre a visualização de dados. |
| ![Mais](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | Selecione ![Mais](/help/assets/icons/More.svg) para abrir um menu de contexto. Você pode selecionar:<br/>![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para [editar](#edit-data-views) uma exibição de dados.<br/>![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** para [copiar uma exibição de dados](#copy-data-views).<br/>![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** para [excluir](#delete-data-views) uma exibição de dados.<br/>![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export para CSV]** para [exportar os detalhes do modo de exibição de dados para um arquivo CSV](#export-data-views-to-csv).<br/>![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Create project]** to [create a new Workspace project](#create-project-from-data-views) for the data view.<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Habilitar para o Data Insights Agent]** para habilitar uma exibição de dados para o Data Insights Agent.<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Desabilitar para o Data Insights Agent]** desabilitar uma exibição de dados para o Data Insights Agent. |
| **[!UICONTROL Conexão]** | O nome da conexão associada à visualização de dados. |
| **[!UICONTROL Sandbox]** | O nome da sandbox associada à visualização de dados. |
| **[!UICONTROL Proprietário]** | O proprietário da visualização de dados. |
| **[!UICONTROL Data Insights Agent]** ![InfoOutline](/help/assets/icons/InfoOutline.svg) | Indica se o [Data Insights Agent](/help/data-analysis-ai.md) está **[!UICONTROL Habilitado]** ou **[!UICONTROL Desabilitado]** para a exibição de dados. <br/>Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para mostrar um pop-up com **[!UICONTROL Status do Data Insights Agent]** em suas visualizações de dados. <br/>![uso do Data Insights Agent](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL Integrações]** | Listar integrações com outras soluções. Por exemplo: Adobe Audience Analysis, Content Analytics, Brand Concierge, Journey Optimizer, GenStudio e Usage Analytics. |
| **[!UICONTROL Usar no CJA]** | Indica se a visualização de dados é usada no Customer Journey Analytics. Este valor é apenas **[!UICONTROL Desativado]** para visualizações de dados que são geradas automaticamente como parte da integração com o Adobe Journey Optimizer. |
| **[!UICONTROL Data de criação]** | O carimbo de data e hora quando a visualização de dados foi criada. |
| **[!UICONTROL Última modificação]** | O carimbo de data e hora quando a visualização de dados foi modificada mais recentemente. |

Para configurar quais colunas serão exibidas na tabela, selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem mostradas. Em seguida, selecione **[!UICONTROL Aplicar]**.


## Pesquisar visualizações de dados

Você pode pesquisar rapidamente por uma visualização de dados usando a caixa ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg).

## Filtrar visualizações de dados

Para aplicar um filtro à lista de visualizações de dados, selecione o ícone ![Filtrar](/help/assets/icons/Filter.svg) e escolha entre as seguintes opções de filtro:

| Opção de filtro | Descrição |
|---------|----------|
| **[!UICONTROL Conexões]** | Somente as visualizações de dados associadas às conexões selecionadas são exibidas. |
| **[!UICONTROL Proprietário]** | Somente as visualizações de dados pertencentes às pessoas selecionadas são exibidas. |
| **[!UICONTROL Sandbox]** | Somente as visualizações de dados disponíveis nas sandboxes selecionadas são exibidas. |
| **[!UICONTROL Integrações]** | Somente as visualizações de dados com integrações selecionadas são exibidas. |
| **[!UICONTROL Usar no CJA]** | Selecione **[!UICONTROL Em]** para mostrar apenas exibições de dados habilitadas para uso com o Customer Journey Analytics. Selecione **[!UICONTROL Desativado]** para mostrar somente visualizações de dados que ainda não estão habilitadas para uso com o Customer Journey Analytics. |


Selecione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar o painel de filtros.

## Criar uma visualização de dados

Para [criar uma nova visualização de dados](/help/data-views/create-dataview.md), selecione **[!UICONTROL Criar nova visualização de dados]**.


## Editar visualizações de dados

Se você deseja [editar uma visualização de dados](/help/data-views/create-dataview.md):

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione a linha de visualização de dados.
1. Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** na barra de ações azul.


## Copiar visualizações de dados

Se quiser copiar uma visualização de dados:

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** no menu de contexto.

Como alternativa, você pode:

1. Selecione uma ou mais linhas de visualização de dados.
1. Selecione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** na barra de ações azul.

A exibição de dados é copiada e adicionada à lista com **[!UICONTROL (Cópia)]** anexada ao nome.


## Excluir visualizações de dados

Se quiser excluir uma visualização de dados:

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** no menu de contexto.

Como alternativa, você pode:

1. Selecione uma ou mais linhas de visualização de dados.
1. Selecione ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** na barra de ações azul.

Ao excluir uma ou mais visualizações de dados, um painel **[!UICONTROL Excluir visualização de dados]** indica quais projetos são afetados.

![Excluir visualização de dados](/help/data-views/assets/delete-data-view.png)


* Em ➊ **[!UICONTROL Confirmação]**, as implicações da exclusão das visualizações de dados são mostradas.
* Selecione **[!UICONTROL Excluir]** para excluir as visualizações de dados permanentemente. Selecione **[!UICONTROL Cancelar]** para cancelar.


## Exportar visualizações de dados para CSV

É possível exportar uma visualização de dados para um arquivo CSV.

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar para CSV]** no menu de contexto.

Como alternativa, você pode:

1. Selecione uma ou mais linhas de visualização de dados.
1. Selecione ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export para CSV]** na barra de ação azul.

Detalhes das visualizações de dados selecionadas são exportados para um arquivo CSV chamado `Data views List (x).csv` na pasta Downloads do seu navegador.


## Criar projeto a partir de visualizações de dados

Você pode criar um projeto do Workspace diretamente na interface de Visualizações de dados.

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Criar projeto]** no menu de contexto.

Como alternativa, você pode:

1. Selecione uma linha de visualização de dados.
1. Selecione ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL Criar projeto]** na barra de ação azul.


## Ativar ou desativar visualizações de dados para o Data Insights Agent

Você pode habilitar ou desabilitar uma exibição de dados para o [Data Insights Agent](/help/data-analysis-ai.md).

1. Selecione ![Mais](/help/assets/icons/More.svg) ao lado do nome da exibição de dados.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable para Data Insights Agent]** ou ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable para Data Insights Agent]** no menu de contexto.

Como alternativa, você pode:

1. Selecione uma ou mais linhas de visualização de dados que estão desativadas ou ativadas para o Data Insights Agent.
1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Enable para Data Insights Agent]** ou ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL Disable para Data Insights Agent]** na barra de ação azul.
