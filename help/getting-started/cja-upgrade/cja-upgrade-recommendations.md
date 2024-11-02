---
title: Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 8%

---

# Atualização do Adobe Analytics para o Customer Journey Analytics

Antes de começar o processo de atualização do Adobe Analytics para o Customer Journey Analytics, compreenda primeiro as etapas de atualização recomendadas.

>[!NOTE]
>
>As etapas de atualização descritas nesta seção são as etapas de atualização recomendadas que qualquer organização pode usar para atualizar com êxito do Adobe Analytics para o Customer Journey Analytics.
>
>No entanto, dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização. Nesse caso, use o [questionário de atualização do Adobe Analytics para Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização.

## Etapas de atualização recomendadas para a maioria das organizações

As etapas recomendadas ao atualizar do Adobe Analytics para o Customer Journey Analytics são uma nova implementação do SDK da Web do Experience Platform, que é o método de coleta de dados preferido para o Customer Journey Analytics. Juntamente com o SDK da Web, a Adobe também recomenda usar o conector de origem do Analytics para reter dados históricos do Adobe Analytics e executar uma comparação de dados lado a lado.

Após a transição completa para o Customer Journey Analytics, o conector de origem do Analytics pode ser desativado e o SDK da Web do Experience Platform pode ser usado exclusivamente.

### Processo de atualização recomendado de alto nível

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

### Etapas de atualização detalhadas recomendadas

As etapas a seguir mostram o processo recomendado para atualizar do Adobe Analytics para o Customer Journey Analytics.

Dependendo do ambiente e dos requisitos exclusivos de sua organização, essas etapas recomendadas podem não ser adequadas para sua organização. Nesse caso, use o [questionário de atualização do Adobe Analytics para Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização.

1. [Planeje sua arquitetura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crie o esquema personalizado desejado no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

1. [Criar um conjunto de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. Expanda a seção que descreve sua implementação atual do Adobe Analytics e conclua as etapas associadas:

   +++Para implementações do Adobe Analytics usando o AppMeasurement

   1. [Criar uma sequência de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++Para implementações do Adobe Analytics que usam a extensão do Analytics (tags)

   1. [Criar uma sequência de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ Para implementações do Adobe Analytics usando o SDK da Web

   Nenhuma etapa adicional é necessária.

+++

1. [Adicionar o Adobe Experience Platform como um serviço à sua sequência de dados](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. Use a tabela a seguir para identificar quaisquer recursos do Adobe Analytics que você deseja continuar usando no Customer Journey Analytics e, em seguida, use as informações fornecidas para saber como configurar esses recursos como parte da atualização para o Customer Journey Analytics:

   | Recurso do Adobe Analytics | Requisitos de implementação para o Customer Journey Analytics | Informações adicionais |
   |---------|----------|---------|
   | Dados de classificação | Crie um conjunto de dados de pesquisa para cada dimensão que contenha dados de classificação. |  |
   | Canais de marketing | Criar um campo derivado de canal de marketing. |  |
   | Sobreposição do Activity Map e rastreamento de link | N/D | No momento, o Adobe está trabalhando no suporte de sobreposição de Activity Map para o Customer Journey Analytics. |
   | Feeds de dados | Nenhuma configuração é necessária durante a implementação.<br/>[Saiba mais sobre as várias opções de exportação do Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md). | Embora uma substituição direta dos Feeds de dados ainda não esteja disponível no Customer Journey Analytics, você pode exportar relatórios de Customer Journey Analytics do Analysis Workspace para uso em ferramentas de terceiros ou para combinar com dados externos. |
   | Data Warehouse | Nenhuma configuração é necessária durante a implementação.<br/>[Saiba mais sobre a Exportação de Tabela Completa no Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md). | Exportação de tabela completa do Customer Journey Analytics é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos e frequentemente solicitados que não estão disponíveis no Data Warehouse hoje. |
   | Dados de mídia de transmissão |  |  |

1. (Opcional) Traga dados históricos do Adobe Analytics usando o conector de origem do Analytics.

   Para obter mais informações, consulte [Usar um conector de origem](/help/data-ingestion/sources.md#use-a-source-connector) em [Assimilar e usar dados usando conectores de origem](/help/data-ingestion/sources.md).

1. Use a tabela a seguir para identificar os recursos de Customer Journey Analytics desejados e, em seguida, use as informações fornecidas para saber como configurar esses recursos como parte da atualização para o Customer Journey Analytics:

   | Recursos do Customer Journey Analytics que você deseja | Requisitos de implementação para o Customer Journey Analytics | Informações adicionais |
   |---------|----------|---------|
   | Vincular dados da Web a dados de outros canais, como dados da central de atendimento | Após criar uma conexão (conforme descrito em uma etapa posterior), adicione conjuntos de dados adicionais à sua conexão no Customer Journey Analytics. |  |
   | Integrar à RTCDP | Ative o perfil no esquema e crie um conjunto de dados de perfil para uso no RTCDP | Isso deve ser feito ao criar o esquema XDM. |
   | Integrar ao Adobe Journey Optimizer | Use o objeto de personalização em sua implementação para usar no Adobe Journey Optimizer |  |

1. Expanda a seção que descreve a implementação do Customer Journey Analytics desejado e conclua as etapas associadas:

   +++Implementação manual (arquivo JS)

   1. [Adicionar alloy.js ao seu site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

+++

   +++Marcas

   1. [Crie uma propriedade de marca na coleção de dados da Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property).

+++

+++ API

   1. Use a API de Edge Network para enviar dados para o fluxo de dados desejado.

+++

1. [Criar uma conexão no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Confirme se os dados estão fluindo para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrar projetos e componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

1. Compare os dados da implementação antiga com os da nova implementação e verifique se você compreende as diferenças e por que elas existem.

1. Planejar a integração do usuário.

   Como no Adobe Analytics, o Analysis Workspace é a principal ferramenta voltada para usuários do Customer Journey Analytics. No entanto, é necessário considerar algumas diferenças importantes de se usar o Analysis Workspace no Customer Journey Analytics.

   Dê a seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.

   Para mais informações sobre algumas das principais diferenças entre o Adobe Analytics e o Customer Journey Analytics, consulte o [Guia para usuários do Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Desative a coleta de dados do AppMeasurement.

1. Desative o conector de origem do Analytics.

   Com a implementação do SDK da Web do Experience Platform, o conector de origem do Analytics é necessário apenas para dados históricos do Adobe Analytics e para comparar os dados da implementação original com os da nova implementação.

   Quando tiver dados históricos suficientes da nova implementação e estiver familiarizado com as diferenças de relatório no Customer Journey Analytics, desative o conector de origem do Analytics.

## Gerar dinamicamente etapas de atualização para sua organização

Dependendo de vários fatores, como restrições de linha do tempo e recursos, as etapas de atualização recomendadas descritas em [Entender as etapas de atualização recomendadas](#1-understand-the-recommended-upgrade-steps) podem não ser práticas para sua organização.

Para gerar dinamicamente etapas de atualização para as circunstâncias exclusivas de sua organização:

1. Conclua o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   Depois de preencher este questionário, você receberá instruções passo a passo, descrevendo as etapas de atualização ideais exclusivas dos requisitos de sua organização. Estas são as etapas de atualização que melhor se alinham ao seu ambiente Adobe Analytics existente e às suas metas para o Customer Journey Analytics.

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









