---
title: Criar Ou Editar Uma Configuração De Insights De Conversa
description: Saiba como definir as configurações de Insights de conversa.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 8%
---
# Criar ou editar configurações


Os Insights de conversa permitem analisar conversas (de modelos de idioma grandes (LLM) ou humanos) em escala e contextualizar essas conversas na jornada completa do cliente. Por meio dos Insights de conversa, é possível entender o impacto dos representantes nos resultados reais do usuário.

Por meio da interface de configuração do Conversation Insights, é possível criar ou editar rapidamente uma configuração e os artefatos associados (conexão, visualizações de dados e muito mais).

Ao criar ou editar uma configuração de Insights de conversa, você especifica a sandbox e os conjuntos de dados de evento que contêm prompts, respostas e dados de feedback. Você também seleciona a conexão do Customer Journey Analytics à qual deseja adicionar esses conjuntos de dados. E a visualização de dados à qual você deseja adicionar as métricas e dimensões do Conversation Insights.

Somente administradores do sistema podem criar ou editar configurações de Insights de conversa.

Você cria ou edita configurações da [interface de Configurações de Insights de Conversa](./conversation-insights-manage.md).

## Restaurar o conjunto de dados combinados ausente

Se você editar uma configuração e o conjunto de dados misturado que foi gerado para a configuração não existir mais, selecione **[!UICONTROL Restaurar]** para regenerar o conjunto de dados misturado.


## Etapas de configuração

Para cada configuração:

1. Na seção **[!UICONTROL Detalhes]**, especifique as seguintes informações:

   ![Detalhes de Insights de Conversa](assets/conversation-insights-configuration-details.png)

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Nome]** | Especifique um nome para a configuração. |
   | **[!UICONTROL Sandbox]** | Selecione a sandbox da Experience Platform que contém os conjuntos de dados de eventos de prompts, respostas e comentários que você deseja adicionar à sua conexão. |

1. Na seção **[!UICONTROL Conjuntos de dados]**, especifique as seguintes informações:

   ![Conjuntos de Dados de Insights de Conversa](assets/conversation-insights-configuration-datasets.png)

   | Campo | Descrição |
   |---------|----------|
   | **[!UICONTROL Solicita o conjunto de dados do evento]** | Selecione o conjunto de dados que contém os dados do evento de prompts. |
   | **[!UICONTROL Conjunto de dados de evento de respostas]** | Selecione o conjunto de dados que contém os dados do evento de respostas. |
   | **[!UICONTROL Conjunto de dados do evento de comentários]** | Selecione o conjunto de dados que contém os dados do evento de feedback. |

1. Na seção **[!UICONTROL Conexão]**, se nenhuma conexão já estiver configurada, use **[!UICONTROL Selecionar uma conexão]** para selecionar uma conexão.

   ![Conexão com os Insights de Conversa](assets/conversation-insights-configuration-connection.png)

   Se uma conexão já estiver configurada, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para selecionar outra conexão.

   ![Editar Conexão de Insights de Conversa](assets/conversation-insights-configuration-edit-connection.png)

   Na caixa de diálogo **[!UICONTROL Selecionar uma conexão]**:

   ![Selecionar Conexão dos Insights de Conversa](assets/conversation-insights-configuration-select-connection.png)

   1. Marque a caixa de seleção ao lado da conexão à qual você deseja adicionar os conjuntos de dados de eventos de prompts, respostas e feedback.
   1. Selecione **[!UICONTROL Usar conexão]**.

   * Para pesquisar na lista de conexões para seleção, use o campo ![Pesquisar](/help/assets/icons/Search.svg).
   * Para definir quais colunas exibir na tabela, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem mostradas. Em seguida, selecione **[!UICONTROL Aplicar]**.

1. Na seção **[!UICONTROL Visualizações de dados]**, se nenhuma visualização de dados já estiver configurada, selecione **[!UICONTROL Selecionar visualizações de dados]** para selecionar visualizações de dados.

   Se as visualizações de dados já estiverem configuradas, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar seleção de visualização de dados]** para reconfigurar a seleção de visualizações de dados.

   Na caixa de diálogo **[!UICONTROL Selecionar várias visualizações de dados]**:

   ![Visões de dados de Seleção de Insights de Conversa](assets/conversation-insights-configuration-select-data-views.png)

   1. Selecione uma ou mais visualizações de dados que deseja usar para a configuração de Insights de conversa.

   1. Selecione **[!UICONTROL Usar visualizações de dados]** para usar as visualizações de dados. Selecione Cancelar para cancelar.

   * Para pesquisar na lista de visualizações de dados para seleção, use o campo ![Pesquisa](/help/assets/icons/Search.svg).
   * Para definir quais colunas exibir na tabela, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg). Na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem mostradas. Em seguida, selecione **[!UICONTROL Aplicar]**.

1. Para concluir a configuração:

   * Selecione **[!UICONTROL Descartar]** para uma nova configuração que não foi criada.

   * Selecione **[!UICONTROL Salvar para mais tarde]** para obter uma nova configuração que você deseja salvar, mas que não deseja criar o artefato para (atualizações em visualizações de dados, por exemplo). Portanto, é possível revisitar a configuração posteriormente e concluir a criação real da configuração.

   * Selecione **[!UICONTROL Criar]** para criar a nova configuração.

   * Selecione **[!UICONTROL Salvar]** para salvar a configuração modificada.

   * Selecione **[!UICONTROL Restaurar]** para restaurar a configuração e regenerar um novo conjunto de dados mesclado para a configuração.

   * Selecione **[!UICONTROL Sair]** para ignorar qualquer alteração na configuração.


## Verificação de visualização de dados

(Explique as métricas e dimensões que você vê nos conjuntos de dados relevantes)


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->