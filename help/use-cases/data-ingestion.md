---
title: Opções de assimilação de dados para o Customer Journey Analytics
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 8a3a868ff4e2fbbcdf83ff7769382c6a92f78ec2
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 63%

---


# Opções de assimilação de dados para o Customer Journey Analytics

Você tem várias opções quando se trata de assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você assimila dados diretamente da Adobe Experience Platform. Essa referência fornece etapas de alto nível que devem seguidas, com links para informações mais detalhadas.

## Assimilar dados do Adobe Analytics tradicional

Esse fluxo de trabalho utiliza o Adobe Analytics Data Connector e varia dependendo do uso do DTM ou do Launch como um Gerente de dados.

### Via Dynamic Tag Management (DTM)

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/prepare/data-layer.html), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use o [DTM](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar o código em seu site para a coleta de dados caso ainda não tenha implementado. O Dynamic Tag Management fornece uma única camada de dados que envia dados de várias fontes.
1. Crie um [Conector de origem do Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html).
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/pt-BR/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

### Através do Launch

1. [Criar uma camada de dados](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), se você ainda não tiver uma. Uma camada de dados é uma estrutura de objetos JavaScript no site que contém todos os valores de variável usados na implementação. Permite maior controle e manutenção simplificada na implementação.
1. Use o [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/launch/overview.html) para implementar o código em seu site para a coleta de dados, caso ainda não tenha implementado. O Launch é uma solução de gerenciamento de tags que permite implantar o código do Analytics junto com outros requisitos de marcação. O Launch oferece integrações com outras soluções e produtos e permite implantar código personalizado. Todas essas tarefas podem ser realizadas sem depender de equipes de desenvolvimento na organização para atualizar o código no site..
1. Crie um [Conector de origem do Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) na Adobe Experience Platform. Esse conector de origem assimilará seus dados do Analytics na Experience Platform em uma estrutura padronizada chamada [Sistema do Experience Data Model (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Ingressar dados via Adobe Experience Platform Web SDK e Edge Network

[O Adobe Experience Platform Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) SDK é uma biblioteca JavaScript do lado do cliente que permite que os clientes da Adobe Experience Cloud interajam com os vários serviços na Experience Cloud por meio da Adobe Experience Platform Edge Network.

1. [Configure a extensão AEP Web SDK no ](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) Launchpara enviar dados para a Adobe Experience Cloud a partir das propriedades da Web, por meio da Adobe Experience Platform Edge Network.
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Ingressar dados com ingestão em lote e ingestão em streaming

A Adobe Experience Platform reúne dados de várias fontes para ajudar os comerciantes a entender melhor o comportamento de seus clientes. A ingestão de dados da Adobe Experience Platform representa os vários métodos pelos quais a plataforma ingere dados dessas fontes, bem como como como esses dados são persistentes no Data Lake para uso pelos serviços de plataforma downstream.

### Ingestão em lote

1. Configure [Ingestão em lote](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch) para permitir que você ingira dados no Adobe Experience Platform como arquivos em lote. Os dados sendo ingeridos podem ser os dados do perfil de um arquivo simples em um sistema CRM (como um arquivo parquet) ou dados que estejam em conformidade com um schema conhecido no registro do Modelo de Dados de Experiência (XDM).
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

### Inclusão de transmissão

1. Configure [Envio de transmissão](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming) para enviar dados de dispositivos cliente e servidor para Experience Platform em tempo real.
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.

## Trazer dados Google Analytics para análise no Customer Journey Analytics

Consulte este tutorial sobre como [Analisar dados de Google Analytics usando Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives) para obter etapas detalhadas.

## Use a API de inserção de dados em massa para obter dados no Analytics e, em seguida, ingressar por meio do conector de fonte de Adobe no Experience Platform

1. [Use a API de inserção de dados em massa ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para enviar dados de coleta do lado do servidor para a Adobe Analytics. Ele permite que você envie arquivos formatados em CSV que contêm dados de evento.
1. [Crie um ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) conector de origem Adobe Analytics para trazer esses dados de consumidor para a Adobe Experience Platform.
1. Use o [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para criar uma ou mais conexões e visualizações de dados que informarão seu relatórios entre canais.