---
title: Entenda sua implementação do Adobe Analytics e como ela afeta a atualização para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 31%

---

# Entenda sua implementação do Adobe Analytics e como ela afeta a atualização para o Customer Journey Analytics {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement (arquivo JS manual)"
>abstract="Uma implementação do JavaScript que carrega o AppMeasurement.js em uma página e envia dados para a Adobe usando o objeto s (por exemplo, s.eVar1)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Extensão do Adobe Analytics (Tags)"
>abstract="Uma implementação de tags que carrega a Coleção de dados da Adobe Experience Platform (conhecida anteriormente como Launch). A tag tem a extensão Adobe Analytics instalada."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="SDK da web (alloy.js)"
>abstract="Uma implementação do JavaScript que carrega a biblioteca do SDK da web (alloy.js) em uma página e envia dados para a Adobe usando um conteúdo JSON."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Extensão do SDK da Web (Tags)"
>abstract="Uma implementação de tags que carrega a Coleção de dados da Adobe Experience Platform (conhecida anteriormente como Launch). A tag tem a extensão do SDK da web instalada."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="API de inserção de dados"
>abstract="Uma implementação que usa a API de inserção de dados ou a API de inserção de dados em massa."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="SDK móvel"
>abstract="Uma implementação que usa o SDK da Adobe Experience Platform para dispositivos móveis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implementação desconhecida"
>abstract="Se não for a pessoa que gerencia a implementação, poderá selecionar essa opção temporariamente."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Há várias maneiras de implementar o Adobe Analytics. Ao atualizar para o Customer Journey Analytics, nem todos os caminhos de atualização estão disponíveis para todas as implementações do Adobe Analytics. No entanto, o caminho de atualização recomendado está disponível independentemente de como o Adobe Analytics é implementado em sua organização.

Use as informações abaixo para saber mais sobre sua implementação atual do Adobe Analytics e quais caminhos de atualização estão disponíveis para sua organização.

Entre em contato com o(a) representante da Adobe se precisar de suporte ou conselhos e orientações específicas.

| Implementação existente do Adobe Analytics | Descrição | Caminhos de atualização disponíveis |
|---------|----------|----------|
| AppMeasurement | O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics.<p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com AppMeasurement para JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrar o Adobe Analytics para o SDK da web</li><li>[Conector Source do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Extensão do Adobe Analytics (tags) | <p>Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.</p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando a extensão do Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Migrar o Adobe Analytics para o SDK da web</li><li>[Conector Source do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | O Experience Platform Web SDK é o método Adobe recomendado para implementar o Adobe Analytics. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o Edge Network de Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| Extensão Experience Platform Web SDK (tags) | O Experience Platform Web SDK é o método Adobe recomendado para implementar o Adobe Analytics para dados da Web. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado. <p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| Experience Platform Mobile SDK | O Experience Platform Mobile SDK é o método Adobe recomendado para implementar o Adobe Analytics para dados móveis. O Edge Network Adobe Experience Platform permite enviar dados destinados a vários produtos para um local centralizado.<p>O Adobe Experience Platform Mobile SDK ajuda a potencializar as soluções e os serviços da Experience Cloud Adobe em seus aplicativos móveis. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics usando o Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md) </li><li>Configurar a implementação do Adobe Analytics Web SDK para enviar dados à Platform</li></ul> |
| API de inserção de dados em massa | A API de inserção de dados em massa (BDIA) é um recurso do Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos, em vez de usar bibliotecas do lado do cliente, como o AppMeasurement. </p><p>Para obter mais informações sobre esse tipo de implementação, consulte [API de Inserção de Dados em Massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nova implementação do Experience Platform Web SDK para coleta de dados contínua; o Conector Source do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md)</li><li>[API e Edge Network do servidor Adobe Experience Platform Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}
