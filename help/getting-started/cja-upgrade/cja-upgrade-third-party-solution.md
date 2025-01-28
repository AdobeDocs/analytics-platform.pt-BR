---
title: Atualização de uma solução de análise de terceiros para o Customer Journey Analytics
description: Saiba como atualizar de uma solução de análise de terceiros para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 12%

---

# Atualização de uma solução de análise de terceiros para o Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="Um produto de análise de terceiros"
>abstract="Uma implementação que coleta dados para um produto de análise de terceiros, como Google Analytics. Selecionar essa opção desativa várias opções no questionário que não se aplicam ao atualizar para o Customer Journey Analytics de um produto de análise de terceiros."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

O processo recomendado de atualização de uma solução de análise de terceiros para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido para o Customer Journey Analytics. Em conjunto com o Web SDK, a Adobe também recomenda assimilar dados históricos da solução de análise de terceiros na Adobe Experience Platform.

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

Use o processo a seguir ao mudar para o Customer Journey Analytics de uma solução de análise de terceiros, como Google Analytics:

1. ...


Entre em contato com o(a) representante da Adobe se precisar de suporte ou conselhos e orientações específicas.

| Solução analítica existente | Descrição | Caminhos de atualização disponíveis |
|---------|----------|----------|
| AppMeasurement | O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics.<p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrar o Adobe Analytics para o SDK da web</li><li>[Conector Source do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extensão do Adobe Analytics (tags) | <p>Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.</p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando a extensão do Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrar o Adobe Analytics para o SDK da web</li><li>[Conector Source do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | O Experience Platform Web SDK é o método Adobe recomendado para implementar o Adobe Analytics. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o Edge Network de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| Extensão Experience Platform Web SDK (tags) | O Experience Platform Web SDK é o método Adobe recomendado para implementar o Adobe Analytics para dados da Web. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| Experience Platform Mobile SDK | O Experience Platform Mobile SDK é o método Adobe recomendado para implementar o Adobe Analytics para dados móveis. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado.<p>O Adobe Experience Platform Mobile SDK ajuda a potencializar as soluções e os serviços da Experience Cloud Adobe em seus aplicativos móveis. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| API de inserção de dados em massa | A API de inserção de dados em massa (BDIA) é um recurso do Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos, em vez de usar bibliotecas do lado do cliente, como o AppMeasurement. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [API de Inserção de Dados em Massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API e Edge Network do servidor Adobe Experience Platform Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}