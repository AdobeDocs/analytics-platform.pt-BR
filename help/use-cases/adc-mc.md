---
title: Importar Canais de marketing para o CJA usando o Conector de dados do Analytics
description: Use as configurações corretas do Conector de dados do Analytics para trazer as regras de processamento do Canal de marketing para o Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Importar Canais de marketing para o CJA usando o Conector de dados do Analytics

Se sua organização usar o [Conector de dados do Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/sources/connectors/adobe-applications/analytics.html) para trazer dados do conjunto de relatórios para o CJA, você poderá configurar uma conexão no CJA para relatar as dimensões do Canal de marketing.

## Pré-requisitos

* Os dados do conjunto de relatórios já devem ser importados para o Adobe Experience Platform usando o [Conector de dados do Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* As regras de processamento de canais de marketing já devem estar configuradas. Consulte [Regras de processamento para Canais de marketing](https://docs.adobe.com/content/help/pt-BR/analytics/components/marketing-channels/c-rules.html) no guia tradicional Componentes do Analytics.

## Elementos do schema do Canal de marketing

Depois de usar o Conector de dados do Analytics em um conjunto de relatórios desejado, um schema XDM é criado para você. Esse schema contém todas as dimensões e métricas do Analytics como dados brutos. Esses dados brutos não contêm atribuição ou persistência. Em vez disso, cada ocorrência é executada pelas regras de processamento de canais de marketing e registra a primeira regra correspondente. Você especifica a atribuição e a persistência ao criar uma visualização de dados no CJA.

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


Como as dimensões do canal de primeiro e último toque são basicamente a mesma dimensão com modelos de atribuição diferentes, é possível recriar dimensões semelhantes ao [criar uma visualização de dados](/help/data-views/create-dataview.md). É possível criar várias dimensões com base no mesmo elemento de schema, dando a elas diferentes modelos de atribuição e persistência.

## Diferenças entre

