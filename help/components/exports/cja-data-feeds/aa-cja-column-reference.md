---
title: Mapear colunas do feed de dados do Adobe Analytics para o Customer Journey Analytics
description: Determine como obter uma determinada coluna de feed de dados do Adobe Analytics e determine o equivalente bruto na implementação do Customer Journey Analytics.
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: b0be8b726c4fab1bf9bb5f9462be84f39bdf184a
workflow-type: tm+mt
source-wordcount: '3768'
ht-degree: 47%

---

# Mapear colunas do feed de dados do Adobe Analytics para o Customer Journey Analytics

Não é possível um mapeamento 1:1 verdadeiro entre as colunas de feed de dados do Adobe Analytics e do Customer Journey Analytics. Os dois produtos diferem fundamentalmente e a implementação de cada organização pode variar significativamente.

Essa referência ajuda os engenheiros de dados a avaliar as colunas do feed de dados do Adobe Analytics e identificar os equivalentes mais próximos do Customer Journey Analytics para seus workflows.

>[!NOTE]
>
>Esta referência inclui apenas colunas consideradas atuais pelo Adobe, com base na [referência de coluna de feed de dados do Analytics](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference). Se você tiver uma coluna de feed de dados do Analytics não listada nesta tabela que usa ativamente, consulte o documento de design de solução da sua organização para determinar seu melhor equivalente no Customer Journey Analytics.

+++**`accept_language`**

Lista todas as linguagens aceitas, conforme indicado no cabeçalho Linguagem aceita de HTTP em uma solicitação de imagem.

+++

+++**`adload`**

Cargas de anúncios de mídia

{{cja-df-post}}

+++

+++**`aemassetid`**

Uma variável multivalores correspondente às IDs de ativo (GUIDs) de um conjunto de ativos do Adobe Experience Manager. Incrementa eventos de impressão.

{{cja-df-post}}

+++

+++**`aemassetsource`**

Identifica a origem do evento de ativo. Usada no Adobe Experience Manager.

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

ID de ativo de um ativo do Adobe Experience Manager. Incrementa eventos de clique.

{{cja-df-post}}

+++

+++**`amo_cid`**

A dimensão ID do AMO, usada em integrações do Adobe Advertising.

{{cja-df-post}}

+++

+++**`amo_ef_id`**

A dimensão da ID AMO EF, usada em integrações do Adobe Advertising.

{{cja-df-post}}

+++

+++**`browser`**

Uma ID numérica que representa o navegador.

{{cja-df-lookup}}

+++

+++**`browser_height`**

A dimensão Altura do navegador.

{{cja-df-post}}

+++

+++**`browser_width`**

A largura do navegador

{{cja-df-post}}

+++

+++**`campaign`**

A dimensão Código de rastreamento.

{{cja-df-post}}

+++

+++**`carrier`**

Especifica a operadora de celular.

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

A dimensão Seções do site.

{{cja-df-post}}

+++

+++**`ch_hdr`**

Dicas do cliente coletadas por meio do cabeçalho de solicitação HTTP.

No Adobe Analytics, as dicas do cliente foram incluídas como uma sequência concatenada nessa coluna. É considerada uma abordagem mais moderna do que a coluna `user_agent`.

{{cja-df-ua}}

+++

+++**`ch_js`**

Dicas do cliente coletadas por meio da API JavaScript de dicas do cliente de usuário-agente.

No Adobe Analytics, as dicas do cliente foram incluídas como uma sequência concatenada nessa coluna. É considerada uma abordagem mais moderna do que a coluna `user_agent`.

Você pode coletar esses dados usando a cadeia de contexto [`highEntropyUserAgentHints`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context) ao configurar o Web SDK. Vários campos XDM são preenchidos em vez de uma longa string concatenada:

* **Versão do sistema operacional**: `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **Arquitetura**: `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **Modelo do dispositivo**: `xdm.environment.browserDetails.userAgentClientHints.model`
* **Bits**: `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **Fornecedor do navegador**: `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **Nome do navegador**: `xdm.environment.browserDetails.userAgentClientHints.brand`
* **Versão do navegador**: `xdm.environment.browserDetails.userAgentClientHints.version`

Consulte [User agent client hints](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) para obter mais informações.

{{cja-df-ua}}

+++

+++**`clickmaplink`**

A dimensão do link Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Essa coluna não se aplica porque o Customer Journey Analytics ainda não oferece suporte ao Activity Map.

+++

+++**`clickmaplinkbyregion`**

A dimensão Link por região do Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Essa coluna não se aplica porque o Customer Journey Analytics ainda não oferece suporte ao Activity Map.

+++

+++**`clickmappage`**

A dimensão da página do Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Essa coluna não se aplica porque o Customer Journey Analytics ainda não oferece suporte ao Activity Map.

+++

+++**`clickmapregion`**

A dimensão Região do Activity Map.

{{cja-df-post}}

{{cja-df-na}}

Essa coluna não se aplica porque o Customer Journey Analytics ainda não oferece suporte ao Activity Map.

+++

+++**`code_ver`**

Versão da API ou SDK cliente usada para compilar e enviar a solicitação de imagem.

