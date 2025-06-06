---
title: Atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba mais sobre as etapas recomendadas ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 105b235c1a4791fd59cf65ae7f543a5fc08fc55d
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 99%

---

# Atualizar do Adobe Analytics para o Customer Journey Analytics

Ao atualizar do Adobe Analytics para o Customer Journey Analytics, você pode seguir as [etapas de atualização recomendadas](#recommended-upgrade-steps-for-most-organizations). Ou você pode [gerar dinamicamente etapas de atualização](#dynamically-generate-upgrade-steps-for-your-organization) para as circunstâncias exclusivas da sua organização.

## Etapas de atualização recomendadas para a maioria das organizações {#upgrade-process}

O processo recomendado de atualização do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do SDK da web da Experience Platform, que é o método de coleta de dados preferido para o Customer Journey Analytics. Juntamente com o SDK da web, a Adobe também recomenda o uso do conector de origem do Analytics para ajudar na transição para o Customer Journey Analytics. Use o conector de origem do Analytics para reter dados históricos do Adobe Analytics e executar uma comparação de dados lado a lado.

Depois de ter dados históricos suficientes usando o SDK da web da Experience Platform e ter feito a transição completa para o Customer Journey Analytics, o conector de origem do Analytics pode ser desativado e o SDK da web pode ser usado exclusivamente.

>[!NOTE]
>
>Se as etapas de atualização descritas nesta seção não forem práticas para sua organização, use o guia de atualização do Customer Journey Analytics para gerar dinamicamente etapas de atualização adaptadas às circunstâncias exclusivas da sua organização. (Para acessar o guia do Customer Journey Analytics, clique na guia **[!UICONTROL Espaço de trabalho]** e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.)

### Processo de atualização de alto nível recomendado {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Dados históricos do Adobe Analytics"
>abstract="Trazer seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implementar o SDK da web da Experience Platform (para coleção de dados contínua)**

   Uma nova implementação do SDK da web da Experience Platform é a melhor maneira de coletar dados para o Customer Journey Analytics. Ele fornece a melhor base para aproveitar ao máximo o Customer Journey Analytics, pois é o método mais eficiente, simples e à prova de obsolescência para implementar o Customer Journey Analytics.

   * Relatórios de alto desempenho e disponibilidade de dados porque a Adobe Experience Platform foi criada para potencializar casos de uso de personalização em tempo real

   * Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)

   * Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)

1. **Configure o conector de origem do Adobe Analytics (para trazer dados históricos)**

   Para ajudar a fazer uma transição descomplicada para o uso do SDK da web da Experience Platform com o Customer Journey Analytics, a Adobe também recomenda o uso do conector de origem do Adobe Analytics. Isso permite que você retenha dados históricos e exiba dados da sua implementação existente do Adobe Analytics no Customer Journey Analytics, lado a lado com os dados da sua nova implementação do SDK da web da Experience Platform.

   O conector de origem do Analytics permite:

   * Trazer seus dados históricos do conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics.

     Você pode manter o conector de origem do Analytics em execução por tanto tempo quanto for necessário manter os dados históricos do Adobe Analytics.

   * Visualize os dados coletados com sua implementação original do Adobe Analytics (AppMeasurement, a extensão do Analytics ou a extensão do SDK da web) no Customer Journey Analytics. Você pode comparar esses dados lado a lado com os da nova implementação do SDK da web.

     É possível manter o conector de origem do Analytics em execução até que você esteja familiarizado e acostumado com as diferenças. <!--elaborate on what those differences are? -->

   O conector de origem do Analytics como uma implementação independente não é um método recomendado de longo prazo para usar o Customer Journey Analytics. Isso se deve à alta latência, esquemas desorganizados e complexos, à dependência da nomenclatura do Adobe Analytics (prop, eVar e assim por diante) e à dificuldade de mudar do conector de origem do Analytics para a implementação recomendada do SDK da web.

### Etapas de atualização detalhadas recomendadas

As etapas a seguir descrevem o processo recomendado para atualizar do Adobe Analytics para o Customer Journey Analytics.

