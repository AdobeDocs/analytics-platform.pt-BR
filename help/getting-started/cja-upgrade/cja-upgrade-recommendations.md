---
title: Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 4%

---

# Atualização do Adobe Analytics para o Customer Journey Analytics

Antes de começar o processo de atualização do Adobe Analytics para o Customer Journey Analytics, compreenda primeiro as etapas de atualização recomendadas.

Dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização. Depois de entender as etapas de atualização recomendadas, preencha o questionário para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização.

## 1. Entenda as etapas de atualização recomendadas

>[!NOTE]
>
>As etapas de atualização descritas nesta seção são as etapas de atualização recomendadas que qualquer organização pode usar para atualizar com êxito do Adobe Analytics para o Customer Journey Analytics.
>
>No entanto, dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização. Depois de entender as etapas de atualização recomendadas, preencha o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização.

As etapas recomendadas ao atualizar do Adobe Analytics para o Customer Journey Analytics são uma nova implementação do SDK da Web do Experience Platform, que é o método de coleta de dados preferido para o Customer Journey Analytics. Juntamente com o SDK da Web, a Adobe também recomenda usar o conector de origem do Analytics para reter dados históricos do Adobe Analytics e executar uma comparação de dados lado a lado.

Após a transição completa para o Customer Journey Analytics, o conector de origem do Analytics pode ser desativado e o SDK da Web do Experience Platform pode ser usado exclusivamente.

1. **Implementar o SDK da Web do Experience Platform**

   Uma nova implementação do SDK da Web do Experience Platform é a melhor maneira de coletar dados para o Customer Journey Analytics. Ele fornece a melhor base para aproveitar ao máximo o Customer Journey Analytics, pois é o método mais eficiente, simples e inovador para implementar o Customer Journey Analytics.

   * Relatórios de alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi criado para potencializar casos de uso de personalização em tempo real

   * Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)

   * Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)

1. **Configurar o conector de origem do Adobe Analytics**

   Para ajudar com uma transição suave para o uso do SDK da Web do Experience Platform com o Customer Journey Analytics, o Adobe também recomenda usar o conector de origem do Adobe Analytics. Isso permite que você retenha dados históricos e visualize dados da sua implementação existente do Adobe Analytics em Customer Journey Analytics, lado a lado com os dados da sua nova implementação do SDK da Web do Experience Platform.

   O conector de origem do Analytics permite:

   * Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics.

     Você pode manter o conector de origem do Analytics em execução por tanto tempo quanto for necessário manter os dados históricos do Adobe Analytics.

   * Visualize os dados coletados com sua implementação original do Adobe Analytics (AppMeasurement, a extensão do Analytics ou a extensão SDK da Web) no Customer Journey Analytics. É possível comparar esses dados lado a lado com os da nova implementação do SDK da Web.

     É possível manter o conector de origem do Analytics em execução até que você esteja familiarizado e familiarizado com as diferenças. <!--elaborate on what those differences are? -->

   O conector de origem do Analytics como uma implementação independente não é um método recomendado de longo prazo para usar o Customer Journey Analytics. Isso se deve à alta latência, esquemas desorganizados e complexos, à dependência da nomenclatura do Adobe Analytics (propriedades, eVars e assim por diante) e à dificuldade de mudar do conector de origem para a implementação recomendada do SDK da Web.

## 2. Gerar dinamicamente etapas de atualização para sua organização

Dependendo de vários fatores, como restrições de linha do tempo e recursos, as etapas de atualização recomendadas descritas em [Entender as etapas de atualização recomendadas](#1-understand-the-recommended-upgrade-steps) podem não ser práticas para sua organização.

Para exibir as etapas de atualização geradas dinamicamente para as circunstâncias exclusivas de sua organização:

1. Conclua o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Depois de preencher este questionário, você receberá instruções passo a passo, descrevendo as etapas de atualização ideais exclusivas de sua organização. Estas são as etapas de atualização que melhor se alinham ao seu ambiente Adobe Analytics existente e às suas metas para o Customer Journey Analytics.

1. Siga as instruções passo a passo geradas para atualizar para o Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