+++

+++**`color`**

ID de Intensidade de cor com base no valor da coluna `c_color`.

{{cja-df-lookup}}

+++

+++**`connection_type`**

ID numérica que representa a dimensão Tipo de conexão.

{{cja-df-lookup}}

+++

+++**`cookies`**

A dimensão Suporte a cookies.<br>Y: Habilitado<br>N: Desabilitado<br>U: Desconhecido

{{cja-df-post}}

+++

+++**`country`**

Uma ID numérica que representa o país do visitante. Faz referência à tabela de pesquisa `country.tsv`.

{{cja-df-lookup}}

+++

+++**`currency`**

O código da moeda que foi usado durante a transação. Defina usando o `currencyCode`.

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

Relacionado à coluna `connection_type`. Os valores mais comuns são LAN/Wifi, Operadora de celular e Modem.

+++

+++**`curr_factor`**

Determina a casa decimal da moeda. Usado para conversão de moeda. Por exemplo, USD usa duas casas decimais, então esse valor de coluna seria `2`.

+++

+++**`curr_rate`**

A taxa de câmbio de quando a transação ocorreu. A Adobe faz parceria com a XE para determinar a taxa de câmbio do dia atual.

+++

+++**`customer_perspective`**

Determina se a ocorrência é uma ocorrência em segundo plano móvel.

{{cja-df-post}}

{{cja-df-na}}

O Customer Journey Analytics não tem um conceito nativo de tipo de evento em que ele inclui ou exclui automaticamente ocorrências com base no contexto da ocorrência. Você pode usar `xdm.eventType` para ajudar a determinar quais eventos devem ser incluídos e excluídos na maioria dos relatórios.

+++

+++**`cust_hit_time_gmt`**

Somente conjuntos de relatório com carimbos de data e hora habilitados. O carimbo de data e hora enviado com a ocorrência, com base no horário UNIX®.

O Customer Journey Analytics não tem um conceito de conjunto de relatórios de carimbo de data e hora versus não carimbo de data e hora. Em vez disso, use `xdm.timestamp` e ajuste as configurações do componente conforme desejado.

{{cja-df-post}}

+++

+++**`cust_visid`**

A ID de visitante personalizada, se definida usando `visitorID`.

O Customer Journey Analytics oferece suporte a qualquer número de identidades usando [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap). Se sua organização usa identidades personalizadas, provavelmente está no mapa de identidade.

{{cja-df-post}}

+++

+++**`c_color`**

Profundidade de bits da paleta de cores. Usado como parte do cálculo da dimensão Intensidade de cor. O AppMeasurement usa a função JavaScript `screen.colorDepth()`.

+++

+++**`daily_visitor`**

Um sinalizador que determina se a ocorrência é um novo visitante diário.

+++

+++**`dataprivacyconsentoptin`**

A dimensão Aceitação do gerenciamento de consentimento. Vários valores podem estar presentes por ocorrência, separados por uma barra vertical (`\|`). Os valores válidos incluem `DMP` e `SELL`.

Se sua organização tiver uma plataforma de gerenciamento de dados, ela provavelmente preencherá os campos XDM desejados para essa dimensão.

+++

+++**`dataprivacyconsentoptout`**

A dimensão Recusa no gerenciamento de consentimento. Vários valores podem estar presentes por ocorrência, separados por uma barra vertical (`\|`). Os valores válidos incluem `SSF`, `DMP` e `SELL`.

Se sua organização tiver uma plataforma de gerenciamento de dados, ela provavelmente preencherá os campos XDM desejados para essa dimensão.

+++

+++**`date_time`**

O horário da ocorrência em formato legível, com base no fuso horário do conjunto de relatórios.

Você pode usar `xdm.timestamp` e aplicar a configuração de componente **[!UICONTROL Data]** ou **[!UICONTROL Data-hora]** [Formato](/help/data-views/component-settings/format.md).

+++

+++**`domain`**

A dimensão Domínio. Com base no ponto de acesso de Internet do visitante.

Habilitar **[!UICONTROL Pesquisa de rede]** ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure). O campo XDM é `xdm.environment.domain` se estiver incluído no esquema.

+++

+++**`duplicated_from`**

Somente usado em conjuntos de relatórios contendo uma cópia da ocorrência com regras VISTA. Indica de qual conjunto de relatórios a ocorrência foi copiada.

{{cja-df-na}}

Essa coluna não se aplica porque o Customer Journey Analytics não tem um conceito de regras VISTA.

+++

+++**`duplicate_events`**

Lista cada evento que foi contado como duplicado.

{{cja-df-na}}

O Customer Journey Analytics não tem um campo único que atue como um sinalizador de desduplicação para todas as métricas. Em vez disso, cada métrica contém suas próprias [Configurações do componente de desduplicação de métrica](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication). Dessa forma, não há um campo equivalente no Customer Journey Analytics para essa coluna do feed de dados do Adobe Analytics.

+++

+++**`duplicate_purchase`**

Um sinalizador que determina se o evento de compra para esta ocorrência é ignorado por estar duplicado.

