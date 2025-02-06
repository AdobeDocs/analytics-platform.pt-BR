---
title: Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 8%

---

# Atualização do Adobe Analytics para o Customer Journey Analytics

Ao atualizar do Adobe Analytics para o Customer Journey Analytics, você pode seguir as [etapas de atualização recomendadas](#recommended-upgrade-steps-for-most-organizations). Ou você pode [gerar dinamicamente etapas de atualização](#dynamically-generate-upgrade-steps-for-your-organization) para as circunstâncias exclusivas de sua organização.

## Etapas de atualização recomendadas para a maioria das organizações {#upgrade-process}

O processo recomendado de atualização do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido para o Customer Journey Analytics. Em conjunto com o Web SDK, o Adobe também recomenda o uso do conector de origem do Analytics para ajudar na transição para o Customer Journey Analytics. Use o conector de origem do Analytics para reter dados históricos do Adobe Analytics e executar uma comparação de dados lado a lado.

Depois de ter dados históricos suficientes usando o Experience Platform Web SDK e ter feito a transição completa para o Customer Journey Analytics, o conector de origem do Analytics pode ser desativado e o Web SDK pode ser usado exclusivamente.

>[!NOTE]
>
>Se as etapas de atualização descritas nesta seção não forem práticas para sua organização, use o [Questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização.

### Processo de atualização recomendado de alto nível {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Dados históricos do Adobe Analytics"
>abstract="Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementar o Experience Platform Web SDK (para coleta de dados contínua)**

   Uma nova implementação do Experience Platform Web SDK é a melhor maneira de coletar dados para o Customer Journey Analytics. Ele fornece a melhor base para aproveitar ao máximo o Customer Journey Analytics, pois é o método mais eficiente, simples e inovador para implementar o Customer Journey Analytics.

   * Relatórios de alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi criado para potencializar casos de uso de personalização em tempo real

   * Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)

   * Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)

1. **Configure o conector de origem do Adobe Analytics (para trazer dados históricos)**

   Para ajudar na transição suave para o uso do Experience Platform Web SDK com Customer Journey Analytics, o Adobe também recomenda o uso do conector de origem Adobe Analytics. Isso permite que você retenha dados históricos e visualize dados da sua implementação existente do Adobe Analytics em Customer Journey Analytics, lado a lado com os dados da sua nova implementação do Experience Platform Web SDK.

   O conector de origem do Analytics permite:

   * Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics.

     Você pode manter o conector de origem do Analytics em execução por tanto tempo quanto for necessário manter os dados históricos do Adobe Analytics.

   * Visualize os dados coletados com sua implementação original do Adobe Analytics (AppMeasurement, a extensão do Analytics ou a extensão do Web SDK) no Customer Journey Analytics. Você pode comparar esses dados lado a lado com os da nova implementação do Web SDK.

     É possível manter o conector de origem do Analytics em execução até que você esteja familiarizado e familiarizado com as diferenças. <!--elaborate on what those differences are? -->

   O conector de origem do Analytics como uma implementação independente não é um método recomendado de longo prazo para usar o Customer Journey Analytics. Isso se deve à alta latência, esquemas desorganizados e complexos, à dependência da nomenclatura do Adobe Analytics (propriedades, eVars e assim por diante) e à dificuldade de mudar do conector de origem do Analytics para a implementação recomendada do Web SDK.

### Etapas de atualização detalhadas recomendadas

As etapas a seguir descrevem o processo recomendado para atualizar do Adobe Analytics para o Customer Journey Analytics.

Cada etapa fornece uma explicação de alto nível de um processo mais detalhado. Siga o link para cada etapa e conclua suas tarefas associadas, retorne a essa página e continue para a próxima etapa do processo.

