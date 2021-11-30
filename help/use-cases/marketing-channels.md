---
title: Usar dimensões do canal de marketing na Adobe Experience Platform
description: Use o Conector de dados do Analytics para trazer regras de processamento de Canal de marketing para a Adobe Experience Platform.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---

# Usar dimensões do canal de marketing na Adobe Experience Platform

Se sua organização usar o [Conector de dados do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR) para trazer dados do conjunto de relatórios para o CJA, você poderá configurar uma conexão no CJA para relatar as dimensões do Canal de marketing.

## Pré-requisitos

* Os dados do conjunto de relatórios já devem ser importados para a Adobe Experience Platform usando o [Conector de dados do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). Outras fontes de dados não são suportadas, pois os canais de marketing dependem das regras de processamento em um conjunto de relatórios do Analytics.
* As regras de processamento do canal de marketing já devem estar configuradas. Consulte [Regras de processamento para Canais de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=pt-BR) no guia tradicional Componentes do Analytics.

## Elementos do esquema do Canal de marketing

Depois que você estabelecer o Conector de dados do Analytics em um conjunto de relatórios desejado, um esquema XDM será criado para você. Esse esquema contém todas as dimensões e métricas do Analytics como dados brutos. Esses dados brutos não contêm atribuição ou persistência. Em vez disso, cada evento é executado pelas regras de processamento do canal de marketing e registra a primeira regra correspondente. Você especifica a atribuição e a persistência ao criar uma visualização de dados no CJA.

1. [Crie uma conexão](/help/connections/create-connection.md) que inclua um conjunto de dados com base no Conector de dados do Analytics.
2. [Crie uma visualização de dados](/help/data-views/create-dataview.md) que inclua as seguintes dimensões:
   * **`channel.typeAtSource`**: Equivalente à dimensão [Canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=pt-BR).
   * **`channel._id`**: Equivalente aos [detalhes do Canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=pt-BR)
3. Dê a cada dimensão o modelo de atribuição e a persistência desejados. Se desejar as dimensões de primeiro e último contato, arraste cada dimensão do canal de marketing para a área de componentes várias vezes. Dê a cada dimensão o modelo de atribuição e a persistência desejados. A Adobe também recomenda dar um nome de exibição a cada dimensão para facilitar o uso no Workspace.
4. Crie a visualização de dados.

Suas dimensões do canal de marketing agora estão disponíveis para uso no Analysis Workspace.

## Diferenças de processamento e arquitetura

>[!IMPORTANT]
>
>Há várias diferenças de dados fundamentais entre os dados do conjunto de relatórios e os dados da Plataforma. A Adobe recomenda que você ajuste as regras de processamento do canal de marketing do conjunto de relatórios para ajudar a facilitar a coleção de dados adequada na Plataforma.

As configurações do canal de marketing operam de forma diferente entre os dados da Plataforma e os dados do conjunto de relatórios. Considere as seguintes diferenças ao configurar canais de marketing para o CJA:

* **É a primeira página da visita**: esses critérios de regra são comuns em várias definições de canal de marketing padrão. Qualquer regra de processamento que contenha esse critério é ignorada na Plataforma (outros critérios na mesma regra ainda se aplicam). As sessões são determinadas no momento da consulta de dados, em vez de no momento da coleção de dados, impedindo a Plataforma de usar esse critério de regra específico. A Adobe recomenda remover os critérios “É a primeira página da visita” de cada regra de processamento do canal de marketing.

   ![Primeira página da visita](assets/first-page-of-visit.png)

* **Substituir canal de último contato**: essa configuração no Gerenciador de canal de marketing normalmente impede que determinados canais obtenham crédito do canal de último contato. A Plataforma ignora essa configuração, permitindo que canais amplos como “Direto” ou “Interno” atribuam métricas de maneiras possivelmente indesejadas. A Adobe recomenda remover canais em que a opção “Substituir Canal de último contato” está desmarcada.
   * Você pode excluir o canal de marketing “Direto” no Gerenciador de canal de marketing e, em seguida, recorrer ao item de dimensão “Nenhum valor” do CJA para esse canal. Também é possível renomear esse item de dimensão como “Direto” ou excluir o item de dimensão totalmente ao configurar uma visualização de dados.
   * Como alternativa, você pode criar uma classificação de canal de marketing, classificando cada valor para si mesmo, exceto os canais que você deseja excluir no CJA. Você pode usar essa dimensão de classificação ao criar uma visualização de dados em vez de `channel.typeAtSource`.

   ![Substituir o canal de último contato](assets/override-last-touch-channel.png)

* **Expiração do canal de marketing**: essa configuração de período de envolvimento determina o período de inatividade antes que um visitante possa obter um novo canal de primeiro contato nos dados do conjunto de relatórios. A plataforma usa suas próprias configurações de atribuição; portanto, essa configuração é ignorada totalmente no CJA.

   ![Expiração de canal de marketing](assets/marketing-channel-expiration.png)

## Comparação de dados entre o CJA e o Analytics tradicional

Como a arquitetura da Adobe Experience Platform é diferente de um conjunto de relatórios tradicional do Analytics, os resultados não têm garantia de correspondência. No entanto, você pode usar as seguintes dicas para facilitar essa comparação:

* Verifique se as diferenças de arquitetura listadas acima não afetam sua comparação. Isso inclui a remoção de canais que não substituem o canal de último contato e a remoção de critérios de regras que são o primeiro hit de uma visita (sessão).
* Verifique se sua conexão usa o mesmo conjunto de relatórios que o Analytics tradicional. Se sua conexão com o CJA contiver vários conjuntos de relatórios com suas próprias regras de processamento do Canal de marketing, não haverá uma maneira fácil de compará-los com o Analytics tradicional. Você gostaria de criar uma conexão separada para cada conjunto de relatórios para comparar os dados.
* Compare os mesmos intervalos de datas e verifique se a configuração de fuso horário na visualização de dados é a mesma do fuso horário do conjunto de relatórios.
* Use um modelo de atribuição personalizado ao exibir dados do conjunto de relatórios. Por exemplo, use a dimensão [Canal de marketing](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) com métricas que usam um modelo de atribuição não padrão. A Adobe recomenda não comparar as dimensões padrão [Canal de primeiro contato](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=pt-BR) ou [Canal de último contato](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=pt-BR), pois dependem da atribuição coletada no conjunto de relatórios. O CJA não depende dos dados de atribuição de um conjunto de relatórios; em vez disso, eles são calculados quando um relatório do CJA é executado.
* Algumas métricas não têm uma comparação razoável devido a diferenças arquitetônicas entre os dados do conjunto de relatórios e os dados da plataforma. Os exemplos incluem visitas/sessões, visitantes/pessoas e ocorrências/eventos.
