---
title: Introdução ao Customer Journey Analytics
description: Entenda os pré-requisitos e o fluxo de trabalho necessários para implementar o Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 04ceeb9e9a048a224ea957ad42bc54cbd4b3f249
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 89%

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
| --- | --- |
| **Etapa 1: Obtenha seus dados na Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<ul><li>**Etapa 1a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) para padronizar os dados de experiência do cliente e [definir schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en) para o gerenciamento da experiência do cliente.</li><li>**Etapa 1b: Crie um conjunto de dados com base no esquema**: Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados de CRM, conjuntos de dados de PDV, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode [criar um conjunto de dados no Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html%3Flang%3Dnl).</li><li>**Etapa 1c: Insira dados na Experience Platform**: Use o Adobe Analytics Platform Connector predefinido para trazer os dados tradicionais da Adobe Analytics para a Platform. Você pode criar uma conexão de origem por conjunto de relatórios. Consulte [Criar uma conexão de origem com o Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) na documentação da Adobe Experience Platform. Depois que a conexão é criada, um esquema de público-alvo e um conjunto de dados são criados automaticamente para conter os dados recebidos. Além disso, ocorre o preenchimento retroativo de dados e a assimilação de até 13 meses de dados históricos. Quando a assimilação inicial for concluída, você poderá continuar com o `Step 2` para criar uma conexão entre esse conjunto de dados do Analytics e do Customer Journey Analytics. Ou você pode assimilar outros tipos de dados por meio da [Assimilação em lote](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en), [Assimilação de streaming](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en) ou por [outros Conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en).</li></ul> |
| **Etapa 2: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre conjuntos de dados da Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Espaço de trabalho.<br>Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 3: Criar visualizações de dados** | Uma visualização de dados é uma visualização “filtrada” dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 4: Relatório dos dados entre canais no Espaço de trabalho** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |
