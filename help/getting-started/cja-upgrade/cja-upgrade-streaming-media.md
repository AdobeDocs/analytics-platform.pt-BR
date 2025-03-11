---
title: Configurar a coleção de mídia de transmissão para o Customer Journey Analytics
description: Saiba como configurar a coleção de mídia de transmissão para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Configurar a coleção de mídia de transmissão para o Customer Journey Analytics {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="Configuração e implementação do Media Edge"
>abstract="Se você planeja usar a Coleção de mídia de transmissão com o Customer Journey Analytics, é necessário fazer seleções específicas em determinadas etapas do processo de atualização. Por exemplo, você precisa adicionar o grupo de campos Detalhes de interações do MediaAnalytics ao esquema, ativar o Media Analytics na sequência de dados e muito mais."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Assim como no Adobe Analytics, a coleção de mídia de transmissão pode ser usada para coletar dados de mídia de transmissão para uso no Customer Journey Analytics. Se você usa a coleção de mídia de streaming com o Adobe Analytics, deve incluí-la em seus planos de atualização para o Customer Journey Analytics.

Conforme você percorre as etapas para atualizar do Adobe Analytics para o Customer Journey Analytics, faça as seguintes seleções para levar em conta os dados da coleção de mídia de transmissão:

* Ao criar o esquema para o Customer Journey Analytics, inclua o grupo de campos `MediaAnalytics Interaction Details`.

  Para obter mais informações sobre como adicionar este grupo de campos, consulte [Configurar o esquema no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar o esquema, consulte [Criar um esquema personalizado para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* Ao configurar a sequência de dados para o Customer Journey Analytics, ative o Media Analytics.

  Para obter mais informações sobre como habilitar esta opção, consulte [Configurar uma sequência de dados no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar a sequência de dados, consulte [Criar uma sequência de dados para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

  >[!NOTE]
  >
  >Se sua implementação do Adobe Analytics já estiver usando o Experience Platform Web SDK, essa etapa não será necessária.

* Ao criar uma visualização de dados para o Customer Journey Analytics, inclua os campos de esquema necessários para a Coleção de mídia de transmissão.

  Mapeie esses campos de esquema para os valores corretos no objeto XDM.

  Para obter mais informações sobre os campos obrigatórios, consulte [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) no Guia de Coleção de Mídia de Streaming.

  Para obter informações sobre como criar a exibição de dados, consulte [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