1. [Planeje sua arquitetura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crie o esquema personalizado desejado no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Considere as seguintes opções ao criar seu esquema:

   * Se quiser integrar o Customer Journey Analytics com RTCDP, habilite a opção **[!UICONTROL Perfil]** no esquema, conforme descrito em [Criar um esquema XDM para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Com essa opção ativada, quando os dados forem assimilados em conjuntos de dados com base nesse esquema, esses dados serão mesclados no Perfil do cliente em tempo real.

   * Se quiser incluir dados de streaming de mídia, você deve [configurar seu esquema para assimilar e usar dados de streaming](/help/data-ingestion/streaming.md).

1. [Criar um conjunto de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Opcional) Se você usar dados de classificação no Adobe Analytics, poderá adicionar dados de classificação ao seu conjunto de dados no Customer Journey Analytics.

   Para fazer isso, [crie um conjunto de dados de pesquisa para cada dimensão que contenha os dados de classificação](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Para implementações do Adobe Analytics que usam o AppMeasurement ou a extensão (marcas) do Analytics, [crie uma sequência de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Para implementações do Adobe Analytics que usam a Web SDK, já existe um fluxo de dados.

1. [Adicionar o Adobe Experience Platform como um serviço à sua sequência de dados](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Opcional) Se quiser integrar o Customer Journey Analytics ao Adobe Journey Optimizer, use o objeto de personalização na implementação para usar no Adobe Journey Optimizer.

1. Expanda a seção que descreve como você deseja implementar o Experience Platform Web SDK para sua implementação de Customer Journey Analytics e, em seguida, conclua as etapas associadas:

   +++Implementação manual (arquivo JS)

   1. [Adicionar alloy.js ao seu site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Preencha um objeto XDM e envie-o para o fluxo de dados.

+++

   +++Marcas

   1. [Crie uma propriedade de marca e adicione a extensão Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Adicionar a extensão Adobe Experience Platform Web SDK à propriedade da tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implemente a marca do carregador em seu site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Adicionar lógica de coleta de dados XDM à sua marca](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Use a API de Edge Network para enviar dados para o fluxo de dados desejado.

+++

1. [Valide se a implementação do Web SDK está enviando dados para um conjunto de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Criar uma conexão no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Opcional) Vincule dados da Web a dados de outros canais, como dados da central de atendimento.

   Você consegue isso adicionando conjuntos de dados à conexão Customer Journey Analytics, conforme descrito em [Importar dados da central de atendimento e da Web](/help/use-cases/cross-channel/call-center.md).

1. [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Confirme se os dados estão fluindo para a exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. [Migrar projetos e componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Opcional) Se você usa canais de marketing na Adobe Analytics, é possível [criar um campo derivado de canal de marketing no Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Os campos derivados são um aspecto importante do relatório em tempo real no Customer Journey Analytics. Um campo derivado permite definir manipulações de dados (geralmente complexas) dinamicamente, por meio de um construtor de regras personalizável.

   Um uso para campos derivados é definir um campo derivado de Canal de marketing que determina o canal de marketing adequado com base em uma ou mais condições (por exemplo, parâmetro de URL, URL da página ou nome da página).

   Use [o modelo de função de canais de marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) em campos derivados para criar rapidamente um campo derivado para canais de marketing.

1. Compare os dados no Adobe Analytics da implementação antiga com os dados no Customer Journey Analytics da nova implementação e verifique se você compreende as diferenças e por que elas existem. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Traga dados históricos do Adobe Analytics usando o conector de origem do Analytics:

   >[!NOTE]
   >
   >Use as etapas a seguir se não tiver criado um conector de origem do Analytics anteriormente.
   >
   >Se você já estiver usando o conector de origem do Analytics com o Customer Journey Analytics, siga as etapas em [Transição do conector de origem do Analytics para o Web SDK para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Criar um esquema XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Se você ainda não tiver um conector de origem do Analytics, [crie o conector de origem do Analytics e mapeie os campos para o esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      Ou

      Se você já tiver um conector de origem do Analytics, [mapeie os campos do conector de origem para o esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Adicione o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planejar a integração do usuário.

   Como no Adobe Analytics, o Analysis Workspace é a principal ferramenta voltada para usuários do Customer Journey Analytics. No entanto, é necessário considerar algumas diferenças importantes de se usar o Analysis Workspace no Customer Journey Analytics.

   Dê a seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.

   Para mais informações sobre algumas das principais diferenças entre o Adobe Analytics e o Customer Journey Analytics, consulte o [Guia para usuários do Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Saiba mais sobre o suporte a recursos [no Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). A maioria dos recursos do Adobe Analytics é suportada no Customer Journey Analytics e muitos recursos adicionais estão disponíveis no Customer Journey Analytics.

1. Desative o Adobe Analytics quando a implementação do Customer Journey Analytics Web SDK estiver concluída e você estiver familiarizado com os dados coletados.

   A Adobe recomenda que você mantenha seu ambiente Adobe Analytics em execução por um período após implementar o Customer Journey Analytics.

   Para obter mais informações sobre os usos do Adobe Analytics durante e após uma atualização, bem como o tempo sugerido para desabilitar o Adobe Analytics, consulte [Avaliar por quanto tempo você precisa do Adobe Analytics após atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

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
