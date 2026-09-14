---
title: Gerenciar Configuração de Insights de Conversa
description: Saiba como gerenciar configurações de Insights de conversa.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 6%
---
# Gerenciar configurações

Depois de [criar configurações de Insights de Conversa](/help/conversation-insights/conversation-insights-configure.md), você poderá exibir, editar ou excluir essas configurações.

Somente administradores do sistema podem gerenciar configurações de Insights de conversa.

Para obter informações sobre Insights de conversa, consulte [Visão geral sobre Insights de conversa](/help/conversation-insights/conversation-insights-overview.md).

## Exibir e filtrar configurações existentes

Para exibir as configurações existentes do Conversation Insights:

1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de Dados]** > **[!UICONTROL Configuração de Insights de Conversa]**.

   ![Visão geral das configurações do Conversation Insights](assets/conversation-insights-configurations.png)

   As seguintes colunas de informações estão disponíveis sobre cada configuração:

   * **[!UICONTROL Nome]**: o nome da configuração dos Insights de Conversa.
   * **[!UICONTROL Criado por]**: o usuário que criou a configuração.

   * **[!UICONTROL Sandbox]**: a sandbox da Experience Platform que contém o conjunto de dados do perfil adicionado à sua conexão.

   * **[!UICONTROL Conexão]**: a conexão adicionada à sua configuração.

   * **[!UICONTROL Data de criação]**: a data e a hora em que a configuração foi criada.

   * **[!UICONTROL Última modificação]**: a data em que a configuração foi modificada pela última vez.

   * **[!UICONTROL Status]**: o status da configuração. Os valores possíveis são:
     ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Concluído]**, ![StatusBlue](/help/assets/icons/StatusBlue.svg) **[!UICONTROL Pendente]** ou ![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Falha]**.

   Para configurar quais colunas serão exibidas na tabela, selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg). Na caixa de diálogo **[!UICONTROL Personalizar tabela]**, selecione as colunas a serem mostradas. Em seguida, selecione **[!UICONTROL Aplicar]**.

1. (Opcional) Para filtrar a lista de configurações, selecione ![Filtrar](/help/assets/icons/Filter.svg) e filtre por um dos seguintes critérios:

   * **[!UICONTROL Conexão]**

   * **[!UICONTROL Criado por]**

   * **[!UICONTROL Sandbox]**

   * **[!UICONTROL Status]**

## Criar uma configuração

Para criar uma nova configuração de Insights de conversa:

1. Selecione **[!UICONTROL Criar configuração]**.
1. Use a caixa de diálogo [**[!UICONTROL Criar configuração]**](./conversation-insights-configure.md) para configurar os insights da conversa.

## Editar uma configuração

Para editar uma configuração existente de Insights de conversa:

1. Siga um destes procedimentos:

   * Selecione o nome da configuração que deseja editar.
   * Marque a caixa de seleção ao lado da configuração que você deseja editar e selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** na barra de ações azul.
   * Selecione ![Mais](/help/assets/icons/More.svg) para a configuração que você deseja editar. No menu de contexto, selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

1. Use a caixa de diálogo [**[!UICONTROL Configuração / _nome da configuração_]**](./conversation-insights-configure.md) para configurar os insights da conversa.

## Excluir uma configuração

Para excluir uma configuração existente do Conversation Insights:

1. Siga um destes procedimentos:

   * Marque a caixa de seleção ao lado da configuração que você deseja excluir e selecione ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** na barra de ação azul.
   * Selecione ![Mais](/help/assets/icons/More.svg) para a configuração que você deseja editar. No menu de contexto, selecione ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]**.

1. Na caixa de diálogo **[!UICONTROL Excluir configuração]**, selecione **[!UICONTROL Excluir]** para excluir a configuração. Selecione **[!UICONTROL Cancelar]** para cancelar.