Cada etapa fornece uma explicação de alto nível de um processo mais detalhado. Siga o link para cada etapa e conclua suas tarefas associadas, retorne a essa página e continue para a próxima etapa do processo.

1. [Planeje sua arquitetura de esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}.

1. [Crie o esquema personalizado desejado na Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}.

   Considere as seguintes opções ao criar seu esquema:

   * Se quiser integrar o Customer Journey Analytics com a RTCDP, habilite a opção **[!UICONTROL Perfil]** no esquema, conforme descrito em [Criar um esquema XDM para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}. Com essa opção habilitada, quando os dados são assimilados em conjuntos de dados com base nesse esquema, esses dados são mesclados ao Perfil do cliente em tempo real.

   * Se quiser incluir dados de transmissão de mídia, você deve [configurar seu esquema para assimilar e usar dados de transmissão](/help/data-ingestion/streaming.md){target="_blank"}.

1. [Crie um conjunto de dados na Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md){target="_blank"}.

1. (Opcional) Se você usar dados de classificação no Adobe Analytics, poderá adicionar dados de classificação ao seu conjunto de dados no Customer Journey Analytics.

   Para fazer isso, [crie um conjunto de dados de pesquisa para cada dimensão contendo dados de classificação](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md){target="_blank"}.

1. Para implementações do Adobe Analytics usando o AppMeasurement ou a extensão (tags) do Analytics, [crie uma sequência de dados na Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md){target="_blank"}. <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   Para implementações do Adobe Analytics que usam o SDK da Web, já há uma sequência de dados disponível. Para obter mais informações, consulte [Configurar implementação existente do SDK da Web do Adobe Analytics para enviar dados para a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md){target="_blank"}.

1. [Adicione a Adobe Experience Platform como um serviço à sua sequência de dados](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md){target="_blank"}.

1. (Opcional) Se quiser integrar o Customer Journey Analytics ao Adobe Journey Optimizer, use o objeto de personalização na sua implementação para uso no Adobe Journey Optimizer.

