---
description: Use a visualização de resumos de conversa para resumir as conversas.
title: Resumo de conversas
feature: Visualizations
role: User
hide: true
source-git-commit: 113a215e26092c65d6eaf2c321f60d3f3a5015b8
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%
---
# Resumos de conversa {#conversation-summaries}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_button"
>title="Resumos de conversa"
>abstract="Crie uma visualização que resume um grupo filtrado de conversas."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_panel"
>title="Resumos de conversa"
>abstract="Resumir um grupo filtrado de conversas. Controlar o comprimento do resumo. Consulte declarações de clientes para validar a precisão dos sinais extraídos. Selecione uma cotação para abrir a repetição completa da conversa."

{{release-limited-testing}}

A visualização ![Resumir](/help/assets/icons/Summarize.svg) **[!UICONTROL Resumos da conversa]** permite resumir um grupo filtrado de conversas.

A visualização mostra um resumo da métrica selecionada (por exemplo, Conversas) e exibe subtópicos ou comentários textuais quando você configura a visualização para incluir subtópicos.


## Criar e configurar {#conversation-summaries-create-configure}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel"
>title="Usar modelo de atribuição não-padrão"
>abstract="Ativar um modelo de atribuição não padrão para essa métrica."

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_usenondefaultattributionmodel_disabled"
>title="Usar modelo de atribuição não-padrão"
>abstract="Modelos de atribuição não padrão não estão disponíveis para esta métrica."

Para criar e configurar uma visualização de **[!UICONTROL Resumos da conversa]**:

1. Adicionar uma visualização de ![Resumir](/help/assets/icons/Summarize.svg) **[!UICONTROL Resumos da conversa]**. Consulte [Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Na configuração de visualização dos **[!UICONTROL resumos da conversa]**:

   1. Selecione uma **[!UICONTROL métrica]**. Por exemplo: **[!UICONTROL Conversas]**.
   1. Opcionalmente, se quiser usar um modelo não padrão [atribuição](/help/analysis-workspace/attribution/models.md) na métrica, selecione **[!UICONTROL Usar modelo de atribuição não padrão]** e selecione **[!UICONTROL Modelo]**, **[!UICONTROL Contêiner]** e **[!UICONTROL Janela de pesquisa]**.
   1. Opcionalmente, é possível aplicar um segmento à visualização. Selecione um segmento no menu suspenso **[!UICONTROL Segmentos]**.

1. Selecione **[!UICONTROL Build]** para criar a visualização. Selecione **[!UICONTROL Redefinir]** para redefinir os valores de configuração para os padrões. Selecione **[!UICONTROL Cancelar]** para cancelar a configuração.

Para reconfigurar a visualização dos **[!UICONTROL Resumos da conversa]**, selecione ![Editar](/help/assets/icons/Edit.svg) ao lado de **[!UICONTROL Métrica: _métrica_]**ou **[!UICONTROL Métrica:_métrica_]** | **[!UICONTROL Segmentos: _segmentos_]**.

## Usar

Para usar a visualização:

>[!BEGINTABS]

>[!TAB Subtópicos]

![Subtópicos](assets/conversation-summaries-subtopics.png)

>[!TAB Comentários textuais]

![Comentários textuais](assets/conversation-summaries-verbatimcomments.png)

>[!ENDTABS]

* Se você tiver [subtópicos incluídos](#settings), selecione **[!UICONTROL Subtópicos]** para exibir subtópicos ou **[!UICONTROL Comentários integrais]** para exibir comentários integrais.
* Quando você tiver selecionado **[!UICONTROL Comentários textuais]**, selecione ![FileSearch](/help/assets/icons/FileSearch.svg) para abrir uma nova visualização de [**[!UICONTROL Revisão da conversa]**](./conversation-review.md) para a conversa específica da qual o comentário textual faz parte.

## Configurações

As [configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings) específicas a seguir estão disponíveis.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Comprimento do resumo]** | Especifique o comprimento do resumo. Você pode selecionar entre **[!UICONTROL Short]** ou **[!UICONTROL Long]**. |
| **[!UICONTROL Incluir subtópicos]** | Selecione **[!UICONTROL Incluir subtópicos]** para exibir subtópicos na visualização. Use **[!UICONTROL Número máximo de subtópicos]** para configurar o número máximo de subtópicos a serem exibidos. |
