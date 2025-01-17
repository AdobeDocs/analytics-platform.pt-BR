---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 23%

---

# Criar um fluxo de dados para usar com o Customer Journey Analytics

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Uma sequência de dados representa a configuração do lado do servidor ao implementar os SDKs móveis e da Web da Adobe Experience Platform. Ao coletar dados com os SDKs da Adobe Experience Platform, os dados são enviados para a Rede de borda da Adobe Experience Platform. É o fluxo de dados que determina para quais serviços esses dados são encaminhados.

Na configuração, você deseja configurar a sequência de dados para enviar os dados coletados para seu conjunto de dados no Adobe Experience Platform.

>[!NOTE]
>
>As etapas a seguir são necessárias somente para implementações do Adobe Analytics que usam o AppMeasurement ou a extensão do Analytics (tags).
>
>Se sua implementação do Adobe Analytics usar a extensão Web SDK ou Web SDK, a sequência de dados já existe em seu ambiente do Adobe Analytics.

Para configurar seu armazenamento de dados:

1. No Adobe Experience Platform, selecione **[!UICONTROL Datastreams]** de [!UICONTROL DATA COLLECTION] no painel esquerdo.

1. Selecione **[!UICONTROL Novo fluxo de dados]**.

1. Nomeie e descreva o armazenamento de dados. Selecione o esquema na lista [!UICONTROL Esquema do evento].

   ![Novo fluxo de dados](assets/new-datastream.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
