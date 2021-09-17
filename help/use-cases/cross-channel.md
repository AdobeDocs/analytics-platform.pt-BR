---
title: Análise de Jornada entre canais
description: Analise e extraia insights das interações em toda a jornada do cliente.
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# Análise de Jornada entre canais

Tenha uma única visualização consolidada do comportamento do cliente em vários canais, unificando dados de várias propriedades da Web, móveis e offline. Por exemplo, você pode usar essa visualização consolidada para analisar as interações do cliente no desktop e nos dispositivos móveis para entender o comportamento do cliente e extrair insights para otimizar as experiências do cliente digital. Também é possível analisar as interações do cliente em todos os canais, incluindo canais digitais e offline, como interações de suporte e compras na loja, para entender e otimizar melhor a jornada do cliente.

## Arquitetura

![Arquitetura entre canais](assets/cross-channel-architecture.svg)

## Etapas da implementação

1. [Crie ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) esquemas para os dados que serão assimilados.
1. [Crie ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) conjuntos de dados para que os dados sejam assimilados.
1. [Assimilar dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. Use uma ID de namespace comum em conjuntos de dados ou use o [Cross-Channel Analytics](/help/connections/cca/overview.md) para vincular pessoas. Observe que o Customer Journey Analytics não usa atualmente o Perfil do Experience Platform ou os serviços de identidade para compilar.
1. Execute qualquer preparação de dados personalizada para garantir uma chave comum em conjuntos de dados de séries de tempo que serão assimilados no Customer Journey Analytics.
1. Forneça aos dados de pesquisa uma ID primária que possa se associar a um campo nos dados do evento. Conta como linhas no licenciamento.
1. Defina a mesma ID primária para os dados do perfil que a ID primária dos dados do evento.
1. Configure uma conexão de dados para assimilar dados de Experience Platform para Customer Journey Analytics.
1. [Crie uma ](/help/data-views/create-dataview.md) visualização de dados na conexão para selecionar as dimensões e métricas específicas a serem incluídas na exibição. As configurações de atribuição e alocação também são definidas na visualização de dados. Essas configurações são calculadas no momento do relatório.
1. Crie um projeto para configurar painéis e relatórios no Analysis Workspace.

## Considerações

Ao estabelecer esse workflow, considere os seguintes pontos.

* A análise de dados em canais requer o mesmo namespace de ID em cada registro.
* O processo de união de conjuntos de dados diferentes requer uma chave de pessoa/entidade primária comum em todos os conjuntos de dados.
* Atualmente, não há suporte para uniões com base em chave secundárias.
* O processo de identificação baseado em campo permite a criação de novas identidades em linhas com base em registros de ID transitórios subsequentes, como uma ID de autenticação. Isso permite resolver registros diferentes para uma única ID para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.
* Objetos e atributos do mesmo campo XDM se mesclam em uma dimensão no Customer Journey Analytics. Para mesclar vários atributos de vários conjuntos de dados na mesma dimensão de Customer Journey Analytics, os conjuntos de dados devem fazer referência ao mesmo campo ou esquema XDM.
