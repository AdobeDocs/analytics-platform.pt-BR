---
title: Opções de ingestão de dados para o Customer Journey Analytics
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T11:01:56.579Z'
TQID: 'https://experienceleague.adobe.com/Uqoyk9k3hEOB90hzLtXhoYtmfX18wmXPHp-AWxgNIwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 86%

---

# Opções de ingestão de dados para o Customer Journey Analytics

Você tem várias opções quando se trata de assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você assimila dados diretamente da Adobe Experience Platform. Essa referência fornece etapas de alto nível que devem seguidas, com links para informações mais detalhadas.

## Assimilar dados do Adobe Analytics tradicional

Esse fluxo de trabalho utiliza o conector de origem do Analytics e varia dependendo do uso do DTM ou do Launch como um Gerenciador de tags.

### Por meio de tags na Adobe Experience Platform (antes chamada de [!UICONTROL Launch])

1. [Criar uma camada de dados](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=pt-BR), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use as tags da [Adobe Experience Platform Adicionar](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=pt-BR) para implementar o código em seu site para a coleção de dados, caso ainda não tenha implementado. Esta solução de gerenciamento de tags permite implantar o código do Analytics junto com outros requisitos de marcação. As tags oferecem integrações com outras soluções e produtos e permitem implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site..
1. Crie um [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR). Consulte também [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Assimilar dados via Adobe Experience Platform Web SDK e Edge Network

O [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) é uma biblioteca JavaScript do lado do cliente que permite que os clientes do Adobe CX Enterprise interajam com os vários serviços no CX Enterprise por meio do Adobe Experience Platform Edge Network.

1. [Configure a extensão do Adobe Experience Platform Web SDK nas tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=pt-BR) para enviar dados para o CX Enterprise a partir das propriedades da Web, por meio do Adobe Experience Platform Edge Network.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais [conexões](/help/connections/create-connection.md) e [visualizações de dados](/help/data-views/data-views.md) que informarão seu relatórios entre canais.

## Assimilar dados com ingestão em lote e ingestão de transmissão

A Adobe Experience Platform reúne dados de várias fontes para ajudar os profissionais de marketing a entender melhor o comportamento de seus clientes. A ingestão de dados da Adobe Experience Platform representa os vários métodos pelos quais a plataforma ingere dados dessas fontes e também como esses dados são mantidos no Data Lake para uso pelos serviços downstream da plataforma.

### Ingestão em lote

1. Configure a [Ingestão em lote](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=pt-BR#batch) para ingerir dados na Adobe Experience Platform como arquivos em lote. Os dados assimilados podem ser os dados do perfil de um arquivo simples em um sistema CRM (como um arquivo parquet) ou dados que estejam em conformidade com um esquema conhecido no registro do Experience Data Model (XDM).
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais [conexões](/help/connections/create-connection.md) e [visualizações de dados](/help/data-views/data-views.md) que informarão seu relatórios entre canais.

### Ingestão de transmissão

1. Configure a [Ingestão de transmissão](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=pt-BR#streaming) para enviar dados de dispositivos no lado do cliente e do servidor para a Experience Platform em tempo real.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais [conexões](/help/connections/create-connection.md) e [visualizações de dados](/help/data-views/data-views.md) que informarão seu relatórios entre canais.

## Trazer dados do Google Analytics para analisar no Customer Journey Analytics

Consulte este tutorial sobre como [Analisar dados do Google Analytics usando o Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html?lang=pt-BR) para ver as etapas em detalhes.

## Usar a API de inserção de dados em massa para obter dados no Analytics e, em seguida, assimilar por meio do conector de origem do Analytics no Experience Platform

1. [Use a API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para enviar dados de coleção no lado do servidor para o Adobe Analytics. Ela permite que você envie arquivos formatados em CSV que contêm dados de eventos.
1. [Crie um conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para trazer esses dados do consumidor para a Adobe Experience Platform.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais [conexões](/help/connections/create-connection.md) e [visualizações de dados](/help/data-views/data-views.md) que informarão seu relatórios entre canais.
