---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 35%

---

# Criar um fluxo de dados para usar com o Customer Journey Analytics

>[!NOTE]
>
>Esta documentação deve ser usada após o preenchimento do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga as etapas desta página somente após concluir todas as etapas anteriores que foram geradas dinamicamente para sua organização.
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização que foram geradas dinamicamente para sua organização no [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Uma sequência de dados representa a configuração do lado do servidor ao implementar os SDKs móveis e da Web da Adobe Experience Platform. Ao coletar dados com os SDKs da Adobe Experience Platform, os dados são enviados para a Rede de borda da Adobe Experience Platform. É o fluxo de dados que determina para quais serviços esses dados são encaminhados.

Em sua configuração, você deseja que os dados coletados do site sejam enviados para seu conjunto de dados na Adobe Experience Platform.

Para configurar seu armazenamento de dados:

1. No Adobe Experience Platform, selecione **[!UICONTROL Datastreams]** de [!UICONTROL DATA COLLECTION] no painel esquerdo.

1. Selecione **[!UICONTROL Novo fluxo de dados]**.

1. Nomeie e descreva o armazenamento de dados. Selecione o esquema na lista [!UICONTROL Esquema do evento].

   ![Novo fluxo de dados](assets/new-datastream.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continue seguindo as etapas de atualização que foram geradas dinamicamente para sua organização do [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

