---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 51%

---

# Criar uma sequência de dados para usar com o Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="Criar uma sequência de dados na Adobe Experience Platform"
>abstract="Uma sequência de dados é um local intermediário que transmite seus dados para todos os serviços configurados. Crie esse local na Adobe Experience Platform.<br><br>A criação inicial de uma sequência de dados na interface da Platform leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Uma sequência de dados representa a configuração do lado do servidor ao implementar os SDKs móveis e da Web da Adobe Experience Platform. Ao coletar dados com os SDKs da Adobe Experience Platform, os dados são enviados para a Rede de borda da Adobe Experience Platform. É o fluxo de dados que determina para quais serviços esses dados são encaminhados.

Na configuração, você deseja configurar a sequência de dados para enviar os dados coletados para seu conjunto de dados no Adobe Experience Platform.

>[!NOTE]
>
>As etapas a seguir são necessárias somente para implementações do Adobe Analytics que usam AppMeasurement ou a extensão do Analytics (tags).
>
>Se sua implementação do Adobe Analytics usar a extensão Web SDK ou Web SDK, a sequência de dados já existe em seu ambiente do Adobe Analytics.

Para configurar seu armazenamento de dados:

1. No Adobe Experience Platform, selecione **[!UICONTROL Datastreams]** de [!UICONTROL DATA COLLECTION] no painel esquerdo.

1. Selecione **[!UICONTROL Novo fluxo de dados]**.

1. Nomeie e descreva o armazenamento de dados. Selecione o esquema na lista [!UICONTROL Esquema do evento].

   ![Novo fluxo de dados](assets/new-datastream.png)

1. Selecione **[!UICONTROL Salvar]**.

{{upgrade-final-step}}
