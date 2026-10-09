---
title: Criar uma sequência de dados para usar com o Customer Journey Analytics
description: Saiba como criar uma sequência de dados para seus dados do Web SDK ao atualizar do Adobe Analytics para o Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 614a234f8db9783dacaf9d2f3c21a5afd5ea02ef
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 91%
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

Uma sequência de dados representa a configuração do lado do servidor ao implementar os SDKs móveis e da Web da Adobe Experience Platform. Ao coletar dados com os SDKs da Adobe Experience Platform, os dados são enviados para a Rede de borda da Adobe Experience Platform. É a sequência de dados que determina para quais serviços os dados são encaminhados.

Na configuração, você deseja configurar a sequência de dados para enviar os dados coletados para seu conjunto de dados na Adobe Experience Platform.

>[!NOTE]
>
>As etapas a seguir são necessárias somente para implementações do Adobe Analytics que usam AppMeasurement ou a extensão do Analytics (tags).
>
>Se sua implementação do Adobe Analytics usar o SDK da web ou a extensão do SDK da web, a sequência de dados já existe em seu ambiente do Adobe Analytics.

Para configurar seu armazenamento de dados:

1. Na Adobe Experience Platform, selecione **[!UICONTROL Sequências de dados]** em [!UICONTROL COLEÇÃO DE DADOS] no painel esquerdo.

1. Selecione **[!UICONTROL Novo fluxo de dados]**.

1. Nomeie e descreva o armazenamento de dados. Selecione o esquema na lista [!UICONTROL Esquema do evento].

   ![Novo fluxo de dados](assets/new-datastream.png)

1. Selecione **[!UICONTROL Salvar]**.

{{upgrade-final-step}}
