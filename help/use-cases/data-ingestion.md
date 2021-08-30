---
title: Opções de assimilação de dados para o Customer Journey Analytics
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
source-git-commit: fa0033202650f17acd275f1050565285c1464f53
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 100%

---

# Opções de assimilação de dados para o Customer Journey Analytics

Você tem várias opções quando se trata de assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você assimila dados diretamente da Adobe Experience Platform. Essa referência fornece etapas de alto nível que devem seguidas, com links para informações mais detalhadas.

## Assimilar dados do Adobe Analytics tradicional

Esse fluxo de trabalho utiliza o Adobe Analytics Data Connector e varia dependendo do uso do DTM ou do Launch como um Gerente de dados.

### Através do Launch

1. [Criar uma camada de dados](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=pt-BR), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use o [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=pt-BR) para implementar o código em seu site para a coleta de dados, caso ainda não tenha implementado. O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. O Launch oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site..
1. Crie um [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR).
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=pt-BR) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Assimilar dados via Adobe Experience Platform Web SDK e Edge Network

[O Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) é uma biblioteca JavaScript no lado do cliente que permite aos clientes da Adobe Experience Cloud interagir com os vários serviços na Experience Cloud por meio da Adobe Experience Platform Edge Network.

1. [Configure a extensão AEP Web SDK no Launch](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=br) para enviar dados para a Adobe Experience Cloud a partir das propriedades da Web, por meio da Adobe Experience Platform Edge Network.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Assimilar dados com assimilação em lote e por streaming

A Adobe Experience Platform reúne dados de várias fontes para ajudar os profissionais de marketing a entender melhor o comportamento de seus clientes. A assimilação de dados da Adobe Experience Platform representa os vários métodos pelos quais a plataforma assimila dados dessas fontes e também como esses dados são mantidos no Data Lake para uso pelos serviços downstream da plataforma.

### Assimilação em lote

1. Configure a [Assimilação em lote](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=pt-BR#batch) para assimilar dados na Adobe Experience Platform como arquivos em lote. Os dados assimilados podem ser os dados do perfil de um arquivo simples em um sistema CRM (como um arquivo parquet) ou dados que estejam em conformidade com um esquema conhecido no registro do Experience Data Model (XDM).
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

### Assimilação por streaming

1. Configure a [Assimilação por streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=pt-BR#streaming) para enviar dados de dispositivos no lado do cliente e do servidor para a Experience Platform em tempo real.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Trazer dados do Google Analytics para analisar no Customer Journey Analytics

Consulte este tutorial sobre como [Analisar dados do Google Analytics usando o Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=pt-BR#objectives) para ver as etapas em detalhes.

## Usar a API de inserção de dados em massa para obter dados no Analytics e, em seguida, assimilar por meio do Conector de origem da Adobe na Experience Platform

1. [Use a API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para enviar dados de coleção no lado do servidor para o Adobe Analytics. Ela permite que você envie arquivos formatados em CSV que contêm dados de eventos.
1. [Crie um conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para trazer esses dados do consumidor para a Adobe Experience Platform.
1. Use o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.
