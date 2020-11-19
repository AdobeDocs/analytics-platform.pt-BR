---
title: Usar dimensões do canal de marketing no Adobe Experience Platform
description: Use o Conector de dados do Analytics para trazer regras de processamento de Canais de marketing para o Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# Usar dimensões do canal de marketing no Adobe Experience Platform

Se sua organização usar o [Conector de dados do Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/sources/connectors/adobe-applications/analytics.html) para trazer dados do conjunto de relatórios para o CJA, você poderá configurar uma conexão no CJA para relatar as dimensões do Canal de marketing.

## Pré-requisitos

* Os dados do conjunto de relatórios já devem ser importados para o Adobe Experience Platform usando o [Conector de dados do Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). Outras fontes de dados não são suportadas, pois os canais de marketing dependem das regras de processamento em um conjunto de relatórios do Analytics.
* As regras de processamento de canais de marketing já devem estar configuradas. Consulte [Regras de processamento para Canais de marketing](https://docs.adobe.com/content/help/pt-BR/analytics/components/marketing-channels/c-rules.html) no guia tradicional Componentes do Analytics.

## Elementos do schema do Canal de marketing

Depois que você estabelecer o Conector de dados do Analytics em um conjunto de relatórios desejado, um schema XDM será criado para você. Esse schema contém todas as dimensões e métricas do Analytics como dados brutos. Esses dados brutos não contêm atribuição ou persistência. Em vez disso, cada evento é executado pelas regras de processamento de canais de marketing e registra a primeira regra correspondente. Você especifica a atribuição e a persistência ao criar uma visualização de dados no CJA.

1. [Crie uma ](/help/connections/create-connection.md) conexão que inclua um conjunto de dados com base no Conector de dados do Analytics.
2. [Crie uma ](/help/data-views/create-dataview.md) visualização de dados que inclua as seguintes dimensões:
   * **`channel.typeAtSource`**: Equivalente à dimensão  [de canal de ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) marketing.
   * **`channel._id`**: Equivalente aos detalhes do canal  [de marketing](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Dê a cada dimensão o modelo de atribuição e a persistência desejados. Se desejar as dimensões de primeiro e último toque, arraste cada dimensão de canal de marketing para a área de componentes várias vezes. Dê a cada dimensão o modelo de atribuição e a persistência desejados. O Adobe também recomenda dar um nome de exibição a cada dimensão para facilitar o uso no Workspace.
4. Crie a visualização de dados.

Suas dimensões de canal de marketing agora estão disponíveis para uso no Analysis Workspace.

## Diferenças de processamento e arquitetura

>[!IMPORTANT]
>
>Há várias diferenças de dados fundamentais entre os dados do conjunto de relatórios e os dados da plataforma. A Adobe recomenda que você ajuste as regras de processamento de canais de marketing do conjunto de relatórios para ajudar a facilitar a coleta de dados adequada na Plataforma.

As configurações do canal de marketing operam de forma diferente entre os dados da plataforma e os dados do conjunto de relatórios. Considere as seguintes diferenças ao configurar canais de marketing para CJA:

* **É a primeira página da visita**: Esses critérios de regra são comuns em várias definições de canal de marketing padrão. Qualquer regra de processamento que contenha esse critério é ignorada na Plataforma (outros critérios na mesma regra ainda se aplicam). As sessões são determinadas no momento do query de dados, em vez de no momento da coleta de dados, impedindo a Plataforma de usar esse critério de regra específico. O Adobe recomenda remover os critérios &quot;É a primeira página da visita&quot; de cada regra de processamento de canais de marketing.

   ![Primeira página da visita](assets/first-page-of-visit.png)

* **Substituir Canal** de último toque: Essa configuração no Gerenciador de Canais de marketing normalmente impede que determinados canais obtenham crédito de canal de último toque. A plataforma ignora essa configuração, permitindo que canais amplos como &quot;Direto&quot; ou &quot;Interno&quot; atribuam métricas de maneiras potencialmente indesejadas. O Adobe recomenda remover canais nos quais a opção &quot;Substituir Canal de último toque&quot; está desmarcada.
   * Você pode excluir o canal de marketing &#39;Direto&#39; no Gerenciador de Canais de marketing e, em seguida, confiar no item de dimensão &#39;Nenhum valor&#39; do CJA para esse canal. Também é possível renomear esse item de dimensão como &#39;Direto&#39; ou excluir o item de dimensão totalmente ao configurar uma visualização de dados.
   * Como alternativa, você pode criar uma classificação de canal de marketing, classificando cada valor para si mesmo, exceto para canais que você deseja excluir no CJA. Você pode usar essa dimensão de classificação ao criar uma visualização de dados em vez de `channel.typeAtSource`.

   ![Substituir o canal de último toque](assets/override-last-touch-channel.png)

* **Expiração** do Canal de marketing: Essa configuração de período de envolvimento determina o período de inatividade antes que um visitante possa obter um novo canal de primeiro toque nos dados do conjunto de relatórios. A plataforma usa suas próprias configurações de atribuição, de modo que essa configuração é ignorada totalmente no CJA.

   ![Expiração de canal de marketing](assets/marketing-channel-expiration.png)

## Comparação de dados entre o CJA e o Analytics tradicional

Como a arquitetura do Adobe Experience Platform é diferente de um conjunto de relatórios tradicional do Analytics, os resultados não têm garantia de correspondência. No entanto, você pode usar as seguintes dicas para facilitar essa comparação:

* Verifique se as diferenças de arquitetura listadas acima não afetam sua comparação. Isso inclui a remoção de canais que não substituem o canal de último toque e a remoção de critérios de regras que são a primeira ocorrência de uma visita (sessão).
* Duplo verifique se sua conexão usa o mesmo conjunto de relatórios que o Analytics tradicional. Se sua conexão CJA contiver vários conjuntos de relatórios com suas próprias regras de processamento do canal de marketing, não há uma maneira fácil de compará-los com o Analytics tradicional. Você gostaria de criar uma conexão separada para cada conjunto de relatórios para comparar os dados.
* Certifique-se de comparar os mesmos intervalos de datas e de que a configuração de fuso horário na visualização de dados seja a mesma que o fuso horário do conjunto de relatórios.
* Use um modelo de atribuição personalizado ao exibir dados do conjunto de relatórios. Por exemplo, use a dimensão [canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) com métricas que usam um modelo de atribuição não padrão. O Adobe recomenda não comparar as dimensões padrão [canal de primeiro toque](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) ou [canal de último toque](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html), pois eles dependem da atribuição coletada no conjunto de relatórios. O CJA não depende dos dados de atribuição de um conjunto de relatórios; em vez disso, é calculado quando um relatório CJA é executado.
* Algumas métricas não têm uma comparação razoável devido a diferenças arquitetônicas entre os dados do conjunto de relatórios e os dados da plataforma. Os exemplos incluem visitas/sessões, visitantes/pessoas e ocorrências/eventos.
