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
source-git-commit: d5ecbbc28bc3892a2114de2c73df3287f22cf1a0
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 59%

---


# Comparação de produtos do Analytics

Use esta página para comparar os relatórios do Customer Journey Analytics e as ferramentas de exportação em atributos-chave para ajudá-lo a escolher a ferramenta certa para suas necessidades de análise ou exportação de dados.

| Nome do produto e link de ajuda | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [Exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md) | [Feeds de dados](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [APIs](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **Método de acesso** | Navegador | Microsoft Excel | Navegador | Configurar por meio do navegador | Ferramentas RESTful API | Ferramentas compatíveis com MCP |
| **Granularidade de dados** | Agregado | Agregado | Agregado | Evento | Agregado | Agregado |
| **Experience Cloud ID (ECID) disponível** | Não | Não | Sim | Sim | Não | Não |
| **Carimbo de data e hora disponível** | Não | Não | Não | Sim | Não | Não |
| **Nível de processamento** | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Dados do filtro de bot incluídos** | Não | Não | Não | Não | Não | Não |
| **Baixo tráfego (únicos excedidos) aparece** <br> [Saiba mais](/help/components/dimensions/high-cardinality.md) | Sim | Sim | Não | Não | Sim | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 50,000 | Ilimitado | Ilimitado | 50,000 | 50,000 |
| **Várias visualizações de dados** | Sim | Sim | Não | Não | Sim | Sim |
| **Quantidade de detalhamentos** | Ilimitado | Até 2 | Ilimitado | Ilimitado | Ilimitado, executar em vários queries | Ilimitado |
| **Segmentação** <br> [Saiba mais](/help/components/segments/seg-overview.md) | Sim | Sim | Sim | Sim, com [limitações](/help/components/exports/cja-data-feeds/df-segmentation.md) | Sim | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/calc-metrics/calc-metr-overview.md) | Sim, com o [Attribution](/help/analysis-workspace/attribution/overview.md) | Sim, com Atribuição | Não | Não | Sim, com Atribuição | Sim, com Atribuição |
| **Campos derivados** <br> [Saiba mais](/help/data-views/derived-fields/derived-fields.md) | Sim | Sim | Sim | Sim | Sim | Sim |
| **Análise de coorte** | [Sim](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Não | Não | Não | Não | Não |
| **Atribuição** <br> [Saiba mais](/help/analysis-workspace/attribution/overview.md) | Sim | Limitado | Não | Não | Sim | Sim |
| **Preparação** <br> [Saiba mais](/help/analysis-workspace/curate-share/curate.md) | Sim, com em projetos e visualizações de dados | Não | Não | Sim, na visualização de dados | Sim, na visualização de dados | Sim, na visualização de dados |
| **Compartilhamento de projeto** <br> [Saiba mais](/help/analysis-workspace/curate-share/share-projects.md) | Sim, com funções de projeto | Não | Não | Não | Não | Não |
| **Delivery programado** | Sim | Sim | Sim | Sim | Não | Não |
| **Destinos do delivery** | Email | Email | Amazon S3, Azure RBAC, Azure SAS, GCP | Amazon S3, Azure RBAC, Azure SAS, GCP | — | — |
| **Processamento de tempo do relatório de exibição de dados** <br> [Saiba mais](/help/data-views/data-views.md) | Sim | Sim | Não | Não | Sim | Sim |

{style="table-layout:auto"}
