---
title: Entenda a sua implementação do Adobe Analytics e como ela afeta a atualização para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 100%

---

# Entenda a sua implementação do Adobe Analytics e como ela afeta a atualização para o Customer Journey Analytics {#implementation-affects-upgrade}

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
>abstract="Uma implementação de tags que carrega a Coleção de dados da Adobe Experience Platform (conhecida anteriormente como Launch). A tag tem a extensão do Adobe Analytics instalada."

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
>id="cja-upgrade-appmeasurement-third-party"
>title="AppMeasurement usando uma ferramenta de gerenciamento de tags de terceiros"
>abstract="Uma implementação que usa uma ferramenta de gerenciamento de tags de terceiros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="Implementação desconhecida"
>abstract="Se não for a pessoa que gerencia a implementação, poderá selecionar essa opção temporariamente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="Determinar o tipo de implementação existente"
>abstract="Trabalhe internamente em sua organização para determinar que tipo de implementação você usa atualmente para enviar dados para o Adobe Analytics. À medida que você atualiza para o Customer Journey Analytics, colabore com um indivíduo ou equipe que conheça essas informações.<br><br>Depois de determinar o tipo de implementação que sua organização usa, modifique sua resposta no guia de atualização do Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Há várias maneiras de implementar o Adobe Analytics. Ao atualizar para o Customer Journey Analytics, nem todos os caminhos de atualização estão disponíveis para todas as implementações do Adobe Analytics. No entanto, o caminho de atualização recomendado está disponível independentemente de como o Adobe Analytics foi implementado na sua organização.

Use as informações abaixo para saber mais sobre a sua implementação atual do Adobe Analytics e quais caminhos de atualização estão disponíveis para a sua organização.

Entre em contato com o(a) representante da Adobe se precisar de suporte, conselhos ou orientações específicos.

| Implementação existente do Adobe Analytics | Descrição | Caminhos de atualização disponíveis |
|---------|----------|----------|
| AppMeasurement | O AppMeasurement para JavaScript tem sido um método comum para implementar o Adobe Analytics. <p>Para mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com AppMeasurement para JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/js/overview).</p> | <ul><li>[(Recomendado) Nova implementação do SDK da Web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrar o Adobe Analytics para o SDK da Web](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Extensão do Adobe Analytics (tags) | <p>Tags na Adobe Experience Platform é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. A Adobe oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site.</p><p>Para mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com a extensão do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/launch/overview).</p> | <ul><li>[(Recomendado) Nova implementação do SDK da web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Migrar o Adobe Analytics para o SDK da Web](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| SDK da web da Experience Platform (alloy.js) | O SDK da web da Experience Platform é o método recomendado atualmente pela Adobe para implementar o Adobe Analytics. A Edge Network da Adobe Experience Platform permite enviar dados destinados a vários produtos a um local centralizado.  <p>Para mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com a Edge Network da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/overview).</p> | <ul><li>[(Recomendado) Nova implementação do SDK da web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurar a implementação do SDK da web do Adobe Analytics para enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Extensão do SDK da web da Experience Platform (tags) | O SDK da web da Experience Platform é o método recomendado atualmente pela Adobe para implementar o Adobe Analytics para dados da web. A Edge Network da Adobe Experience Platform permite enviar dados destinados a vários produtos a um local centralizado.  <p>Para mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o SDK da web da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do SDK da web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[Configurar a implementação do SDK da Web do Adobe Analytics para enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| SDK móvel da Experience Platform | O SDK móvel da Experience Platform é o método recomendado atualmente pela Adobe para implementar o Adobe Analytics para dados móveis. A Edge Network da Adobe Experience Platform permite enviar dados destinados a vários produtos a um local centralizado. <p>O SDK móvel da Adobe Experience Platform ajuda a potencializar as soluções e os serviços da Experience Cloud da Adobe nos seus aplicativos móveis.  </p><p>Para mais informações sobre esse tipo de implementação, consulte [Implementar o Adobe Analytics com o SDK móvel da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[(Recomendado) Nova implementação do SDK da web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md) </li><li>[Configurar a implementação do SDK da web do Adobe Analytics para enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| API de inserção de dados em massa | A API de inserção de dados em massa (BDIA) é um recurso do Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos em vez de usar bibliotecas do lado do cliente, como o AppMeasurement.  </p><p>Para mais informações sobre esse tipo de implementação, consulte [API de inserção de dados em massa](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).</p> | <ul><li>[(Recomendado) Nova implementação do SDK da web da Experience Platform para coleta contínua de dados; o conector de origem do Analytics para dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Nova implementação do SDK da web da Experience Platform](/help/data-ingestion/aepwebsdk.md)</li><li>[API do servidor da Edge Network da Adobe Experience Platform e Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


