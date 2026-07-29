---
title: Comparação de produtos do Customer Journey Analytics
description: Compare os atributos do cliente dos relatórios do Jornada Analytics e das ferramentas de exportação, como Analysis Workspace, Report Builder, Exportação completa de tabela, Feeds de dados, APIs e MCP.
keywords: sequência de cliques;feed de dados;datafeed;comparação de produto;Analysis Workspace;Report Builder;Exportação de tabela completa
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Comparação de produtos do Analytics

Use esta página para comparar os relatórios do Customer Journey Analytics e as ferramentas de exportação em atributos-chave para ajudá-lo a escolher a ferramenta certa para suas necessidades de análise ou exportação de dados.

| Nome do produto e link de ajuda | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md) | [Feeds de dados](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP | Extensão BI | Colaborador |
|---|---|---|---|---|---|---|---|---|
| **Método de acesso** | Navegador | Microsoft Excel | Navegador | Configurar por meio do navegador | Ferramentas RESTful API | Ferramentas compatíveis com MCP | Ferramentas de BI | Ferramentas compatíveis com MCP |
| **Granularidade de dados** | Agregado | Agregado | Agregado | Evento | Agregado | Agregado | Agregado | Agregado |
| **Experience Cloud ID (ECID) disponível** | Não | Não | Não | Sim | Não | Não | Não | Não |
| **Carimbo de data e hora disponível** | Não | Não | Não | Sim | Não | Não | Não | Não |
| **Nível de processamento** | Totalmente processado | Totalmente processado, com relatório em tempo real separado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Onde a filtragem de bot é aplicada** | No [Datastream](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/bot-detection) e/ou no [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | No [Datastream](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/bot-detection) e/ou no [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | No [Datastream](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/bot-detection) e/ou no [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | No [Datastream](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/bot-detection) e/ou no [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) |  |  | No [Datastream](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/bot-detection) e/ou no [CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection) | |
| **Limite de linha visível (antes da paginação)** | 400 | 50,000 | Limite de 3 milhões, 30 milhões, 150 milhões ou 300 milhões, dependendo do nível | Dependente da camada | 50,000 | 50,000 | 50,000 | 50,000 |
| **Várias visualizações de dados** | Sim, um projeto pode conter dados de várias visualizações de dados | Sim, um projeto pode conter dados de várias visualizações de dados | Não, uma exportação pode conter dados de apenas uma visualização de dados | Não, uma exportação pode conter dados de apenas uma visualização de dados | Não, cada consulta pode referenciar apenas uma visualização de dados | Não, cada consulta pode referenciar apenas uma visualização de dados | Não, cada consulta pode referenciar apenas uma visualização de dados | Sim, se solicitado pelo usuário |
| **Número de colunas da dimensão** | Até 5 | ? | Até 10 | Ilimitado | Até 5 | ? | ? | ? |
| **Número de colunas de métrica** | ? | ? | Até 10 | Ilimitado | ? | ? | ? | ? |
| **Segmentação** <br> [Saiba mais](/help/components/segments/seg-overview.md) | Sim | Sim | Sim | Sim, com [limitações](/help/components/exports/cja-data-feeds/df-segmentation.md) | Sim | Sim | Sim | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/calc-metrics/calc-metr-overview.md) | Sim | Sim | Sim, com [limitações](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | Não | Sim | Sim | Sim | Sim |
| **Campos derivados** <br> [Saiba mais](/help/data-views/derived-fields/derived-fields.md) | Sim | Sim | Sim | Sim | Sim | Sim | Sim | Sim |
| **Atribuição** <br> [Saiba mais](/help/analysis-workspace/attribution/overview.md) | Sim | Limitado | Sim, com [limitações](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | Não | Sim | Sim | Sim | Sim |
| **Delivery programado** | Sim | Sim | Sim | Sim | — | — | — | — |
| **Destinos do delivery** | Email | Email | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — | — | — |

{style="table-layout:auto"}
