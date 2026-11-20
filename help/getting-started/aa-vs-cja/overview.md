---
title: Comparação com o Adobe Analytics
description: Visão geral da comparação do Customer Journey Analytics com o Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Comparação com o Adobe Analytics

Esta seção da documentação explica como comparar e entender as diferenças entre o Adobe Customer Journey Analytics e o Adobe Analytics.

A diferença fundamental entre as duas soluções é a amplitude dos dados que você pode considerar ao criar seus relatórios e análises.

No Customer Journey Analytics, *qualquer* fonte de dados pode fazer parte dos dados usados em relatórios e análises. O Adobe Analytics destina-se principalmente a dados online coletados de sites e aplicativos móveis. O Adobe Analytics oferece recursos para importar dados de outras fontes, mas o objetivo principal dessa funcionalidade é fornecer mais contexto sobre os dados online mencionados anteriormente.

## Coleção de dados

O Customer Journey Analytics depende dos dados armazenados nos conjuntos de dados da Adobe Experience Platform. Há várias opções para coletar e assimilar dados desses conjuntos de dados da Experience Platform. Essas opções estão detalhadas na [Visão geral da assimilação de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/data-ingestion).

O Adobe Analytics coleta dados dentro da própria solução. Novamente, você tem várias opções para coletar esses dados, que são detalhadas no [Guia de Implementação do Adobe Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/home).

Você pode usar os dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics por meio do [conector de origem do Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Esse conector assimila os dados coletados do Adobe Analytics para a Experience Platform. Em seguida, é possível criar uma conexão com esse conjunto de dados no Customer Journey Analytics. Consulte [Usar dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja) para obter mais informações.

Os dados do conjunto de relatórios do Adobe Analytics são independentes dos dados armazenados nos conjuntos de dados do Adobe Experience Platform que constituem a conexão do Customer Journey Analytics. Dessa forma, a Adobe recomenda que você avalie os dados em cada plataforma separadamente, em vez de esperar que ambas as plataformas reflitam os mesmos valores.

## Processamento de dados

Antes de criar relatórios sobre os dados, geralmente é necessário processar esses dados para garantir que possam ser usados corretamente para essa finalidade. Esse processamento de dados pode ocorrer no momento da coleta e no momento do relatório.

Em geral, o Customer Journey Analytics foi projetado para trabalhar com os dados coletados e armazenados nos conjuntos de dados do Experience Platform no momento do relatório. O Customer Journey Analytics oferece uma eficiente funcionalidade de processamento de tempo de relatório para garantir que os dados estejam prontos para relatórios e análises. [Campos derivados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/derived-fields) e [configurações de componentes](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) podem ser modificados e aplicados retroativamente a dados históricos. Se você precisar mapear, transformar e validar dados antes que sejam assimilados no Experience Platform, poderá usar a funcionalidade [Preparo de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home) do Experience Platform.

No Adobe Analytics, a maior parte do processamento de dados ocorre imediatamente após a coleta de dados. As regras do canal de marketing, as regras de processamento, a persistência do eVar e outras lógicas de pós-processamento são aplicadas no momento e são permanentes no conjunto de relatórios. As alterações feitas em qualquer uma dessas configurações afetam apenas os novos dados recebidos a partir desse ponto.

Consulte [Comparar o processamento de dados entre o Adobe Analytics e o Customer Journey Analytics](data-processing-comparisons.md) e [Regras de processamento, VISTA e classificações em comparação ao Preparo de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep) para obter mais informações.


## Terminologia

O Customer Journey Analytics oferece flexibilidade na definição de dimensões e métricas, possibilitada pelos esquemas subjacentes baseados no Experience Data Model (XDM). Por exemplo, quando o Adobe Analytics usa visitantes, visitas e ocorrências, o Customer Journey Analytics usa pessoas, sessões e eventos (você pode alterar a nomenclatura conforme desejar).

Consulte [Comparar terminologia de dados do Analytics transmitidos pelo conector de origem do Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology) para obter mais informações sobre as diferenças de terminologia.


## Ambientes de relatórios virtuais e sandboxes

O Adobe Analytics utiliza o conceito de conjuntos de relatórios virtuais, que permite segmentar os dados coletados e controlar o acesso a eles.

O Customer Journey Analytics utiliza um conceito semelhante, chamado de Visualizações de dados. As visualizações de dados são containers que permitem determinar como interpretar os dados de uma conexão. Elas oferecem flexibilidade máxima para especificar e configurar dimensões e métricas em preparação para relatórios e análises.

O Experience Platform oferece sandboxes que funcionam como um container que armazena dados e aplicativos de um determinado ambiente. A funcionalidade de uma sandbox não está relacionada a um conjunto de relatórios virtual do Adobe Analytics ou a uma visualização de dados do Customer Journey Analytics. O Adobe Analytics em si não tem dependência ou relação com as sandboxes do Experience Platform. O Customer Journey Analytics é compatível com as sandboxes da Experience Platform, no entanto, há algumas considerações importantes.

Consulte [Conjuntos de relatórios virtuais, visualizações de dados, sandboxes da Adobe Experience Platform e o conector de origem do Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc) para obter mais informações.


## Identidades

O Customer Journey Analytics é compatível com as identidades definidas nos esquemas com os quais seus conjuntos de dados estão em conformidade. Sendo assim, as identidades são um conceito fundamental da Experience Platform que o Customer Journey Analytics usa ao configurar uma [conexão](../../connections/overview.md) (definindo a ID de pessoa para cada conjunto de dados) e ao aplicar a [compilação](../../stitching/overview.md) para a análise entre canais. Uma identidade importante usada pelos SDKs e pela API do Experience Platform é a ECID.

O Adobe Analytics usa um conjunto mais definitivo de campos de identidade, como a Adobe Analytics ID (AAID). Ao usar o conector de origem do Analytics, esses campos de identidade do Adobe Analytics recebem tratamento especial. Consulte [AAID, ECID, AACUSTOMID e o conector de origem do Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc) para obter mais informações.


## Dimensões de alta cardinalidade

O Customer Journey Analytics armazena valores de dimensão inteiros e não há limite para quantos valores únicos uma dimensão pode expandir. Por outro lado, o Adobe Analytics usa hashes de 32 bits para mapear valores de dimensão a fim de otimizar os relatórios e o armazenamento. Este comportamento pode levar a [colisões de hash](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions) nos relatórios. A Adobe Analytics também agrupa valores no item de linha [Tráfego baixo](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic) quando o limite exclusivo é atingido. Os segmentos que usam essas dimensões podem mostrar discrepâncias entre os relatórios do Adobe Analytics e do Customer Journey Analytics.

## Recursos compatíveis

Você pode encontrar uma visão geral dos recursos do Adobe Analytics e como o Customer Journey Analytics oferece suporte a eles em [suporte aos recursos do Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa).
