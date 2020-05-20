---
title: Introdução à Análise de jornada do cliente
description: Introdução à Análise de jornada do cliente.
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 1%

---


# Introdução à Análise de jornada do cliente

Para implementar a Análise de jornada do cliente, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras na Análise de jornada do cliente.

## Pré-requisitos

A Análise de jornada do cliente está disponível para clientes que

* São clientes do Adobe Analytics [Select, Prime ou Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) e
* São provisionados para a [Adobe Experience Platform](https://www.adobe.com/br/experience-platform.html)e
* Adquiriu a SKU do Customer Journey Analytics

## Fluxo de trabalho

| Tarefa | Detalhes |
|---|---|---|
| **Etapa 1: Obtenha seus dados na Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<br>**Etapa 1a: Prepare seu schema **de dados: Use o[Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html)para padronizar os dados de experiência do cliente e[definir schemas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)para o gerenciamento da experiência do cliente.<br>**Etapa 1b: Crie um conjunto de dados com base no schema**: Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados CRM, conjuntos de dados POS, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um schema e em lotes de dados. Você pode criar um conjunto de dados [na Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>**Etapa 1c: Ingressar dados na plataforma **Experience: Use o Adobe Analytics Platform Connector pronto para usar o Adobe Analytics Platform para trazer os dados tradicionais do Adobe Analytics para a Plataforma. Você pode criar uma conexão de origem por conjunto de relatórios. Consulte[Criar uma conexão de origem com o Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)na documentação da plataforma Adobe Experience. Depois que a conexão é criada, um schema de público alvo e um conjunto de dados são criados automaticamente para conter os dados recebidos. Além disso, ocorre o preenchimento retroativo de dados e ingere até 13 meses de dados históricos. Quando a ingestão inicial for concluída, você poderá continuar`Step 2`a criar uma conexão entre esse conjunto de dados do Analytics e o Análise de jornada do cliente.<br>Ou você pode assimilar outros tipos de dados por meio da ingestão[em](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)lote, ingestão[em](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)sequência ou por meio de conectores[de](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)outra fonte. |
| **Etapa 2: Criar conexões entre conjuntos de dados da plataforma e Análise de jornada do cliente** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Workspace. Para criar relatórios sobre conjuntos de dados da plataforma Experience, primeiro é necessário estabelecer uma conexão entre conjuntos de dados na plataforma Experience e na Workspace.<br>Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 3: Criar visualizações de dados** | Uma visualização de dados é uma visualização &quot;filtrada&quot; dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização](/help/data-views/create-dataview.md)de dados. |
| **Etapa 4: Relatório dos dados entre canais no Workspace** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o poder e a flexibilidade da Análise Workspace.<br>Consulte [Realizar análise](/help/projects/perform-basic-analysis.md) básica e [Realizar análise](/help/projects/perform-adv-analysis.md)avançada. |
