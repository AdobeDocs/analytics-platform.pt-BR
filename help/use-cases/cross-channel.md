---
title: Análise de jornada entre canais
description: Analise e extraia insights das interações em toda a jornada do cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
source-git-commit: 68ca5b1ee9d695f53b22c821cec481cc116dcdb3
workflow-type: ht
source-wordcount: '433'
ht-degree: 100%

---

# Análise de jornada entre canais

Tenha uma visão única e consolidada do comportamento do cliente através de vários canais, unificando dados de várias propriedades web, móveis e offline. Por exemplo, é possível usar a visualização consolidada para analisar as interações dos clientes no desktop e nos dispositivos móveis e entender seus comportamentos, extraindo insights para otimizar suas experiências digitais. Também é possível analisar as interações do cliente entre canais, incluindo canais digitais e offline, como interações de suporte e compras na loja, a fim de melhor entender e otimizar a jornada do cliente.

## Arquitetura

![Arquitetura entre canais](assets/cross-channel-architecture.svg)

## Etapas da implementação

1. [Crie esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) para os dados que serão assimilados.
1. [Crie conjuntos de dados](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=pt-BR) para os dados que serão assimilados.
1. [Assimilar dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=pt-BR).
1. Use uma ID de namespace comum entre os conjuntos de dados, ou use a [Análise entre canais](/help/connections/cca/overview.md) para vincular pessoas. Observe que o Customer Journey Analytics não usa atualmente os serviços de Perfil ou de Identidade da Experience Platform para compilações.
1. Execute qualquer preparação de dados personalizada para garantir uma chave comum entre os conjuntos de dados de série de tempo que serão assimilados no Customer Journey Analytics.
1. Forneça aos dados de pesquisa uma ID primária que possa se associar a um campo nos dados do evento. Conta como linhas no licenciamento.
1. Configure a mesma ID primária para os dados do perfil que foi configurada para os dados do evento.
1. Configure uma conexão de dados para assimilar dados da Experience Platform para o Customer Journey Analytics.
1. [Crie uma visualização de dados](/help/data-views/create-dataview.md) na conexão para selecionar as dimensões e métricas específicas a serem incluídas na visualização. As configurações de atribuição e alocação também são definidas na visualização de dados. Essas configurações são computadas no momento da emissão do relatório.
1. Crie um projeto para configurar painéis e relatórios dentro do Analysis Workspace.

## Considerações

Ao estabelecer esse fluxo de trabalho, não se esqueça de considerar os seguintes pontos.

* A análise de dados entre canais requer o mesmo namespace de ID em todos os registros.
* O processo de união de conjuntos de dados desiguais requer uma chave primária comum de pessoa/entidade, entre todos os conjuntos de dados.
* Atualmente, não há suporte para uniões com base em chave secundária.
* O processo de compilação de identidades com base em campo permite rechavear identidades em linhas, com base em registros de ID transitórios subsequentes, como uma ID de autenticação. Isso permite consolidar registros desiguais em uma única ID para análise no nível da pessoa, em vez do dispositivo ou do cookie.
* Objetos e atributos do mesmo campo XDM são mesclados em uma dimensão no Customer Journey Analytics. Para mesclar vários atributos de vários conjuntos de dados na mesma dimensão do Customer Journey Analytics, os conjuntos de dados devem fazer referência ao mesmo campo ou esquema XDM.