1. Expanda a seção que descreve como você deseja implementar o SDK da web da Experience Platform para a sua implementação do Customer Journey Analytics e, em seguida, conclua as etapas associadas:

   +++Implementação manual (arquivo JS)

   1. [Adicione o alloy.js ao seu site](https://experienceleague.adobe.com/pt-br/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22){target="_blank"}.

   1. Preencha um objeto do XDM e envie-o à sequência de dados.

   +++

   +++Tags

   1. [Crie uma propriedade da tag e adicione a extensão do SDK da web da Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md){target="_blank"}.

   1. [Adicione a extensão Adobe Experience Platform Web SDK à propriedade da marca](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md){target="_blank"}.

   1. [Implemente a tag do carregador no seu site](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Adicione a lógica da coleção de dados do XDM à sua tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md){target="_blank"}.

   +++

+++ API

   1. Use a API da Edge Network para enviar dados à sequência de dados desejada.

+++

1. [Confirme que a sua implementação do SDK da web está enviando dados a um conjunto de dados](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md){target="_blank"}.

1. [Crie uma conexão no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md){target="_blank"}.

1. (Opcional) Vincule dados da web a dados de outros canais, como dados da central de atendimento.

   Para isso, adicione outros conjuntos de dados à sua conexão do Customer Journey Analytics, conforme descrito em [Importar dados da central de atendimento e da web](/help/use-cases/cross-channel/call-center.md){target="_blank"}.

1. [Crie uma visualização de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md){target="_blank"}.

1. [Confirme que os dados estão fluindo para a visualização de dados no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md){target="_blank"}.

1. Em seu ambiente do Adobe Analytics, [use o inventário do Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/analytics-inventory){target="_blank"} para ter uma visão geral abrangente do seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais.

1. [Migre projetos e componentes](https://experienceleague.adobe.com/pt-br/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration){target="_blank"}.

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Opcional) Caso você utilize canais de marketing no Adobe Analytics, é possível [criar um campo derivado de canal de marketing no Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"}.

   Os campos derivados são um aspecto importante dos relatórios em tempo real do Customer Journey Analytics. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável.

   Um uso dos campos derivados é definir um campo derivado de canal de marketing que determina o canal de marketing adequado com base em uma ou mais condições (por exemplo, parâmetro de URL, URL da página ou nome da página).

   Use [o modelo de função de canais de marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"} em campos derivados para criar um campo derivado para canais de marketing rapidamente.

1. Compare os dados da implementação antiga no Adobe Analytics com os dados da nova implementação no Customer Journey Analytics e certifique-se de entender as diferenças e por que elas existem. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Transfira dados históricos do Adobe Analytics por meio do conector de origem do Analytics:

   >[!NOTE]
   >
   >Use as etapas a seguir, caso não tenha criado um conector de origem do Analytics anteriormente.
   >
   >Se você já estiver usando o conector de origem do Analytics com o Customer Journey Analytics, siga as etapas apresentadas em [Transição do conector de origem do Analytics para o SDK da web do Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}.

   1. [Criar um esquema XDM para o conector de origem do Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md){target="_blank"}.

   1. Se você ainda não tiver um conector de origem do Analytics, [crie o conector de origem do Analytics e mapeie os campos para o esquema do XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md){target="_blank"}.

      Ou

      Se você já tiver um conector de origem do Analytics, [mapeie os campos do conector de origem para o esquema do XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}.

   1. [Adicione o conjunto de dados do conector de origem do Analytics à conexão](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md){target="_blank"}.

1. Planeje a integração de usuários.

   Como no Adobe Analytics, o Analysis Workspace é a principal ferramenta voltada para usuários do Customer Journey Analytics. No entanto, é necessário considerar algumas diferenças importantes de se usar o Analysis Workspace no Customer Journey Analytics.

   Dê a seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.

   Para mais informações sobre algumas das principais diferenças entre o Adobe Analytics e o Customer Journey Analytics, consulte o [Guia para usuários do Adobe Analytics](/help/getting-started/aa-to-cja-user.md){target="_blank"}.

1. Saiba mais sobre a [compatibilidade de recursos no Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md){target="_blank"}. A maioria dos recursos do Adobe Analytics é compatível com o Customer Journey Analytics, e muitos recursos adicionais estão disponíveis no Customer Journey Analytics.

1. Desabilite o Adobe Analytics quando a implementação do SDK da web do Customer Journey Analytics for concluída e você tiver se familiarizado com os dados a serem coletados.

   A Adobe recomenda que você mantenha o seu ambiente do Adobe Analytics em execução por um período após implementar o Customer Journey Analytics.

   Para mais informações sobre os usos do Adobe Analytics durante e após uma atualização, bem como o tempo sugerido para desabilitar o Adobe Analytics, consulte [Avaliar por quanto tempo você precisa do Adobe Analytics após a atualização para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md){target="_blank"}.

## Gerar dinamicamente etapas de atualização para a sua organização

Dependendo de vários fatores, como a linha do tempo e restrições de recursos, as etapas de atualização recomendadas descritas em [Entenda as etapas de atualização recomendadas](#recommended-upgrade-steps-for-most-organizations) podem não ser práticas para sua organização. Nesse caso, é possível gerar dinamicamente etapas de atualização para as circunstâncias específicas da sua organização. O processo de geração dessas etapas varia se você já tem acesso ao Customer Journey Analytics.

### Para clientes que têm acesso ao Customer Journey Analytics

Para gerar dinamicamente etapas de atualização para as circunstâncias únicas da sua organização:

1. Conclua o guia de atualização do Customer Journey Analytics.

   No Customer Journey Analytics, clique na guia **[!UICONTROL Espaço de trabalho]** e selecione **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.

   Após concluir este guia de atualização, você receberá instruções passo a passo que descrevem as etapas ideais de atualização para atender as necessidades específicas da sua organização. Estas são as etapas de atualização que melhor se alinham ao seu ambiente atual do Adobe Analytics e às suas metas para o Customer Journey Analytics. As etapas de atualização estão disponíveis como um link compartilhável ou como um arquivo .csv para download.

1. Siga as instruções passo a passo geradas para atualizar para o Customer Journey Analytics.

### Para clientes que ainda não têm acesso ao Customer Journey Analytics

Para gerar dinamicamente etapas de atualização para as circunstâncias únicas da sua organização:

1. Entre em contato com a equipe de contas da Adobe para concluir o guia de atualização do Customer Journey Analytics.

   A equipe de contas da Adobe oferece orientação sobre como usar o guia de atualização e fornece um arquivo .csv que contém as perguntas, as respostas e as etapas de atualização geradas dinamicamente para as necessidades exclusivas da sua organização.

   Antes de entrar em contato com sua equipe de contas da Adobe, familiarize-se com as perguntas incluídas no guia de atualização do Customer Journey Analytics e determine suas respostas. O guia de atualização do Customer Journey Analytics contém as seguintes perguntas e suas possíveis respostas:


   | Pergunta | Respostas disponíveis | Informações adicionais |
   |---------|----------|---------|
   | Selecione a opção que descreve a sua implementação atual do Adobe Analytics. Estas informações podem afetar as opções de atualização alternativas disponíveis ao atualizar para o Customer Journey Analytics. | Selecione uma opção: <ul><li>**AppMeasurement:**<br/> uma implementação JavaScript que carrega o AppMeasurement.js em uma página e envia dados para a Adobe usando o objeto s (por exemplo, s.eVar1).</li><li>**Extensão do Adobe Analytics (tags):** <br/>uma implementação de tags que carrega a coleção de dados da Adobe Experience Platform (anteriormente conhecida como Launch). A tag tem a extensão do Adobe Analytics instalada.</li><li>**Extensão do SDK da Web da Experience Platform (tags):**<br/> uma implementação de tags que carrega a coleção de dados da Adobe Experience Platform (anteriormente conhecida como Launch). A tag tem a extensão do SDK da web instalada.</li><li>**SDK da Web da Experience Platform (alloy.js):** uma implementação JavaScript que carrega a biblioteca de SDK da Web (alloy.js) em uma página e envia dados para a Adobe usando um conteúdo JSON.</li><li>**API de inserção de dados em massa:**<br/> uma implementação que usa a API de inserção de dados ou a API de inserção de dados em massa.</li><li>**SDK móvel da Experience Platform:**<br/> uma implementação que usa o SDK móvel da Adobe Experience Platform.</li><li>**AppMeasurement com uma ferramenta de gerenciamento de tags de terceiros:**<br/> uma implementação que usa uma ferramenta de gerenciamento de tags de terceiros.</li><li>**Um produto diferente do Adobe Analytics:**<br/> uma implementação que coleta dados para um produto diferente do Adobe Analytics, como o Google Analytics. Selecionar esta opção desabilita várias opções no guia de atualização que não se aplicam ao atualizar para o Customer Journey Analytics de um produto diferente do Adobe Analytics. </li><li>**Não sei:**<br/> se você não é a pessoa que gerencia a implementação, é possível selecionar temporariamente esta opção.</li></ul><p>Selecione se aplicável:<ul><li>**Nossa implementação atualmente usa o conector de origem do Analytics:**<br/> o conector de origem do Analytics permite aproveitar facilmente o Customer Journey Analytics, mas exige que você pague pelo Adobe Analytics e pelo Customer Journey Analytics. Este guia pode ajudar você a avançar para uma implementação independente do SDK da web.</li></ul></p> | <ul><li>[Entenda a implementação do Adobe Analytics e como ela afeta sua atualização para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transição do conector de origem do Analytics para o SDK da Web no Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | A maioria dos recursos do Adobe Analytics estão prontamente disponíveis no Customer Journey Analytics. No entanto, os seguintes recursos devem ser levados em consideração durante o processo de atualização. Selecione qualquer um que você planeje usar. | Selecione todas as respostas corretas:<ul><li>**Dados históricos do Adobe Analytics:**</br> traga os dados históricos do seu conjunto de relatórios do Adobe Analytics para a Adobe Experience Platform e o Customer Journey Analytics.</li><li>**Componentes e projetos do Adobe Analytics:**</br> os componentes do Adobe Analytics incluem projetos (com suas tabelas de forma livre e visualizações associadas), segmentos e métricas calculadas.</li><li>**Sobreposição de mapa de atividades e rastreamento de links:**</br> uma extensão do navegador que permite ver dados de rastreamento de link como uma sobreposição no seu site.</li><li>**Dados de classificação:**</br> agrupe ou categorize dados como dimensões separadas.</li><li>**Canais de marketing:**</br> crie regras que categorizem como os clientes chegam ao seu site.</li><li>**Data Warehouse:**</br> exporte dados processados do Adobe Analytics em formato de planilha.</li><li>**Feeds de dados**: ainda não existe um recurso totalmente equivalente aos feeds de dados disponível no Customer Journey Analytics. No entanto, é possível obter funcionalidades semelhantes com recursos como a exportação de tabela completa, exportação de conjunto de dados da plataforma, integração de ferramentas de BI e a API de relatórios.</br></li><li>**Dados de mídia de transmissão:**</br> um complemento do Adobe Analytics e do Customer Journey Analytics especializado na coleta de dados de mídia, como áudio, vídeo ou conteúdo transmitido.</li></ul> | <ul><li>[Entenda o suporte de recursos do Adobe Analytics ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | A maioria dos novos recursos estão prontamente disponíveis no Customer Journey Analytics. No entanto, os seguintes recursos devem ser levados em consideração durante o processo de atualização. Selecione qualquer um que você planeje usar. | Selecione todas as respostas corretas:<ul><li>**Vincule os dados coletados com dados de outras fontes (por exemplo, dados do centro de contatos):**</br> (Recomendado) vincule dados de várias propriedades da web, móveis e offline para criar uma exibição única e consolidada do comportamento do cliente. Essa capacidade de combinar dados analíticos de outros canais é o principal caso de uso do Customer Journey Analytics.</li><li>**Compile ocorrências de outros conjuntos de dados usando uma dimensão personalizada:**<br/> se algum dos seus conjuntos de dados não compartilhar um identificador primário (como uma ID da Experience Cloud), você ainda poderá compilar esses dados usando outra dimensão, como o nome de usuário de logon ou endereço de email.</li><li>**Integração com o Adobe Journey Optimizer:**<br/> ofereça experiências conectadas, contextuais e personalizadas aos clientes.</li><li>**Integração com a Adobe Real-Time CDP:**<br/> combine dados de perfil de várias fontes para gerar públicos-alvo e segmentos com base nas características do usuário.</li><li>**Integração com o Adobe Target (A4T):**<br/> a Adobe recomenda a integração com o Adobe Journey Optimizer para casos de uso de personalização. A integração com o Adobe Target é possível, mas é uma solução temporária.</li><li>**Integração com o Adobe Audience Manager:**<br/> a Adobe recomenda a integração com a Adobe Real-time CDP para casos de uso baseados em público-alvo. A integração com o Audience Manager é possível, mas é uma solução temporária.</li></ul> | [Entenda os recursos exclusivos do Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Selecione como você planeja usar o Adobe Analytics e o Customer Journey Analytics: | Selecione uma opção: <ul><li>**Pretendo migrar totalmente do Adobe Analytics para o Customer Journey Analytics:**<br/> (Recomendado) a Adobe recomenda que você faça a transição completa do Adobe Analytics para o Customer Journey Analytics. Durante o período de transição, você deve planejar a execução do Adobe Analytics junto com o Customer Journey Analytics para realizar comparações de dados lado a lado. Após se acostumar com os dados, desabilite o Adobe Analytics.</li><li>**Pretendo manter os dois produtos do Analytics:**<br/> (Não recomendado) se você selecionar esta opção, seu contrato com a Adobe incluirá o Adobe Analytics e o Customer Journey Analytics, o que pode ser mais caro para sua organização ao longo do tempo.</li></ul> | [Avalie quando é apropriado desabilitar o Adobe Analytics após atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Selecione como você deseja configurar o seu esquema do Customer Journey Analytics: | Selecione uma opção: <ul><li>**Quero usar um esquema adaptado à minha organização:**</br> (Recomendado) personalizar o esquema permite que a organização rastreie apenas o que é necessário e evita a sobrecarga associada a campos confusos e desnecessários. Esta opção inclui grupos de campos adicionados pelo SDK da Web e grupos de campos personalizados para sua organização.</li><li>**Quero usar o esquema padrão do Adobe Analytics:**</br> (Não recomendado) o esquema do Adobe Analytics contém mais de mil campos, o que pode resultar em um esquema desorganizado e complexo. Sua organização seria forçada a continuar aderindo ao conceito de props e eVars, que é um conceito legado não usado no Customer Journey Analytics. A integração com outros serviços da Adobe Experience Platform é mais difícil.</li></ul> | [Escolha seu esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Selecione a sua maneira preferida de implementar o Customer Journey Analytics: | <ul><li>**Implementação manual (alloy.js):**<br/> inclua a biblioteca do SDK da Web (alloy.js) em cada página do seu site.</li><li>**Tags:**<br/> (Recomendado) se você ainda não estiver usando tags, instale o carregador de tags no seu site. Se você já estiver usando tags, poderá adicionar a extensão do SDK da web à propriedade da tag. Essa opção inclui implementações que usam tags na coleção de dados da Adobe Experience Platform e em sistemas de gerenciamento de tags de terceiros.</li><li>**API:**<br/> use a API de coleção de dados para enviar dados diretamente para uma sequência de dados. Há suporte para os tipos não autenticados (cliente para servidor) e autenticados (servidor para servidor).</li></ul> | [Entenda as opções de implementação do SDK da Web ao atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Opcional) Selecione um método de atualização alternativo | <ul><li>**Use apenas o conector de origem do Analytics:**<br/> (Não recomendado) você pode usar o conector de origem do Analytics como o único caminho de implementação para o Customer Journey Analytics.<p>Esta opção economiza tempo de implementação enviando dados rapidamente para o Customer Journey Analytics. No entanto, ela inclui várias desvantagens, como maior latência e dificuldade para sair do Adobe Analytics no futuro.</p></li><li>**Quero usar minha lógica do AppMeasurement com o SDK da Web:**<br/> em vez de enviar dados por meio de um objeto XDM, envie todas as variáveis no formato do AppMeasurement por meio do objeto de dados.<p>Esta opção economiza tempo de implementação, permitindo que você mapeie sua lógica do AppMeasurement para o XDM, em vez de preencher um objeto XDM do zero. No entanto, ela se torna mais complexa com o tempo, pois qualquer campo adicionado no futuro deve ser mapeado para o XDM na sequência de dados.</p></li><li>**Quero enviar minha camada de dados para a Adobe sem configuração adicional:**<br/> em vez de enviar dados por meio de um objeto XDM, você pode enviar toda a sua camada de dados para a Adobe por meio do objeto de dados.<p>Esta opção economiza tempo de implementação, permitindo que você mapeie sua camada de dados para o XDM, em vez de preencher um objeto XDM do zero. No entanto, esse mapeamento é bastante trabalhoso devido à grande quantidade de dados que a Adobe não conseguirá interpretar prontamente. Essa opção também se torna mais complexa com o tempo, pois qualquer campo adicionado aos dados posteriormente deverá ser mapeado para o XDM no fluxo de dados.</p></li></ul> | <ul><li>[Alternativa de atualização: use o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Alternativa de atualização: use a coleção de dados do AppMeasurement com o SDK da Web da Experience Platform e o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Alternativa de atualização: envie sua camada de dados para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Após concluir este guia de atualização com sua equipe de contas da Adobe, você receberá um arquivo .csv que contém as perguntas, suas respostas e as etapas de atualização geradas dinamicamente para se alinhar ao seu ambiente atual do Adobe Analytics e às suas metas para o Customer Journey Analytics.

1. Siga as instruções passo a passo geradas no arquivo .csv para atualizar para o Customer Journey Analytics.

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
