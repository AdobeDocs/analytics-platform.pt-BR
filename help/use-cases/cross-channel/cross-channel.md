---
title: Análise de jornada entre canais
description: Analise e extraia insights das interações em toda a jornada do cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
autotag-review: '2026-05-19T09:37:23.903Z'
TQID: 'https://experienceleague.adobe.com/zguhaVwn2XtF0vSGqYAgjiL2IwUq-DMH-WUd0uQRnPc'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: bf2b169f-d8b2-488a-97b9-f3bc9532e35cid: b7fb3355-1f54-4380-bce3-d444b226c0e9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 638
ht-degree: 100%

---

# Análise entre canais {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="Adicionar outros conjuntos de dados à conexão"
>abstract="Depois de adicionar dados a um conjunto de dados na Adobe Experience Platform, é possível adicionar esse conjunto à conexão no Customer Journey Analytics. Ao adicionar dados de outros canais, verifique se eles seguem o esquema que a sua organização usa.<br><br>Cada conjunto de dados adicionado exige muito trabalho, principalmente para garantir que exista um identificador exclusivo para cada evento e que a estrutura de dados abrangente esteja em conformidade com o esquema personalizado da sua organização. Estabelecer esse fluxo de trabalho pode exigir coordenação entre muitas equipes dentro da sua organização e levar vários meses."

<!-- markdownlint-enable MD034 -->

A análise entre canais permite uma visão única e consolidada do comportamento do cliente em vários canais, unificando dados de várias propriedades da web, dispositivos móveis e offline. Por exemplo, é possível usar a visualização consolidada para analisar as interações dos clientes no desktop e nos dispositivos móveis e entender seus comportamentos, extraindo insights para otimizar suas experiências digitais. Também é possível analisar as interações do cliente entre canais, incluindo canais digitais e offline, como interações de suporte e compras na loja, a fim de melhor entender e otimizar a jornada do cliente.

## Etapas da implementação

![Fluxo de etapas de implementação conforme descrito nesta seção.](../assets/cca-architecture.png)

1. [Crie esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) para os dados que serão assimilados.
1. [Crie conjuntos de dados](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=pt-BR) para os dados que serão assimilados.
1. [Assimilar dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=pt-BR).
   1. Dados baseados em eventos ![evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) do site ou aplicativo móvel por meio do conector de origem da Edge Network ou do Analytics.
   2. Dados de perfil ![perfil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (por exemplo, de um sistema CRM, aplicativo de central de atendimento, aplicativo de fidelidade).
   3. Dados de pesquisa ![pesquisa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (por exemplo, nome do produto, categoria de um sistema de informações do produto).

1. Use uma ID de namespace comum em conjuntos de dados. Use a [Compilação](../../stitching/overview.md) para elevar qualquer ![atualização de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) do conjunto de dados baseado em eventos com relação ao fornecimento da ID comum em cada linha. Observe que o Customer Journey Analytics não usa atualmente os serviços de Perfil ou de Identidade da Experience Platform para compilações.
1. Execute qualquer preparação de dados personalizada para garantir uma chave comum entre os conjuntos de dados de série temporal que serão assimilados no Customer Journey Analytics.
1. Forneça aos dados de pesquisa uma ID primária que possa se associar a um campo nos dados do evento. Conta como linhas no licenciamento.
1. Configure a mesma ID primária para os dados do perfil que foi configurada para os dados do evento.
1. [Crie uma conexão](../../connections/overview.md) para assimilar os conjuntos de dados relevantes da Experience Platform para o Customer Journey Analytics.
1. [Crie uma visualização de dados](/help/data-views/create-dataview.md) na conexão para selecionar as dimensões e métricas específicas a serem incluídas na visualização. As configurações de atribuição e alocação também são definidas na visualização de dados. Essas configurações são computadas no momento da emissão do relatório.
1. [Crie um projeto](/help/analysis-workspace/home.md) para configurar painéis e relatórios no Analysis Workspace.

## Considerações

Ao estabelecer esse fluxo de trabalho, não se esqueça de considerar os seguintes pontos.

* A análise de dados entre canais requer o mesmo namespace de ID em todos os registros.
* O processo de união de conjuntos de dados desiguais requer uma chave primária comum de pessoa/entidade, entre todos os conjuntos de dados.
* Atualmente, não há suporte para uniões com base em chave secundária.
* O processo de compilação permite rechavear identidades em linhas, com base nas informações de ID transitória (como uma ID de autenticação) de registros que compartilham a mesma ID persistente. Isso permite resolver registros diferentes em uma única ID compilada para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.
* Objetos e atributos do mesmo campo XDM são mesclados em uma dimensão no Customer Journey Analytics. Para mesclar vários atributos de vários conjuntos de dados na mesma dimensão do Customer Journey Analytics, os conjuntos de dados devem fazer referência ao mesmo campo ou esquema XDM.

