---
title: Atualização do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre as etapas recomendadas ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 17%

---

# Atualização do Adobe Analytics para o Customer Journey Analytics

Ao atualizar do Adobe Analytics para o Customer Journey Analytics, você pode seguir as [etapas de atualização recomendadas](#recommended-upgrade-steps-for-most-organizations). Ou você pode [gerar dinamicamente etapas de atualização](#dynamically-generate-upgrade-steps-for-your-organization) para as circunstâncias exclusivas de sua organização.

## Etapas de atualização recomendadas para a maioria das organizações {#upgrade-process}

O processo recomendado para atualizar do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido do Customer Journey Analytics. Juntamente com o Web SDK, a Adobe também recomenda o uso do conector de origem do Analytics para ajudar na transição para o Customer Journey Analytics. Use o conector de origem do Analytics para reter dados históricos do Adobe Analytics e executar uma comparação de dados lado a lado.

Depois de ter dados históricos suficientes usando o Experience Platform Web SDK e ter feito a transição completa para o Customer Journey Analytics, o conector de origem do Analytics pode ser desativado e o Web SDK pode ser usado exclusivamente.

>[!NOTE]
>
>Se as etapas de atualização descritas nesta seção não forem práticas para sua organização, use o Guia de atualização do Customer Journey Analytics para gerar dinamicamente etapas de atualização personalizadas para as circunstâncias exclusivas de sua organização. (Para acessar o guia no Customer Journey Analytics, selecione a guia **[!UICONTROL Workspace]** e clique em **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.)

### Processo de atualização de alto nível recomendado {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Dados históricos do Adobe Analytics"
>abstract="Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementar o Experience Platform Web SDK (para coleta de dados contínua)**

   Uma nova implementação do Experience Platform Web SDK é a melhor maneira de coletar dados para o Customer Journey Analytics. Ele fornece a melhor base para aproveitar ao máximo o Customer Journey Analytics, pois é o método mais eficiente, simples e à prova de obsolescência para implementar o Customer Journey Analytics.

   * Relatórios de alto desempenho e disponibilidade de dados porque o Adobe Experience Platform foi criado para potencializar casos de uso de personalização em tempo real

   * Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)

   * Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)

1. **Configure o conector de origem do Adobe Analytics (para trazer dados históricos)**

   Para ajudar na transição suave para o uso do Experience Platform Web SDK com o Customer Journey Analytics, a Adobe também recomenda o uso do conector de origem do Adobe Analytics. Isso permite que você retenha dados históricos e visualize dados da sua implementação existente do Adobe Analytics no Customer Journey Analytics, lado a lado com os dados da sua nova implementação do Experience Platform Web SDK.

   O conector de origem do Analytics permite:

   * Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e para o Customer Journey Analytics.

     Você pode manter o conector de origem Analytics funcionando, desde que precise manter os dados históricos Adobe Analytics.

   * Exibir os dados coletados com a implementação original da Adobe Analytics (AppMeasurement, a Extensão Analytics ou a Extensão do SDK da Web) no Customer Journey Analytics. É possível comparar esses dados lado a lado com os novos implementação do SDK da Web.

     Você pode manter o conector de origem Analytics em execução até estar familiarizado e confortável com as diferenças. <!--elaborate on what those differences are? -->

   O conector de origem Analytics como um implementação independente não é um método recomendado a longo prazo para usar Customer Journey Analytics. Isso se deve à alta latência, esquemas desordenados e complexos, dependência da Adobe Analytics nomenclatura (prop, eVar etc) e dificuldade para eventualmente mudar do conector de origem Analytics para o SDK da Web recomendado implementação.

### Etapas detalhadas recomendadas de atualização

As etapas a seguir descrevem o processo recomendado para atualização de Adobe Analytics para Customer Journey Analytics.

Cada etapa fornece uma explicação de alto nível de um processo mais detalhado. Siga o link para cada etapa e conclua suas tarefas associadas, retorne a essa página e continue para a próxima etapa do processo.

