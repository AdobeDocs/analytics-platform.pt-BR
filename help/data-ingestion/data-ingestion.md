---
title: Visão geral da ingestão de dados
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ec56bc657961b2e4e8318ab14cd676288398462f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 100%

---

# Visão geral da assimilação de dados

Você tem várias opções para assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você usa dados assimilados no Adobe Experience Platform.

>[!IMPORTANT]
>
>Em todos os cenários, os dados que você deseja _usar_ no Customer Journey Analytics é _assimilado_ na Adobe Experience Platform.


A arquitetura de alto nível do Customer Journey Analytics pode ser vista aqui:

![Arquitetura do Customer Journey Analytics](/help/getting-started/assets/cja-overview.svg)

Essa arquitetura ilustra como o Customer Journey Analytics permite:

* Combinar vários conjuntos de dados ![Dados](/help/assets/icons/Data.svg) em uma [conexão](/help/connections/overview.md).
* Defina e configure as dimensões ![Dimensões](/help/assets/icons/Dimensions.svg) e as métricas ![Evento](/help/assets/icons/Event.svg) em uma [visualização de dados](/help/data-views/data-views.md), com base nos campos disponíveis nos conjuntos de dados definidos na conexão.
* Crie relatórios ![ViewTable](/help/assets/icons/ViewTable.svg) e visualizações (como linha ![Linha](/help/assets/icons/GraphTrend.svg) e área ![Área](/help/assets/icons/GraphAreaStacked.svg)) nos [projetos](/help/analysis-workspace/home.md) com base nas dimensões e métricas das visualizações de dados.

Os conjuntos de dados na arquitetura podem originar de várias fontes:

* dados em lote,

* dados de transmissão,

* dados de uma implantação atual do Adobe Analytics,

* dados do rastreamento do site/aplicativo móvel usando o SDK da web/móvel da Adobe Experience Platform,

* dados do rastreamento de um aplicativo de desktop, jogo de console, decodificador ou dispositivo IoT usando a API de servidor da Egde Network da Adobe Experience Platform ou

* dados provenientes de um provedor de dados de terceiros para o qual a Adobe fornece um conector de origem.

E você pode ter muitos desses conjuntos de dados.

Esta seção da documentação fornece guias de início rápido para vários cenários.

## Priorização de assimilação e latência

Agora é possível assimilar dados de evento no Customer Journey Analytics em 90 minutos (SLT), não importa se os dados tenham sido gerados há 24 horas, 48 horas ou 7 dias. 

Observe que esse recurso difere com base no pacote SKU que sua empresa adquiriu:

* Assimilação de prioridade básica: dados gerados há 24 horas no processamento SLT de 90 minutos (disponível para o **CJA Foundation** e o **CJA Select**)

* Assimilação de prioridade intermediária: dados gerados há 72 horas no processamento SLT de 90 minutos (disponível para o **CJA Prime**)

* Assimilação de prioridade avançada: dados gerados há 1 semana no processamento SLT de 90 minutos (disponível para o **CJA Ultimate**)

## Assimilar e usar dados do Adobe Analytics tradicional

O Adobe Analytics já implantou e deseja assimilar esses dados na Adobe Experience Platform e usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados do Adobe Analytics tradicional](./analytics.md) para obter mais informações.


## Assimilar e usar dados por meio da Edge Network

### Uso do SDK da web da Adobe Experience Platform

Você deseja analisar seu site com a tecnologia da Adobe e está considerando migrar de outra solução ou começar a monitorar o comportamento das pessoas. Você deseja seguir as práticas recomendadas da Adobe para implementação, que usam os SDKs da Adobe Experience Platform e a Rede de borda, para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio do SDK da web da Adobe Experience Platform](./aepwebsdk.md) para obter mais informações.

### Uso do SDK móvel da Adobe Experience Platform

Você deseja analisar seu aplicativo móvel com a tecnologia da Adobe e está considerando migrar de outra solução ou começar a monitorar o comportamento de uma pessoa no aplicativo do zero. Você deseja seguir as práticas recomendadas da Adobe para implementação, que usam os SDKs da Adobe Experience Platform e a Rede de borda, para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio do SDK móvel da Adobe Experience Platform](./aepmobilesdk.md) para obter mais informações.

### Uso da API de servidor da Edge Network da Adobe Experience Platform

Você deseja analisar seu aplicativo de desktop, um jogo de um console de videogame, o uso de um aplicativo de transmissão de vídeo em um decodificador ou seu dispositivo IoT com tecnologia da Adobe. Está considerando migrar de outra solução ou começar a rastrear o comportamento de uma pessoa nesses dispositivos do zero. Você deseja seguir as práticas recomendadas da Adobe para implementação, que envolve o uso de APIs de servidor da Edge Network da Adobe Experience Platform e a Edge Network para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio da API de servidor da Edge Network da Adobe Experience Platform](./serverapi.md) para obter mais informações.

## Assimilar e usar dados em lote

Você tem dados relevantes em lote disponíveis, que fornecem detalhes que podem ajudar a entender melhor o comportamento do cliente e analisar as interações do cliente. Exemplos desses dados em lote são arquivos simples no formato CSV, JSON ou Parquet de um sistema CRM, aplicativo de fidelidade ou outra solução para a qual a Adobe atualmente não fornece um conector de origem. Inserir esses dados em lote na Adobe Experience Platform permite usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados em lote](./batch.md) para obter mais informações.

## Assimilar e usar dados de transmissão

Você tem uma fonte de dados relevante, como um sistema de CRM, ERP ou qualquer outra fonte que forneça detalhes que possam ajudar a entender melhor o comportamento do cliente e analisar as interações do cliente. Essa fonte de dados pode se comunicar por meio da infraestrutura de transmissão de nuvem HTTP ou pública, mas para a qual a Adobe atualmente não fornece um conector de origem. Inserir esses dados de transmissão na Adobe Experience Platform em tempo real permite usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados de transmissão](./streaming.md) para obter mais informações.

## Assimilar e usar dados usando conectores de origem

Você tem dados disponíveis de uma fonte compatível com um conector de origem. Os conectores de origem são configurações que podem ser definidas e permitem assimilar dados da Adobe, de aplicativos próprios e de terceiros na Adobe Experience Platform. Consulte [Visão geral dos conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR) para obter uma visão geral dos conectores de origem disponíveis. Usando o conector de origem, você pode assimilar facilmente dados da fonte na Adobe Experience Platform e, em seguida, usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados usando conectores de origem](./sources.md) para obter mais informações.

## Assimilar e usar dados ad hoc

Há dados ad hoc disponíveis que exigem apenas um único conjunto de dados na Experience Platform e não precisam da configuração de um esquema Experience Data Model (XDM). Esse cenário é chamado de esquema ad hoc. Esquemas ad hoc são usados em vários fluxos de trabalho de assimilação de dados da Experience Platform, incluindo a assimilação de arquivos CSV e a criação de determinados tipos de conexões de origem.

Consulte [Assimilar e usar dados ad hoc](./adhoc.md)

>[!MORELIKETHIS]
>
>Blog: [Análise detalhada do processamento e da assimilação de dados no Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-closer-look-at-data-processing-amp-ingestion-in-adobe-customer/ba-p/665091)

