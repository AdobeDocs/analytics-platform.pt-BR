---
title: Selecionar Uma Visualização De Dados No Report Builder
description: Saiba como selecionar uma visualização de dados no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Selecionar uma visualização de dados

Você pode selecionar uma visualização de dados no menu suspenso ou selecionar uma visualização de dados de uma célula e atualizar automaticamente seu bloco de dados com uma nova visualização de dados.

## Selecionar visualização de dados de uma célula

Selecionar uma visualização de dados de uma célula facilita a atualização de blocos de dados usando visualizações de dados diferentes. Em vez de criar relatórios totalmente novos com blocos de dados separados, você pode atualizar blocos de dados com uma visualização de dados selecionada de uma célula.

Selecionar uma visualização de dados em uma célula é útil quando você tem:

* Várias visualizações de dados que são semelhantes ou idênticas entre si na estrutura.
* Formatos de blocos de dados complicados que incluem componentes e layouts personalizados.

Para selecionar uma visualização de dados de uma célula, primeiro crie um bloco de dados e atribua várias visualizações de dados a uma célula fora do bloco de dados. Em seguida, use o painel **[!UICONTROL Visualização de dados da célula]** para atualizar seus blocos de dados de visualizações de dados diferentes.

1. Criar um bloco de dados. Para obter informações sobre como criar um bloco de dados, consulte [Criar um bloco de dados](/help/report-builder/create-a-data-block.md).

1. Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) em **[!UICONTROL Data views]**.

1. Selecione uma célula usando ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) fora do bloco de dados.

1. Adicione uma ou mais exibições de dados da **[!UICONTROL Selecione as exibições de dados a serem adicionadas à exibição de dados da célula]** usando a função arrastar e soltar. Como alternativa, você pode selecionar duas vezes uma visualização de dados para adicioná-la à lista **[!UICONTROL Visualizações de dados incluídas]**.

   * Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) **[!UICONTROL _Selecionar visualizações de dados_]** para procurar visualizações de dados.
   * Use ![MaisPequeno](/help/assets/icons/MoreSmall.svg) para abrir um menu de contexto e mover as exibições de dados para cima ou para baixo na lista **[!UICONTROL Exibições de dados incluídas]**.
   * Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para excluir uma exibição de dados da lista **[!UICONTROL Exibições de dados incluídas]**.

   ![Selecionar exibição de dados de uma célula](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Selecione **[!UICONTROL Aplicar]** para aplicar as visualizações de dados selecionadas à célula selecionada.


## Alterar a visualização de dados de uma célula

1. Selecione o local da célula de visualização de dados em sua planilha.
1. No hub do Report Builder, selecione o link **[!UICONTROL Visualizações de dados da célula]** em **[!UICONTROL Edição rápida]**.
1. Selecione uma exibição de dados no menu suspenso **[!UICONTROL Exibição de dados]**.

   ![Alterar exibição de dados de uma célula](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Opcional, selecione **[!UICONTROL Atualizar bloco(s) de dados após a alteração]**.

1. Selecione **[!UICONTROL Aplicar]**. O Report Builder atualiza o bloco de dados com base na visualização de dados selecionada.
