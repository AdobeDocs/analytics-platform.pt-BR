---
title: Introdução ao Customer Journey Analytics
description: Entenda os pré-requisitos e o fluxo de trabalho necessários para implementar o Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 100%

---

# Introdução ao Customer Journey Analytics

Para implementar o Customer Journey Analytics, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

## Pré-requisitos

O Customer Journey Analytics está disponível para clientes que

* são clientes do Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/br/analytics/compare-adobe-analytics-packages.html) e
* são provisionados para a [Adobe Experience Platform](https://www.adobe.com/br/experience-platform.html) e
* adquiriram a SKU do Customer Journey Analytics.

## Fluxo de trabalho

| Tarefa | Detalhes |
|---|---|
| **Etapa 1: Obtenha seus dados na Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<ul><li>**Etapa 1a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.translate.html) para padronizar os dados de experiência do cliente e [definir schemas](https://docs.adobe.com/content/help/pt-BR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md) para o gerenciamento da experiência do cliente.</li><li>**Etapa 1b: Crie um conjunto de dados com base no esquema**: Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados de CRM, conjuntos de dados de PDV, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode criar um conjunto de dados [na Experience Platform](https://docs.adobe.com/content/help/pt-BR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).</li><li>**Etapa 1c: Insira dados na Experience Platform**: Use o Adobe Analytics Platform Connector predefinido para trazer os dados tradicionais da Adobe Analytics para a Platform. Você pode criar uma conexão de origem por conjunto de relatórios. Consulte [Criar uma conexão de origem com o Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/tutorials/home.translate.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) na documentação da Adobe Experience Platform. Depois que a conexão é criada, um esquema de público-alvo e um conjunto de dados são criados automaticamente para conter os dados recebidos. Além disso, ocorre o preenchimento retroativo de dados e a assimilação de até 13 meses de dados históricos. Quando a assimilação inicial for concluída, você poderá continuar com o `Step 2` para criar uma conexão entre esse conjunto de dados do Analytics e do Customer Journey Analytics. Ou você pode assimilar outros tipos de dados por meio da [Assimilação em lote](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md), [Assimilação de streaming](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) ou por [outros Conectores de origem](https://docs.adobe.com/content/help/pt-BR/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md).</li></ul> |
| **Etapa 2: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Workspace. Para criar relatórios sobre conjuntos de dados da Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Workspace.<br>Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 3: Criar visualizações de dados** | Uma visualização de dados é uma visualização “filtrada” dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 4: Relatório dos dados entre canais no Workspace** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |
