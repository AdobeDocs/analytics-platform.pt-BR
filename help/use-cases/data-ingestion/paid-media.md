---
title: Assimilar Dados De Mídia Paga No Customer Journey Analytics
description: Saiba como assimilar dados de mídia paga por meio de conectores de origem do Adobe Experience Platform e preparar conexões, visualizações de dados e métricas no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%
---

# Assimilar e usar dados de mídia paga

Os dados de mídia paga incluem desempenho de publicidade e metadados de plataformas como [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] e [!DNL LinkedIn]. Este guia explica como assimilar esses dados na Adobe Experience Platform e disponibilizá-los no Customer Journey Analytics para relatórios e análise.

Os dados de mídia paga normalmente passam por três estágios:

1. As plataformas do Advertising fornecem dados de campanha, anúncios, ativos e desempenho.
1. A Adobe Experience Platform assimila esses dados por meio de um conector de origem e os armazena nos conjuntos de dados de mídia paga padrão.
1. O Customer Journey Analytics expõe os conjuntos de dados por meio de uma conexão e uma visualização de dados, para que você possa analisar os dados no Workspace.

Os dados de mídia paga são assimilados pelos conectores de origem do Experience Platform. Por exemplo, você pode usar o conector [!DNL Meta Ads] na categoria Advertising. Quando você conecta uma origem compatível, o Adobe provisiona os conjuntos de dados de mídia paga padrão com base no esquema de mídia paga global e nos grupos de campo.

## Pré-requisitos

Certifique-se de ter o seguinte acesso no Experience Platform:

* Permissão para exibir e gerenciar fontes.
* Permissão para criar esquemas, conjuntos de dados e fluxos de dados.
* Uma sandbox selecionada para trabalhar. Escolha a sandbox antes de prosseguir com as etapas de configuração.

Se você usar [!DNL Meta Ads] como origem, verifique também os seguintes pré-requisitos:

* Uma conta do [!DNL Meta Business Manager] com pelo menos uma conta de anúncios ativa que contém campanhas, conjuntos de anúncios, anúncios e ativos.
* Um aplicativo [!DNL Meta] autorizado para [!DNL Graph API] e [!DNL Marketing API], configurado no console do desenvolvedor [!DNL Meta] e vinculado a [!DNL Business Manager].
* `ads_read` e `ads_management` escopos aprovados para o aplicativo.
* Acesso no nível do anunciante ou superior para o usuário que autoriza a conexão.
* Verificado o acesso às contas de anúncio desejadas na interface do usuário do [!DNL Meta].

A autenticação para o conector usa [!DNL OAuth 2.0]. Durante a configuração, você faz logon e concede acesso ao conector. Como os tokens de acesso expiram, prepare-se para reautorizar a conexão se a concessão for revogada.

## Modelo de dados

A [configuração automática de mídia paga do Content Analytics](/help/content-analytics/config/paid-media.md) explica detalhadamente o modelo de dados de mídia paga. Essa configuração automática cria e configura os conjuntos de dados e componentes necessários em geral e para analisar o conteúdo especificamente.

Para entender o modelo de dados de mídia paga, consulte esta documentação. Use-a para decidir quais conjuntos de dados usar no Customer Journey Analytics. Os conectores de origem configurados geram esses conjuntos de dados.

## Assimilar dados de mídia paga

Use o processo a seguir para conectar uma origem e assimilar dados de mídia paga na Experience Platform:

1. Verifique se você tem as permissões de origem do Experience Platform e o acesso à plataforma de anúncios necessários.
1. No Experience Platform, vá para **[!UICONTROL Fontes]** > **[!UICONTROL Catálogo]** > **[!UICONTROL Advertising]**.
1. Verifique se você está na sandbox que contém os conjuntos de dados de mídia paga.
1. Selecione o conector que deseja usar, como **[!DNL Meta Ads]**. Selecione **[!UICONTROL Configurar]** para criar uma nova conexão ou selecione **[!UICONTROL Adicionar dados]** para adicionar mais dados a uma conexão existente.
1. Autentique com [!DNL OAuth 2.0] entrando com um usuário que tenha o acesso de nível de anunciante necessário.
1. Selecione as contas de publicidade, entidades e dados do insight que você deseja assimilar.
1. Verifique se os conjuntos de dados de pesquisa e de métricas de resumo foram provisionados corretamente.
1. Insira as configurações de fluxo de dados, confirme os conjuntos de dados de destino e configure a programação de assimilação.
1. Salve o fluxo de dados e monitore as execuções em **[!UICONTROL Fontes]** > **[!UICONTROL Fluxos de dados]**.
1. Valide se os conjuntos de dados de mídia paga padrão existem e contêm dados.

Antes de migrar para o Customer Journey Analytics, valide os dados assimilados:

* Confirme se os valores de entidade `GUID` e ID nativa estão preenchidos de forma consistente nas métricas de resumo e nos conjuntos de dados de pesquisa.
* Confirme se cada linha de métricas de resumo inclui um carimbo de data e hora.
* Confirme se os principais campos de relatórios, como dimensões (por exemplo: `channel`, `adNetwork`) e métricas (por exemplo: `impressions`, `clicks`, `spend`) contêm valores. Observe que nem todas as plataformas de origem preenchem alguns campos como `region`.
* Confirme se os valores de moeda e fuso horário são consistentes em todas as contas relevantes.

## Usar dados de mídia paga

A Customer Journey Analytics não cria relatórios diretamente sobre conjuntos de dados da Experience Platform. Em vez disso, você expõe os conjuntos de dados por meio de uma conexão e cria uma visualização de dados que define as dimensões, as métricas e a lógica usadas nos relatórios.

### Criar ou atualizar uma conexão

Use o processo a seguir para criar ou atualizar uma conexão:

1. No Customer Journey Analytics, [crie ou edite uma conexão existente](/help/connections/create-connection.md).
1. Selecione a sandbox que contém os conjuntos de dados de mídia paga como parte da configuração de conexão.
1. Adicione os conjuntos de dados de métricas de resumo como dados de resumo. Se vários conjuntos de dados de métricas de resumo estiverem disponíveis, use a [pesquisa](/help/connections/create-connection.md#add-datasets) para filtrar pelas classes `Paid Media` para identificar os conjuntos de dados corretos.
1. Adicione cada conjunto de dados de pesquisa como um conjunto de dados de pesquisa. Una o conjunto de dados de pesquisa aos dados de resumo usando os identificadores GUID de entidade correspondentes (as chaves globais geradas pela Adobe) para conta, campanha, grupo de anúncios, anúncio, ativo e experiência. Algumas plataformas de origem também oferecem suporte a associações em valores de ID nativos.
1. Opcionalmente, adicione dados do evento de sequência de cliques se desejar relacionar dados de mídia paga agregados a metadados compartilhados, como IDs, códigos de rastreamento ou parâmetros `UTM`.
1. Revise as [configurações específicas para cada conjunto de dados](/help/connections/create-connection.md#dataset-settings).
1. Salve a conexão e confirme se a conexão começa a preencher os dados retroativamente.

Os dados de mídia paga são dados agregados e não dependem da identificação de identidade no nível da pessoa. Os identificadores de entidade na tabela de resumo são usados para unir identidades semelhantes nas tabelas de pesquisa.

### Criar uma visualização de dados

Quando a conexão estiver pronta, será necessário criar ou editar uma ou mais visualizações de dados para a conexão:


1. No Customer Journey Analytics, [crie ou edite uma ou mais visualizações de dados](/help/data-views/create-dataview.md):
1. Defina as configurações padrão, como fuso horário e moeda.
1. Adicione os componentes necessários para a análise de mídia paga.

Incluir componentes, como os seguintes:

* **Dimensões**: campanha, canal, rede de anúncios, grupo de anúncios, anúncio, ativo, conta, região e tipo de dispositivo.
* **Métricas**: impressões, cliques, taxa de cliques, gastos, conversões, valor de conversão, compromissos e métricas relevantes de vídeo ou compartilhamento de impressão.
* **Campos derivados**: normalize ou classifique dimensões usando [análise](/help/data-views/derived-fields/derived-fields.md#url-parse), [expressões regulares](/help/data-views/derived-fields/derived-fields.md#regex-replace) ou [pesquisa](/help/data-views/derived-fields/derived-fields.md#lookup) lógica para produzir valores de canal e campanha consistentes em redes de anúncios.
* **Agrupamento de resumo**: [combine valores relacionados de vários conjuntos de dados em uma única dimensão de relatório](/help/data-views/component-settings/summary-data-group.md), como uma dimensão de canal pago unificada.
* **Métricas calculadas**: defina métricas de eficiência reutilizáveis, como CPC, CPM, CPA, CTR e taxa de conversão.

### Criar um projeto

Para relatar e analisar os dados de mídia paga, crie um projeto no Analysis Workspace.

## Validar

Use a lista de verificação a seguir para validar a implementação.

### Verificações do Adobe Experience Platform

* Confirme se as permissões de origem e o acesso à plataforma de anúncios estão em vigor.
* Confirme se o conector está autenticado e se o fluxo de dados está sendo executado de acordo com a programação.
* Confirme se todos os conjuntos de dados de mídia paga estão presentes e preenchidos.
* Confirme se os esquemas usam as classes de mídia paga global e os grupos de campos.
* Confirme se as chaves de junção, carimbos de data e hora e campos-chave de relatórios estão preenchidos.

### Verificações do Customer Journey Analytics

* Confirme se a conexão inclui o conjunto de dados de métricas de resumo e os seis conjuntos de dados de pesquisa.
* Confirme se a visualização de dados inclui as dimensões de publicidade e as métricas de mídia paga necessárias.
* Confirme se os campos derivados normalizam os valores do canal e da campanha conforme esperado.
* Confirme se o agrupamento de resumo consolida dados de várias redes onde necessário.
* Confirme se as métricas calculadas estão definidas para as taxas que sua organização usa.
* Confirme se os relatórios do Workspace estão alinhados aos relatórios da plataforma de anúncio de origem.


>[!MORELIKETHIS]
>
>[Conector de origem do Meta Ads](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Configuração automática de mídia paga do Content Analytics](/help/content-analytics/config/paid-media.md)