1. [Planeje sua arquitetura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Crie o esquema personalizado desejado no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Considere as seguintes opções ao criar seu esquema:

   * Se quiser integrar o Customer Journey Analytics com RTCDP, habilite a opção **[!UICONTROL Perfil]** no esquema, conforme descrito em [Criar um esquema XDM para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Com essa opção ativada, quando os dados forem assimilados em conjuntos de dados com base nesse esquema, esses dados serão mesclados no Perfil do cliente em tempo real.

   * Se você quiser incluir dados de mídia de streaming, configure [seus schema para assimilar e use dados](/help/data-ingestion/streaming.md) de streaming.

1. [Criar uma conjunto de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Opcional) Se você usar classificação dados em Adobe Analytics, é possível adicionar classificação dados às suas conjunto de dados em Customer Journey Analytics.

   Para fazer isso, [crie uma conjunto de dados de pesquisa para cada dimensão contendo dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) classificação.

1. Para implementações do Adobe Analytics usando o AppMeasurement ou a extensão (marcas) do Analytics, [crie uma sequência de dados no Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Para implementações do Adobe Analytics que usam a Web SDK, já existe um fluxo de dados. Para obter mais informações, consulte [Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Adicionar o Adobe Experience Platform como um serviço à sua sequência de dados](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Opcional) Se quiser integrar o Customer Journey Analytics ao Adobe Journey Optimizer, use o objeto de personalização na implementação para usar no Adobe Journey Optimizer.

1. Expanda a seção que descreve como você deseja implementar o Experience Platform Web SDK para sua implementação do Customer Journey Analytics e, em seguida, conclua as etapas associadas:

   +++Implementação manual (arquivo JS)

   1. [Adicione alloy.js ao seu site](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22).

   1. Preencha um objeto XDM e o envie para a sequência de dados.

+++

   +++Marcas

   1. [Crie uma propriedade de marca e adicione a extensão Adobe Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Adicionar a extensão do SDK da web da Adobe Experience Platform à sua propriedade de tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implemente a marca do carregador em seu site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Adicione a lógica coleção de dados XDM ao tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Use a API de rede Edge para enviar dados para a sequência de dados desejada.

+++

1. [Valide se o implementação do Web SDK está enviando dados para uma conjunto de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Criar uma conexão no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Opcional) Vincule dados da Web a dados de outros canais, como dados da central de atendimento.

   Você consegue isso adicionando conjuntos de dados à conexão do Customer Journey Analytics, conforme descrito em [Importar dados da central de atendimento e da Web](/help/use-cases/cross-channel/call-center.md).

1. [Criar uma exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Confirme se os dados estão fluindo para a exibição de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. Em seu ambiente do Adobe Analytics, [use o Inventário do Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) para ter uma visão geral abrangente de seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais.

1. [Migrar projetos e componentes](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Opcional) Se você usa canais de marketing no Adobe Analytics, é possível [criar um campo derivado de canal de marketing no Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Os campos derivados são um aspecto importante dos relatórios em tempo real no Customer Journey Analytics. Um campo derivado permite definir manipulações de dados (geralmente complexas) dinamicamente, por meio de um construtor de regras personalizável.

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

1. Saiba mais sobre o suporte a recursos [no Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). A maioria dos recursos do Adobe Analytics é compatível com o Customer Journey Analytics e muitos recursos adicionais estão disponíveis no Customer Journey Analytics.

1. Desative o Adobe Analytics quando a implementação do Customer Journey Analytics Web SDK estiver concluída e você estiver familiarizado com os dados coletados.

   Adobe Systems recomenda manter sua Adobe Analytics ambiente em execução por um período de tempo após a implementação de Customer Journey Analytics.

   Para obter mais informações sobre os usos de Adobe Analytics durante e após uma atualização, bem como o tempo sugerido para desabilitar Adobe Analytics, consulte [Avaliar quanto tempo você precisa Adobe Analytics após a atualização para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Gere dinamicamente as etapas de atualização para sua organização

Dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas descritas em [Entender as etapas](#recommended-upgrade-steps-for-most-organizations) de atualização recomendadas podem não ser práticas para sua organização. Nesse caso, você pode gerar dinamicamente etapas de atualização para as circunstâncias exclusivas de sua organização. O processo de geração dessas etapas difere dependendo se você já tem acesso a Customer Journey Analytics.

### Para clientes que têm acesso ao Customer Journey Analytics

Para gerar dinamicamente as etapas de atualização das circunstâncias exclusivas de sua organização:

1. Complete o Guia de atualização do Customer Journey Analytics.

   No Customer Journey Analytics, selecione a guia **[!UICONTROL Workspace]** e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.

   Após a conclusão deste guia de atualização, são fornecidas instruções passo a passo, descrevendo as etapas de atualização ideais exclusivas para os requisitos de sua organização. Estas são as etapas de atualização que melhor se alinham ao seu ambiente existente do Adobe Analytics e às suas metas do Customer Journey Analytics. As etapas de atualização estão disponíveis como um link compartilhável ou como um arquivo .csv que pode ser baixado.

1. Siga as instruções passo a passo geradas para atualizar para o Customer Journey Analytics.

### Para clientes que ainda não têm acesso ao Customer Journey Analytics

Para gerar dinamicamente etapas de atualização para as circunstâncias exclusivas de sua organização:

1. Entre em contato com a equipe de conta da Adobe para concluir o Guia de atualização do Customer Journey Analytics.

   A equipe de conta da Adobe pode orientá-lo no guia de atualização e fornecer um arquivo .csv que contém as perguntas, as respostas e as etapas de atualização geradas dinamicamente e exclusivas da organização.

   Antes de entrar em contato com sua equipe de conta da Adobe Systems, familiarize-se com as perguntas incluídas no Guia de atualização Customer Journey Analytics e determine suas respostas. O Guia de atualização do Customer Journey Analytics contém as seguintes perguntas e possíveis respostas:


   | Pergunta | Respostas disponíveis | Informações adicionais |
   |---------|----------|---------|
   | Selecione a opção que descreve a sua implementação atual do Adobe Analytics. Estas informações podem afetar as opções de atualização alternativas disponíveis ao atualizar para o Customer Journey Analytics. | Selecione uma opção: <ul><li>**AppMeasurement:**<br/> um JavaScript implementação que carrega AppMeasurement.js em um página e envia dados para Adobe Systems usando o objeto s (por exemplo, s.eVar1).</li><li>**Extensão do Adobe Analytics (marcas):** <br/>Uma implementação de marcas que carrega a Coleção de Dados do Adobe Experience Platform (anteriormente conhecida como Launch). A tag tem a extensão Adobe Analytics instalada.</li><li>**Extensão do Experience Platform Web SDK (marcas):**<br/> Uma implementação de marcas que carrega a Coleção de Dados do Adobe Experience Platform (anteriormente conhecida como Launch). A tag tem a extensão do SDK da web instalada.</li><li>**Experience Platform Web SDK (alloy.js):** uma implementação do JavaScript que carrega a biblioteca do Web SDK (alloy.js) em uma página e envia dados para o Adobe usando uma carga JSON.</li><li>**API de Inserção de Dados em Massa:**<br/> uma implementação que usa a API de inserção de dados ou a API de inserção de dados em massa.</li><li>**Experience Platform Publicação de conteúdo para dispositivos móveis SDK:**<br/> uma implementação que usa o SDK Publicação de conteúdo para dispositivos móveis Adobe Experience Platform.</li><li>**AppMeasurement usando uma gerenciamento de tags de terceiros ferramenta:**<br/> uma implementação que usa um ferramenta de gerenciamento de tags de terceiros.</li><li>**Um produto não Adobe Analytics:**<br/> um implementação que coleta dados para um produto diferente de Adobe Analytics, como Google Analytics. Selecionar essa opção desativa várias opções no guia de atualização que não se aplicam ao atualizar para Customer Journey Analytics de um produto não Adobe Analytics. </li><li>**Não sei:**<br/> se você não for a pessoa que gerencia sua implementação, poderá selecionar temporariamente esta opção.</li></ul><p>Selecione se aplicável:<ul><li>**Nossa implementação usa atualmente o conector de origem do Analytics:**<br/> O conector de origem do Analytics permite que você obtenha facilmente valor do Customer Journey Analytics, mas exige que você pague pelo Adobe Analytics e pelo Customer Journey Analytics. Este guia pode ajudar a avançar para uma implementação independente do SDK da web.</li></ul></p> | <ul><li>[Entenda sua implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transição do conector de origem do Analytics para o Web SDK para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | A maioria dos recursos do Adobe Analytics estão prontamente disponíveis no Customer Journey Analytics. No entanto, os seguintes recursos devem ser levados em consideração durante o processo de atualização. Selecione qualquer um que você planeje usar. | Selecione todas as respostas corretas:<ul><li>**Dados históricos do Adobe Analytics:**</br> Traga seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics.</li><li>**Componentes e projetos do Adobe Analytics:**</br> Os componentes do Adobe Analytics incluem: projetos (com suas tabelas e visualizações de forma livre associadas), segmentos e métricas calculadas.</li><li>**Sobreposição de mapa de atividades e rastreamento de link:**</br> Uma extensão de navegador que permite que você veja os dados de rastreamento de link como uma sobreposição no seu site.</li><li>**Dados de classificação:**</br> Agrupar ou categorizar dados como dimensões separadas.</li><li>**Canais de marketing:**</br> crie regras que categorizem como os clientes chegam ao site.</li><li>**Data Warehouse:**</br> Exportar dados processados do Adobe Analytics em formato de planilha.</li><li>**Feeds de dados:**uma substituição exata para Feeds de dados ainda não está disponível no Customer Journey Analytics. No entanto, uma funcionalidade semelhante pode ser obtida com recursos como exportação de tabela completa, exportação de conjunto de dados da plataforma, integração da ferramenta de BI e a API de relatórios.</br></li><li>**Dados de mídia de streaming:**</br> Um complemento do Adobe Analytics e do Customer Journey Analytics especializado na coleta de dados de mídia, como áudio, vídeo ou conteúdo de streaming.</li></ul> | <ul><li>[Entender o suporte a recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | A maioria dos novos recursos estão prontamente disponíveis no Customer Journey Analytics. No entanto, os seguintes recursos devem ser levados em consideração durante o processo de atualização. Selecione qualquer um que você planeje usar. | Selecione todas as respostas corretas:<ul><li>**Unir dados coletados com dados de outras fontes (por exemplo, dados da central de contatos):**</br>(Recomendado) Unir dados de várias propriedades da Web, móveis e offline para criar uma visão única e consolidada do comportamento do cliente. Essa capacidade de combinar dados análise de outros canais é o principal caso de uso para Customer Journey Analytics.</li><li>**Compilar ocorrências de outros conjuntos de dados usando uma dimensão personalizada:**<br/> Se algum dos seus conjuntos de dados não compartilhar um identificador principal (como uma Experience Cloud ID), você ainda poderá compilar esses dados usando outra dimensão, como nome de usuário de logon ou endereço de email.</li><li>**Integrar ao Adobe Journey Optimizer:**<br/> Fornecer experiências conectadas, contextuais e personalizadas aos clientes.</li><li>**Integrar com o Adobe Real-Time CDP:**<br/> Combine dados de perfil de várias fontes para gerar públicos e segmentos com base nas características do usuário.</li><li>**Integração com o Adobe Target (A4T):**<br/> A Adobe recomenda a integração com o Adobe Journey Optimizer para casos de uso de personalização. A integração com o Adobe Target é possível, mas uma solução de curto prazo.</li><li>**Integração com Adobe Audience Manager:**<br/> Adobe Systems recomenda a integração com Adobe Systems CDP em tempo real para casos de uso baseados em público-alvo. A integração com Audience Manager é possível, mas uma solução de curto prazo.</li></ul> | [Entender os recursos exclusivos do Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Selecione como você planeja usar o Adobe Analytics e o Customer Journey Analytics: | Selecione uma opção: <ul><li>**Pretendo migrar totalmente do Adobe Analytics para o Customer Journey Analytics:**<br/>(Recomendado) A Adobe recomenda que você faça a transição completa do Adobe Analytics para o Customer Journey Analytics. Durante o período de transição, você deve planejar a execução do Adobe Analytics junto com o Customer Journey Analytics para realizar comparações de dados lado a lado. Após se acostumar com os dados, desabilite o Adobe Analytics.</li><li>**Pretendo manter ambos os produtos do Analytics:**<br/>(Não recomendado) Se você selecionar essa opção, seu contrato com a Adobe incluirá Adobe Analytics e Customer Journey Analytics, o que pode ser mais caro para sua organização ao longo do tempo.</li></ul> | [Avalie quando desabilitar o Adobe Analytics após a atualização para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Selecione como você deseja configurar o seu esquema do Customer Journey Analytics: | Selecione uma opção: <ul><li>**Quero usar um esquema personalizado para minha organização:**</br>(Recomendado) A personalização do esquema permite que sua organização rastreie apenas o que você precisa e evite a sobrecarga associada a campos desnecessários e confusos. Essa opção inclui grupos de campos adicionados pelo SDK da web e grupos de campos personalizados para sua organização.</li><li>**Desejo usar o esquema padrão do Adobe Analytics:**</br>(Não recomendado) O esquema do Adobe Analytics contém mais de mil campos, o que pode levar a um esquema confuso e complexo. Sua organização seria forçada a continuar aderindo ao conceito de props e eVars, que é um conceito legado não usado no Customer Journey Analytics. A integração com outros serviços da Adobe Experience Platform é mais difícil.</li></ul> | [Escolha seu esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Selecione a sua maneira preferida de implementar o Customer Journey Analytics: | <ul><li>**Implementação manual (alloy.js):**<br/> Inclua a biblioteca do Web SDK (alloy.js) em cada página do seu site.</li><li>**Tags:**<br/>(Recomendado) Se você ainda não estiver usando Tags, instale o carregador de tag no seu site. Se você já estiver usando tags, poderá adicionar a extensão do SDK da web à propriedade da tag. Essa opção inclui implementações que usam tags na coleção de dados da Adobe Experience Platform e em sistemas de gerenciamento de tags de terceiros.</li><li>**API:**<br/> use a API coleção de dados para enviar dados diretamente para uma sequência de dados. Há suporte para os tipos não autenticados (cliente para servidor) e autenticados (servidor para servidor).</li></ul> | [Entenda as opções de implementação do SDK da Web ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Opcional) Selecione um método de atualização alternativo | <ul><li>**Soley use o conector de origem Analytics:**<br/>(Não recomendado) Você pode usar o conector de origem Analytics como o único implementação caminho para Customer Journey Analytics.<p>Essa opção economiza implementação tempo enviando rapidamente dados para Customer Journey Analytics. No entanto, ela inclui várias desvantagens, como maior latência e dificuldade para sair do Adobe Analytics no futuro.</p></li><li>**Quero usar minha lógica do AppMeasurement com o Web SDK:**<br/> Em vez de enviar dados por meio de um objeto XDM, envie todas as variáveis no formato AppMeasurement por meio do objeto de dados.<p>Essa opção economiza tempo de implementação, permitindo mapear a lógica do AppMeasurement para o XDM, em vez de preencher um objeto XDM do zero. No entanto, ela se torna mais complexa com o tempo, pois qualquer campo adicionado no futuro deve ser mapeado para o XDM no fluxo de dados.</p></li><li>**Quero enviar minha camada de dados para a Adobe sem configuração adicional:**<br/> Em vez de enviar dados por meio de um objeto XDM, você pode enviar toda a camada de dados para a Adobe por meio do objeto de dados.<p>Essa opção economiza implementação tempo, permitindo mapear sua camada de dados para XDM, em vez de preencher um objeto XDM do zero. No entanto, esse mapeamento é bastante trabalhoso devido à grande quantidade de dados que a Adobe não conseguirá interpretar prontamente. Essa opção também se torna mais complexa com o tempo, pois qualquer campo adicionado aos dados posteriormente deverá ser mapeado para o XDM no fluxo de dados.</p></li></ul> | <ul><li>[Alternativa de atualização: use o conector de origem Analytics exclusivamente para atualizar para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Alternativa de atualização: use o AppMeasurement coleção de dados com o Experience Platform Web SDK e Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Alternativa de atualização: envie sua camada de dados para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Após concluir este guia de atualização com sua equipe de conta da Adobe, você receberá um arquivo .csv que contém as perguntas, suas respostas e as etapas de atualização geradas dinamicamente que melhor se alinham com seu ambiente Adobe Analytics existente e suas metas do Customer Journey Analytics.

1. Siga as instruções detalhadas geradas no arquivo .csv para atualizar para o Customer Journey Analytics.

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