Embora não haja uma tradução direta para essa coluna do feed de dados do Analytics, sua funcionalidade de agir para desduplicar compras ainda existe. Se estiver usando o grupo de campos [[!UICONTROL Detalhes do Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), você poderá definir [Configurações do componente de desduplicação de métrica](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication), onde a **[!UICONTROL ID de Desduplicação]** é `xdm.commerce.purchases.id`.

Se for necessária uma tradução direta quando você quiser um sinalizador de compras duplicadas, poderá usar um [Campo derivado](/help/data-views/derived-fields/derived-fields.md) usando a função **Desduplicar** no conjunto de regras.

+++

+++**`ef_id`**

A ID EF, usada em integrações do Adobe Advertising.

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

Variáveis personalizadas 1-250. Usado nas dimensões do eVar. Cada organização usa eVars de forma diferente. O melhor lugar para obter mais informações sobre como sua organização preenche as respectivas eVars é um documento de design de solução específico para sua organização.

{{cja-df-post}}

+++

+++**`event_list`**

Lista separada por vírgulas de IDs numéricas que representam eventos acionados na ocorrência. Inclui eventos comerciais e eventos personalizados 1-1000. Usa a pesquisa `event.tsv`.

Essa coluna provavelmente mapeia dezenas de métricas separadas, dependendo da implementação. A Adobe recomenda o seguinte processo para mapear cada métrica respectiva no Customer Journey Analytics ao seu valor numérico representado nesta coluna de feed de dados do Analytics:

1. Use a pesquisa `event.tsv` para mapear cada valor numérico para seu nome de métrica.
1. Use o documento de design da solução para mapear cada nome de evento do Analytics para o nome de métrica correspondente no Customer Journey Analytics.
1. Selecione o componente mapeado na interface de Visualizações de dados e anote a ID do componente. Se a ID do componente for muito difícil de controlar, você poderá preencher o campo de ID de alias do feed de dados e usá-lo.
1. Repita o processo para cada métrica que sua organização usa.

{{cja-df-post}}

Se o esquema usar o grupo de campos [[!UICONTROL Detalhes do Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), algumas métricas poderão mapear diretamente para os seguintes campos XDM:

* **Check-outs**: `xdm.commerce.checkouts.value`
* **Adições ao carrinho**: `xdm.commerce.productListAdds.value`
* **Aberturas do carrinho**: `xdm.commerce.productListOpens.value`
* **Remoções do carrinho**: `xdm.commerce.productListRemovals.value`
* **Exibições do carrinho**: `xdm.commerce.productListViews.value`
* **Exibições do produto**: `xdm.commerce.productViews.value`
* **Pedidos**: `xdm.commerce.purchases.value`

Algumas métricas podem usar a serialização de eventos, que é a forma como o Adobe Analytics permite o controle total sobre a desduplicação. Você pode usar a configuração do componente [Desduplicação de métrica](/help/data-views/component-settings/metric-deduplication.md) para obter a paridade de desduplicação.

* Se a sua métrica for desduplicada por visita no Adobe Analytics, você poderá definir o escopo de desduplicação para sessão nas configurações de componente dessa métrica.
* Se sua métrica for desduplicada por ID de evento no Adobe Analytics, é provável que o objeto XDM para essa métrica contenha um campo `value` e `id`. Se o esquema usar o grupo de campos [[!UICONTROL Detalhes do Commerce]](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details), essas métricas provavelmente residirão nesses campos XDM, que você pode definir para o campo **[!UICONTROL ID de Desduplicação]** nas configurações de componente da métrica:

   * **Check-outs**: `xdm.commerce.checkouts.id`
   * **Adições ao carrinho**: `xdm.commerce.productListAdds.id`
   * **Aberturas do carrinho**: `xdm.commerce.productListOpens.id`
   * **Remoções do carrinho**: `xdm.commerce.productListRemovals.id`
   * **Exibições do carrinho**: `xdm.commerce.productListViews.id`
   * **Exibições do produto**: `xdm.commerce.productViews.id`

Se você deseja desduplicar a métrica Pedidos, consulte `duplicate_purchase`.

+++

+++**`exclude_hit`**

Um sinalizador que determina se a ocorrência é excluída dos relatórios. A coluna `visit_num` não é incrementada para hits excluídos.

O Customer Journey Analytics não respeita as &quot;ocorrências excluídas&quot; prontas para uso. No entanto, é possível recriar essa funcionalidade se você tiver um campo XDM que sinaliza determinadas ocorrências a serem excluídas:

1. Verifique se o campo XDM que sinaliza as ocorrências excluídas está incluído como um componente (dimensão ou métrica, dependendo de como você configurou esse sinalizador). Selecionar [Ocultar componente nos relatórios](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) provavelmente é benéfico para este campo.
1. Em [Configurações de visualização de dados](/help/data-views/session-settings.md), selecione o menu suspenso **[!UICONTROL Adicionar segmento]** e selecione **[!UICONTROL Criar segmento]**.
1. Crie um segmento que exclua todos os eventos em que o componente de ocorrência de exclusão existe ou contém valores que você deseja excluir.
1. Selecione **[!UICONTROL Salvar]** no segmento e na visualização de dados.

As ocorrências excluídas agora não existem nos relatórios do Customer Journey Analytics, mas ainda estão disponíveis nas exportações do feed de dados.

+++

+++**`first_hit_pagename`**

A dimensão Original da página de entrada. O nome da página de entrada original do visitante.

+++

+++**`first_hit_page_url`**

O primeiro URL do visitante.

+++

+++**`first_hit_referrer`**

O primeiro URL referenciador do visitante.

+++

+++**`first_hit_ref_domain`**

A dimensão Domínio referenciador original. Baseado em `first_hit_referrer`. O primeiro domínio de referência do visitante.

+++

+++**`first_hit_ref_type`**

Uma ID numérica que representa o tipo do primeiro referenciador do visitante.

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

Carimbo de data e hora da primeira ocorrência de um(a) visitante, com base no horário UNIX®.

+++

+++**`geo_city`**

O nome da cidade na qual a ocorrência foi originada, com base no IP. Usado na dimensão Cidades.

+++

+++**`geo_country`**

A abreviação do país no qual a ocorrência foi originada, com base no IP. Usado na dimensão Países.

+++

+++**`geo_dma`**

Uma ID numérica da área demográfica em que a ocorrência foi originada, com base no IP. Usado na dimensão US DMA.

+++

+++**`geo_region`**

O nome do estado ou região em que a ocorrência foi originada, com base no IP. Usado na dimensão Regiões.

+++

+++**`geo_zip`**

O código postal no qual a ocorrência foi originada, com base no IP. Ajuda a preencher a dimensão CEP. Consulte também `zip`.

+++

+++**`hitid_high`**

Usado em combinação com `hitid_low` para identificar uma ocorrência.

+++

+++**`hitid_low`**

Usado em combinação com `hitid_high` para identificar uma ocorrência.

+++

+++**`hit_source`**

A origem da ocorrência. As fontes de ocorrência 1 e 2 são cobradas. <br>1: Solicitação de imagem padrão sem carimbo de data/hora <br>2: Solicitação de imagem padrão com carimbo de data/hora <br>3: Carregamento de fonte de dados ao vivo com carimbos de data/hora <br>4: Não utilizado <br>5: Carregamento de fonte de dados genérica <br>6: Deixar de ser utilizado; Carregamento completo da fonte de dados de processamento <br>7: Carregamento da fonte de dados TransactionID <br>8: Deixar de ser utilizado; Versões anteriores das fontes de dados do Adobe Advertising <br>9: Deixar de ser utilizado; Métricas de resumo do Adobe Social <br>10: Encaminhamento do Audience Manager usado

+++

+++**`hit_time_gmt`**

O carimbo de data e hora de quando os servidores de coleta de dados de ocorrências da Adobe receberam a ocorrência, com base no horário UNIX®.

+++

+++**`hourly_visitor`**

Um sinalizador que determina se a ocorrência é um novo visitante por hora.

+++

+++**`ip`**

O endereço IPv4, com base no cabeçalho HTTP da solicitação de imagem. Mutualmente exclusivo de `ipv6`; se essa coluna contiver um endereço IP não ofuscado, `ipv6` está em branco.

+++

+++**`ipv6`**

O endereço IPv6 compactado, se disponível. Mutualmente exclusivo de `ip`; se essa coluna contiver um endereço IP não ofuscado, `ip` está em branco.

+++

+++**`javascript`**

Uma ID de pesquisa da versão do JavaScript, com base em `j_jscript`.

{{cja-df-lookup}}

+++

+++**`java_enabled`**

A dimensão Java ativado. <br>Y: Habilitado <br>N: Desabilitado <br>U: Desconhecido

{{cja-df-post}}

+++

+++**`j_jscript`**

A versão do JavaScript suportada pelo navegador.

+++

+++**`language`**

Uma ID numérica que representa o idioma do visitante.

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

Carimbo de data e hora (em horário UNIX®) da ocorrência anterior. Usado para calcular a dimensão Dias desde a última visita.

+++

+++**`last_purchase_num`**

A dimensão Fidelização do cliente. O número de compras que o visitante fez anteriormente. <br>0: Nenhuma compra anterior (não é um cliente) <br>1: 1 compra prévia (novo cliente) <br>2: 2 compras anteriores (cliente recorrente) <br>3: 3 ou mais compras anteriores (cliente fidelizado)

+++

+++**`last_purchase_time_gmt`**

Usado na dimensão Dias desde a última compra. Carimbo de data e hora (em horário UNIX®) da última compra feita. Para compras feitas pela primeira vez e visitantes que ainda não fizeram uma compra, esse valor é `0`.

+++

+++**`latlon1`**

Localização (abaixo de 10 km)

+++

+++**`latlon23`**

Localização (abaixo de 100 m)

+++

+++**`latlon45`**

Localização (abaixo de 1 m)

+++

+++**`mcvisid`**

ID de visitante da Experience Cloud. Número de 128 bits que consiste em dois números concatenados de 64 bits preenchidos com 19 dígitos.

+++

+++**`mc_audiences`**

Lista de IDs de segmento do Audience Manager à qual o visitante pertence. A coluna `post_mc_audiences` altera o delimitador para `--**--`.

{{cja-df-post}}

+++

+++**`mobileaction`**

Ação em dispositivo móvel. Coletado automaticamente quando `trackAction` é chamado em implementações móveis. Permite a criação de caminhos de ação automática no aplicativo.

{{cja-df-post}}

+++

+++**`mobileappid`**

ID do aplicativo móvel. Armazena o nome e a versão do aplicativo no seguinte formato: `[AppName] [BundleVersion]`. 

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

Usado no conector de dados Apteligent. O ID do aplicativo usado no Apteligent.

+++

+++**`mobileappperformancecrashid`**

Usado no conector de dados Apteligent. O ID de falha usado no Apteligent.

+++

+++**`mobileappstoreobjectid`**

Usado no conector de dados [!DNL Appfigures]. ID do objeto na loja de aplicativos.

+++

+++**`mobilebeaconmajor`**

Beacon do Mobile Services maior

+++

+++**`mobilebeaconminor`**

Beacon do Mobile Services menor

+++

+++**`mobilebeaconproximity`**

Proximidade de beacon do Mobile Services

+++

+++**`mobilebeaconuuid`**

UUID de beacon do Mobile Services

+++

+++**`mobilecampaigncontent`**

O nome ou a ID do conteúdo que exibiu o link. Preenchido pela Aquisição do dispositivo móvel.

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

Meio de marketing, como banner ou email. Preenchido pela Aquisição do dispositivo móvel.

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

O nome da campanha, também armazenado na variável da campanha. Preenchido pela Aquisição do dispositivo móvel.

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

Referenciador original, como informativos ou redes sociais. Preenchido pela Aquisição do dispositivo móvel.

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

Palavras-chave pagas ou outros termos que você deseja rastrear com essa aquisição. Preenchido pela Aquisição do dispositivo móvel.

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

Dia da semana no qual o aplicativo foi inicializado.

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

Número de dias desde a primeira execução do aplicativo.

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

Número de dias desde a execução mais recente do aplicativo.

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

Coletada da variável de dados de contexto `a.deeplink.id`. Usado nos relatórios de aquisição como um identificador para o link de aquisição móvel.

+++

+++**`mobiledevice`**

Nome do dispositivo móvel. No iOS, ele é armazenado como uma string de 2 dígitos separada por vírgulas. O primeiro número representa a geração do dispositivo e o segundo representa a família do dispositivo.

{{cja-df-post}}

+++

+++**`mobilehourofday`**

Define a hora do dia em que o aplicativo foi inicializado. Segue um formato numérico de 24 horas.

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Data de instalação móvel. Fornece a data da primeira vez que um usuário abriu o aplicativo móvel.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

Há um aumento de um cada vez que o aplicativo é inicializado.

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

Coletada da variável de dados de contexto `a.message.button.id`. Usado para mensagens no aplicativo para identificar o botão que fechou a mensagem.

{{cja-df-post}}

+++

+++**`mobilemessageid`**

ID da mensagem no aplicativo

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

Mensagens no aplicativo online

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

Coletada da variável de dados de contexto `a.push.optin`. Defina como &quot;true&quot; quando o usuário optar por enviar mensagens de push; caso contrário, o valor será &quot;false&quot;.

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

Coletada da variável de dados de contexto `a.push.payloadid`. Usado em mensagens de push como o identificador de carga.

{{cja-df-post}}

+++

+++**`mobileosversion`**

Versão do sistema operacional do Mobile Services

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

Coletada da variável de dados de contexto `a.loc.acc`. Indica a precisão do GPS em metros no momento da coleta.

+++

+++**`mobileplacecategory`**

Coletada da variável de dados de contexto `a.loc.category`. Descreve a categoria de um local específico.

+++

+++**`mobileplaceid`**

Coletada da variável de dados de contexto `a.loc.id`. Identificador para um determinado ponto de interesse.

+++

+++**`mobilepushoptin`**

Aceitação por push do Mobile Services

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

ID do conteúdo de push do Mobile Services

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Conteúdo de inicialização do Mobile Services

+++

+++**`mobilerelaunchcampaignmedium`**

Meio de lançamento do Mobile Services

+++

+++**`mobilerelaunchcampaignsource`**

Fonte de lançamento do Mobile Services

+++

+++**`mobilerelaunchcampaignterm`**

Termo de lançamento do Mobile Services

+++

+++**`mobilerelaunchcampaigntrackingcode`**

Coletada da variável de dados de contexto `a.launch.campaign.trackingcode`. Usado na aquisição como o código de rastreamento para a campanha de lançamento.

+++

+++**`mobileresolution`**

Resolução do dispositivo móvel. `[Width] x [Height]` em pixels.

{{cja-df-post}}

+++

+++**`mobile_id`**
Se o visitante estiver usando um dispositivo móvel, o ID numérico do dispositivo.

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

Um sinalizador que determina se o visitante é único no mês atual.

+++

+++**`mvvar1`** - **`mvvar3`**

Lista de valores de variáveis. Contém uma lista delimitada de valores personalizados dependendo da implementação. As colunas `post_mvvar1` - `post_mvvar3` substituem o delimitador original por `--**--`.

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

Os valores da variável de lista que foram definidos na ocorrência atual. Substitui o delimitador original por `--**--`. As colunas `post` normalmente não contêm dados.

{{cja-df-post}}

+++

+++**`new_visit`**

Um sinalizador que determina se a ocorrência atual é uma nova visita. Definido pela Adobe após 30 minutos de inatividade da visita.

+++

+++**`os`**

Uma ID numérica que representa o sistema operacional do visitante. Com base na coluna `user_agent`. 

{{cja-df-lookup}}

Ao [configurar uma sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure), você pode habilitar a **[!UICONTROL Pesquisa de dispositivo]**. Se habilitado, marque a caixa de seleção **[!UICONTROL Sistema operacional]**. Isso preencherá automaticamente os seguintes campos XDM se você tiver incluído esses campos no esquema:

* **Fornecedor do sistema operacional**: `xdm.environment.operatingSystemVendor`
* **Nome do sistema operacional**: `xdm.environment.operatingSystem`
* **Versão do sistema operacional**: `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

A dimensão Página. Se a variável `pagename` estiver vazia, o Analytics usa `page_url`.

{{cja-df-post}}

+++

+++**`pagename_no_url`**

Semelhante a `pagename`, exceto que não retorna a `page_url`. Somente a coluna `post` está disponível.

{{cja-df-post}}

+++

+++**`page_event`**

O tipo de ocorrência enviado na solicitação da imagem (ocorrência padrão, link de download, link personalizado, link de saída).

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

Usado somente em solicitações de imagem de rastreamento de link. O URL do link de download, link de saída ou link personalizado clicado.

{{cja-df-post}}

+++

+++**`page_event_var2`**

Usado somente em solicitações de imagem de rastreamento de link. O nome personalizado (se especificado) do link. Define o Link personalizado, Link de download ou Link de saída dependendo do valor em `page_event`.

{{cja-df-post}}

+++

+++**`page_type`**

A dimensão Páginas não encontradas, que é normalmente usada para páginas 404.

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**: A URL da ocorrência. Usa um tipo de dados de texto.<br>**`post_page_url`**: removido para solicitações de imagem de rastreamento de link (`tl()`).

{{cja-df-post}}

+++

+++**`paid_search`**

Um sinalizador que determina se a ocorrência corresponde à detecção de pesquisa paga.

+++

+++**`persistent_cookie`**

Usada na dimensão Suporte à cookie persistente. Indica se o visitante aceita cookies que não são descartados após cada ocorrência.

{{cja-df-post}}

+++

+++**`pointofinterest`**

Nome do ponto de interesse do Mobile Services

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Centro de distância do Mobile Services ao ponto de interesse

{{cja-df-post}}

+++

+++**`product_list`**

A variável de página `products`. Ajuda a preencher várias dimensões e métricas, incluindo Categoria, Produto, Unidades e Receita.

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

Variáveis de tráfego personalizadas 1 - 75. Usado nas dimensões Prop.

{{cja-df-post}}

+++

+++**`purchaseid`**

Identificador exclusivo de uma compra, definido usando a variável `purchaseID`. Usado pela coluna `duplicate_purchase`.

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

Um sinalizador que determina se a ocorrência é um novo visitante trimestral.

+++

+++**`referrer`**

A dimensão Referenciador. Observe que, embora o `referrer` use um tipo de dados de varchar(255), o `post_referrer` usa um tipo de dados de varchar(244).

{{cja-df-post}}

+++

+++**`ref_domain`**

A dimensão Domínio referenciador. Com base na coluna `referrer`. 

+++

+++**`ref_type`**


Uma ID numérica que representa o tipo de referência da ocorrência. Usada na dimensão Tipo de referenciador.<br>1: Dentro do site<br>2: Outros sites<br>3: Mecanismos de pesquisa<br>4: Disco rígido<br>5: USENET<br>6: Digitado/Marcado (sem referenciador)<br>7: Email<br>8: Sem JavaScript<br>9: Redes Sociais<br>10: Ferramentas de IA de Conversação

+++

+++**`resolution`**

Uma ID numérica que representa a resolução do monitor. Usado na dimensão Resolução do monitor.

{{cja-df-lookup}}

+++

+++**`search_engine`**

Uma ID numérica que representa o mecanismo de pesquisa que direcionou o visitante ao site. Usado nas dimensões do Mecanismo de pesquisa.

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

Usado pela dimensão Todas as classificações da página de pesquisa. Indica em qual página dos resultados de pesquisa seu site foi exibido antes de o usuário clicar no seu site.

+++

+++**`secondary_hit`**

Um sinalizador que determina se a ocorrência é secundária. Normalmente origina-se da marcação de vários relatórios e regras VISTA que copiam ocorrências.

+++

+++**`sourceid`**

ID da origem

+++

+++**`stats_server`**

Fora de uso. Servidor interno da Adobe que processou o hit.

+++

+++**`s_kwcid`**

A ID de palavra-chave usada em integrações da Adobe Advertising 

{{cja-df-post}}

+++

+++**`s_resolution`**

Valor bruto da resolução da tela. Coletado usando a função do JavaScript `screen.width x screen.height`.

+++

+++**`tnt`**

Usado em integrações do Adobe Target. Representa todos os testes qualificados até o momento. O formato é: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`.

{{cja-df-post}}

+++

+++**`tnt_action`**

Usado em integrações do Adobe Target. Representa todos os testes para os quais o hit se qualificou.

{{cja-df-post}}

+++

+++**`tnt_instances`**

Usado em integrações do Adobe Target. Variável de instâncias do Target.

+++

+++**`transactionid`**

Um identificador exclusivo, em que vários pontos de dados podem ser carregados posteriormente por meio de fontes de dados. Coletado usando a variável `transactionID`.

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

Um sinalizador que indica que a solicitação de imagem foi truncada (uma ocorrência parcial foi recebida). <br>Y: Ocorrência truncada; ocorrência parcial recebida <br>N: Ocorrência não truncada; ocorrência total recebida

+++

+++**`t_time_info`**

Horário local do visitante. O formato é: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

Fora de uso. A ID numérica da ID do conjunto de relatórios. Use `username` no lugar dela.

+++

+++**`username`**

A ID de conjunto de relatórios da ocorrência.

+++

+++**`user_agent`**

A string de agente do usuário enviada no cabeçalho HTTP da solicitação de imagem.

+++

+++**`user_hash`**

Fora de uso. Hash na ID do conjunto de relatórios. Use `username` no lugar dela.

+++

+++**`user_server`**

Usado na dimensão Servidor.

{{cja-df-post}}

+++

+++**`va_closer_detail`**

A dimensão Detalhe do último contato.

+++

+++**`va_closer_id`**

Uma ID numérica que identifica a dimensão Canal de último contato.

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

A dimensão Detalhe de primeiro contato.

+++

+++**`va_finder_id`**

Uma ID numérica que identifica a dimensão Canal de primeiro contato.

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

Um sinalizador que identifica Instâncias do Canal de marketing.

+++

+++**`va_new_engagement`**

Um sinalizador que identifica Novos engajamentos no Canal de marketing.

+++

+++**`video`**

A dimensão Serviços de streaming de mídia de conteúdo.

{{cja-df-post}}

+++

+++**`videoad`**

A dimensão Serviços de streaming de mídia de anúncio.

{{cja-df-post}}

+++

+++**`videoadinpod`**

A dimensão Serviços de mídia de transmissão da posição do anúncio no pod.

{{cja-df-post}}

+++

+++**`videoadlength`**

A dimensão Serviços de mídia de transmissão de duração do anúncio (variável).

{{cja-df-post}}

+++

+++**`videoadname`**

A dimensão Serviços de mídia de transmissão do nome do anúncio (variável).

{{cja-df-post}}

+++

+++**`videoadplayername`**

A dimensão Serviços de mídia de streaming do nome do player do anúncio.

{{cja-df-post}}

+++

+++**`videoadpod`**

A dimensão Serviços de mídia de transmissão do pod de anúncio.

{{cja-df-post}}

+++

+++**`videoadvertiser`**

A dimensão Serviços de mídia de transmissão do anunciante.

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

A dimensão Serviços de mídia de transmissão de álbuns.

+++

+++**`videoaudioartist`**

A dimensão Serviços de streaming de mídia do artista.

+++

+++**`videoaudioauthor`**

A dimensão Serviços de mídia de transmissão do autor.

+++

+++**`videoaudiolabel`**

A dimensão Serviços de mídia de transmissão de rótulo.

+++

+++**`videoaudiopublisher`**

A dimensão Serviços de streaming de mídia do Publisher.

+++

+++**`videoaudiostation`**

A dimensão Serviços de mídia de transmissão da estação.

+++

+++**`videocampaign`**

A dimensão Serviços de mídia de transmissão da ID da campanha.

{{cja-df-post}}

+++

+++**`videochannel`**

A dimensão Serviços de mídia de transmissão do canal de conteúdo.

{{cja-df-post}}

+++

+++**`videochapter`**

A dimensão Serviços de streaming de mídia do capítulo.

{{cja-df-post}}

+++

+++**`videocontenttype`**

A dimensão Serviços de mídia de transmissão do tipo de conteúdo.

{{cja-df-post}}

+++

+++**`videodaypart`**

A dimensão Serviços de mídia de transmissão da parte do dia.

{{cja-df-post}}

+++

+++**`videoepisode`**

A dimensão Serviços de mídia de transmissão de episódio.

{{cja-df-post}}

+++

+++**`videofeedtype`**

A dimensão Serviços de mídia de transmissão do tipo de feed de mídia.

{{cja-df-post}}

+++

+++**`videogenre`**

A dimensão Serviços de streaming de mídia de gênero. Essa dimensão permite vários valores delimitados por vírgula na mesma ocorrência.

{{cja-df-post}}

+++

+++**`videolength`**

A dimensão Serviços de mídia de transmissão de duração do conteúdo (variável).

{{cja-df-post}}

+++

+++**`videomvpd`**

A dimensão Serviços de streaming de mídia da MVPD.

{{cja-df-post}}

+++

+++**`videoname`**

A dimensão Serviços de mídia de transmissão do nome do conteúdo (variável).

{{cja-df-post}}

+++

+++**`videonetwork`**

A dimensão Serviços de mídia de transmissão da rede.

{{cja-df-post}}

+++

+++**`videopath`**

A dimensão Serviços de mídia de transmissão do caminho de mídia.

{{cja-df-post}}

+++

+++**`videoplayername`**

A dimensão Serviços de mídia de streaming do nome do reprodutor de conteúdo.

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

A dimensão Serviços de mídia de transmissão da taxa de bits média.

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

A taxa de bits altera a dimensão de serviços de mídia de transmissão.

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

A dimensão Buffer events streaming media services.

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

A dimensão Serviços de mídia de transmissão da duração total do buffer.

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

A dimensão Dropped frames streaming media services.

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

A dimensão Erros nos serviços de mídia de transmissão.

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

A dimensão Serviços de mídia de streaming de IDs de erro externo. Essa dimensão permite vários valores na mesma ocorrência.

+++

+++**`videoqoeplayersdkerrors`**

A dimensão Serviços de mídia de streaming de IDs de erro do Player SDK. Essa dimensão permite vários valores na mesma ocorrência.

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

A dimensão Tempo para iniciar os serviços de streaming de mídia.

{{cja-df-post}}

+++

+++**`videoseason`**

A dimensão Serviços de mídia de transmissão da temporada.

{{cja-df-post}}

+++

+++**`videosegment`**

A dimensão Serviços de mídia de transmissão do segmento de conteúdo.

{{cja-df-post}}

+++

+++**`videosessionid`**

A dimensão Serviços de mídia de transmissão da ID da sessão de mídia.

{{cja-df-post}}

+++

+++**`videoshow`**

A dimensão Mostrar serviços de streaming de mídia.

{{cja-df-post}}

+++

+++**`videoshowtype`**

A dimensão Mostrar serviços de mídia de transmissão do tipo.

{{cja-df-post}}

+++

+++**`videostreamtype`**

A dimensão Serviços de mídia de transmissão do tipo Stream.

+++

+++**`visid_high`**

Usado em combinação com `visid_low` para identificar exclusivamente um(a) visitante.

{{cja-df-post}}

+++

+++**`visid_low`**

Usado em combinação com `visid_high` para identificar exclusivamente um(a) visitante.

{{cja-df-post}}

+++

+++**`visid_new`**

Um sinalizador que determina se a ocorrência contém uma ID de visitante recém-gerada.

+++

+++**`visid_timestamp`**

Se uma ID de visitante for recém-gerada, fornece o carimbo de data e hora no horário UNIX® de quando ela foi gerada.

+++

+++**`visid_type`**

Não destinado a uso externo; usado internamente pela Adobe para otimizar o processamento. Uma ID numérica que representa o método usado para identificar o visitante.<br>`0`: ID de visitante personalizado ou desconhecido/não aplicável<br>`1`: fallback de IP e agente de usuário <br>`2`: cabeçalho de assinante móvel HTTP <br>`3`: valor de cookie herdado (`s_vi`) <br>`4`: valor de cookie de fallback (`s_fid`) <br>`5`: serviço de identidade

{{cja-df-post}}

+++

+++**`visit_keywords`**

A dimensão Palavra-chave de pesquisa. Essa coluna usa um limite de caracteres não padrão de varchar(244) para acomodar a lógica de back-end usada pelo Adobe. A coluna pós-processada é `**post_keywords**`, não `**post_visit_keywords**`.

{{cja-df-post}}

+++

+++**`visit_num`**

A dimensão Número de visitas. Começa em 1, e incrementa a cada início de nova visita por visitante.

+++

+++**`visit_page_num`**

A dimensão Profundidade da ocorrência. Aumenta em 1 para cada ocorrência que o visitante gera. Redefine cada visita.

+++

+++**`visit_referrer`**

O primeiro referenciador da visita.

+++

+++**`visit_ref_domain`**

Com base na coluna `visit_referrer`. O primeiro domínio referenciador da visita.

+++

+++**`visit_ref_type`**

Uma ID numérica que representa o tipo do primeiro referenciador da visita.

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

Uma ID numérica que representa o primeiro mecanismo de pesquisa da visita.

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

Página da primeira ocorrência da visita.

+++

+++**`visit_start_page_url`**

URL da primeira ocorrência da visita.

+++

+++**`visit_start_time_gmt`**

Carimbo de data e hora (em horário UNIX®) da primeira ocorrência da visita.

+++

+++**`weekly_visitor`**

Um sinalizador que determina se a ocorrência é um novo visitante semanal.

+++

+++**`yearly_visitor`**

Um sinalizador que determina se a ocorrência é um novo visitante anual.

+++

+++**`zip`**

Ajuda a preencher a dimensão CEP. Consulte também `geo_zip`.

{{cja-df-post}}

+++
