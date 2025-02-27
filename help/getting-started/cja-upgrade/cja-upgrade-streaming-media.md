---
title: Configurar a coleção de mídia de transmissão para o Customer Journey Analytics
description: Saiba como configurar a coleção de mídia de transmissão para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Configurar a coleção de mídia de transmissão para o Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configuração e implementação do Media Edge"
>abstract="É possível configurar a Coleção de mídia de streaming do Adobe para usar o Experience Platform Edge e disponibilizar dados no Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

As etapas para implementar a Coleção de mídia de transmissão no Customer Journey Analytics diferem dependendo de sua implementação atual da Coleção de mídia de transmissão no Adobe Analytics.

A coleção de mídia de transmissão pode ser implementada no Adobe Analytics de uma das seguintes maneiras:

* [Implementações do Edge Network para a coleção de mídia de transmissão](#edge-network-implementations)

+++ Exibir infográfico

  ![Implementação de streaming de mídia no Edge](assets/streaming-media-edge.png)

+++

* [Implementações somente do Adobe Analytics para a coleção de mídia de transmissão](#adobe-analytics-only-implementations)

+++ Exibir infográfico

  ![Implementação somente do Analytics](assets/analytics-implementation.png)

+++

Para obter mais informações sobre as diferenças entre esses métodos de implementação, consulte [Implementar a coleção de mídia de streaming](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) no Guia de coleção de mídia de streaming.

## Implementações do Edge Network para a coleção de mídia de transmissão

Se a Coleção de Mídia de Streaming estiver [implementada usando a Edge Network na implementação do Adobe Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), isso significa que algumas etapas necessárias para atualizar a Coleção de Mídia de Streaming para o Customer Journey Analytics já foram concluídas como parte da implementação do Adobe Analytics. Veja a seguir as etapas concluídas:

* [Configurar o esquema no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Criar um conjunto de dados no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configurar uma sequência de dados no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

As seguintes etapas adicionais precisam ser concluídas como parte da atualização para o Customer Journey Analytics:

>[!NOTE]
>
>Ao concluir as etapas de atualização do Customer Journey Analytics, certifique-se de usar o esquema, o conjunto de dados e o fluxo de dados da implementação da Coleção de mídia de transmissão no Adobe Analytics.

* [Criar uma conexão no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Implementações somente do Adobe Analytics para a coleção de mídia de transmissão

Se a Coleção de mídia de streaming for [implementada usando uma implementação somente Adobe Analytics em seu ambiente Adobe Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), significa que os dados de mídia de streaming ainda não irão para o Edge Network.

À medida que você cria o esquema, o conjunto de dados, a sequência de dados, a conexão e a visualização de dados como parte de sua atualização do Adobe Analytics para o Customer Journey Analytics, faça as seguintes seleções para levar em conta os dados da coleção de mídia de transmissão:

* Ao criar o esquema para o Customer Journey Analytics, inclua o grupo de campos `MediaAnalytics Interaction Details`.

  Para obter mais informações sobre como adicionar este grupo de campos, consulte [Configurar o esquema no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar o esquema, consulte [Criar um esquema personalizado para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Ao configurar a sequência de dados para o Customer Journey Analytics, ative o Media Analytics.

  Para obter mais informações sobre como habilitar esta opção, consulte [Configurar uma sequência de dados no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar a sequência de dados, consulte [Criar uma sequência de dados para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* Ao criar uma visualização de dados para o Customer Journey Analytics, inclua os campos de esquema necessários para a Coleção de mídia de transmissão.

  Mapeie esses campos de esquema para os valores corretos no objeto XDM.

  Para obter mais informações sobre os campos obrigatórios, consulte [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar a exibição de dados, consulte [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).


