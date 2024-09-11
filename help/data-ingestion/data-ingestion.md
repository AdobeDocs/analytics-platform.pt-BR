---
title: Visão geral da assimilação de dados
description: Entenda as diferentes maneiras de assimilar dados no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
role: Admin
source-git-commit: ac1d8a191bbad049ada246937364aeb7f8b275a0
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 64%

---

# Visão geral da assimilação de dados

Você tem várias opções ao assimilar dados no Customer Journey Analytics. Algumas delas presumem que você deseja mover os dados tradicionais do Adobe Analytics, outras presumem que você usa dados assimilados no Adobe Experience Platform.

>[!IMPORTANT]
>
>Em todos os cenários, os dados que você deseja _usar_ no Customer Journey Analytics é _assimilado_ na Adobe Experience Platform.

Consulte a arquitetura de alto nível do Customer Journey Analytics mostrada anteriormente na [Visão geral](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-overview):

Arquitetura ![Customer Journey Analytics descrita nesta seção](./assets/cja-architecture.png)

O conjunto de dados na arquitetura acima pode se originar de várias fontes:

- dados em lote,

- dados de transmissão,

- dados de uma implantação atual do Adobe Analytics,

- dados do rastreamento do seu site/aplicativo móvel usando o SDK da Web/móvel da Adobe Experience Platform,

- dados do rastreamento de um aplicativo de desktop, jogo de console, decodificador de sinais ou dispositivo IoT usando a API do servidor Adobe Experience Platform Edge Network ou

- dados provenientes de um provedor de dados de terceiros para o qual a Adobe fornece um conector de origem.

E você pode ter muitos desses conjuntos de dados.

Esta seção da documentação fornece guias de início rápido para vários cenários.

## Priorização e latência de assimilação

Você pode assimilar os dados do evento no Customer Journey Analytics em 90 minutos (SLT), independentemente de os dados terem 24 horas, 48 horas ou 7 dias.

Observe que esse recurso é diferente com base no pacote SKU que sua empresa adquiriu:

- Básica de assimilação de prioridade: dados com 24 horas no processamento SLT de 90 minutos (disponível para **CJA Foundation** e **CJA Select**)

- Assimilação prioritária intermediária: dados de 72 horas no processamento SLT de 90 minutos (disponível para o **CJA Prime**)

- Assimilação de prioridade avançada: dados com 1 semana de duração dentro do processamento SLT de 90 minutos (disponível para **CJA Ultimate**)

## Assimilar e usar dados do Adobe Analytics tradicional

O Adobe Analytics já implantou e deseja assimilar esses dados na Adobe Experience Platform e usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados do Adobe Analytics tradicional](./analytics.md) para obter mais informações.


## Assimilar e use dados por meio do Edge Network

### Uso do SDK da Web da Adobe Experience Platform

Você deseja analisar seu site com a tecnologia Adobe, migrando potencialmente de outra solução ou começar a rastrear o comportamento de sua pessoa. Você deseja seguir as práticas recomendadas da Adobe para implementação, que usam os SDKs da Adobe Experience Platform e a Rede de borda, para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio do SDK da Web da Adobe Experience Platform](./aepwebsdk.md) para obter mais informações.

### Uso do SDK do Adobe Experience Platform Mobile

Você deseja analisar seu aplicativo móvel com a tecnologia Adobe, migrando potencialmente de outra solução ou começando a rastrear o comportamento de uma pessoa no aplicativo do zero. Você deseja seguir as práticas recomendadas da Adobe para implementação, que usam os SDKs da Adobe Experience Platform e a Rede de borda, para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio do SDK do Adobe Experience Platform Mobile](./aepmobilesdk.md) para obter mais informações.

### Uso da API do servidor Adobe Experience Platform Edge Network

Você deseja analisar seu aplicativo de desktop, o jogo conforme é reproduzido em um console de jogos, o uso de um aplicativo de streaming de vídeo em um decodificador de sinais ou seu dispositivo IoT com tecnologia Adobe. Migração potencial de outra solução ou início do rastreamento do comportamento de uma pessoa nesses dispositivos do zero. Você deseja seguir as práticas recomendadas de implementação do Adobe, que é o uso das APIs e Edge Network do servidor Edge Network da Adobe Experience Platform, para assimilar os dados. Em seguida, você pode usar, combinar e analisar os dados assimilados com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados por meio da API do Adobe Experience Platform Edge Network Server](./serverapi.md) para obter mais informações.

## Assimilar e usar dados em lote

Você tem dados relevantes em lote disponíveis, que fornecem detalhes que podem ajudar a entender melhor o comportamento do cliente e analisar as interações do cliente. Exemplos desses dados em lote são arquivos simples no formato CSV, JSON ou Parquet de um sistema CRM, aplicativo de fidelidade ou outra solução para a qual a Adobe atualmente não fornece um conector de origem. Inserir esses dados em lote na Adobe Experience Platform permite usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados em lote](./batch.md) para obter mais informações.

## Assimilar e usar dados de transmissão

Você tem uma fonte de dados relevante, como um sistema de CRM, ERP ou qualquer outra fonte que forneça detalhes que possam ajudar a entender melhor o comportamento do cliente e analisar as interações do cliente. Essa fonte de dados pode se comunicar por meio da infraestrutura de transmissão de nuvem HTTP ou pública, mas para a qual a Adobe atualmente não fornece um conector de origem. Inserir esses dados de transmissão na Adobe Experience Platform em tempo real permite usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados de transmissão](./streaming.md) para obter mais informações.

## Assimilar e usar dados usando conectores de origem

Você tem dados disponíveis de uma fonte compatível com um conector de origem. Os conectores de origem são configurações que podem ser definidas e permitem assimilar dados da Adobe, de aplicativos próprios e de terceiros na Adobe Experience Platform. Consulte [Visão geral dos conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR) para obter uma visão geral dos conectores de origem disponíveis. Usando o conector de origem, você pode assimilar facilmente dados da fonte na Adobe Experience Platform e, em seguida, usá-los, combiná-los e analisá-los com dados de outros canais e fontes de dados no Customer Journey Analytics.

Consulte [Assimilar e usar dados usando conectores de origem](./sources.md) para obter mais informações.
