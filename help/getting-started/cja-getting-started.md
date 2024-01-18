---
title: Introdução ao Customer Journey Analytics
description: Entenda os pré-requisitos e o fluxo de trabalho necessários para implementar o Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: ht
source-wordcount: '459'
ht-degree: 100%

---

# Introdução ao Customer Journey Analytics

Para implementar o Customer Journey Analytics, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

## Pré-requisitos

O Customer Journey Analytics está disponível para clientes que

* são provisionados para a [Adobe Experience Platform](https://www.adobe.com/br/experience-platform.html) e
* adquiriram a SKU do Customer Journey Analytics.

## Fluxo de trabalho

| Tarefa | Detalhes |
| --- | --- |
| **Etapa 1: se estiver migrando do Adobe Analytics para o Customer Journey Analytics, migre seus dados e replique seus projetos.** | Para obter informações sobre como migrar dados do Adobe Analytics para o Customer Journey Analytics, consulte: <ul><li>[Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)</li><li>[Assimilação e utilização de dados do Adobe Analytics tradicional](../data-ingestion/analytics.md)</li></ul><p>Para obter informações sobre como replicar seus projetos do Adobe Analytics no Customer Journey Analytics, bem como mapear componentes de projeto de um conjunto de relatórios do Adobe Analytics para uma visualização de dados do Customer Journey Analytics, consulte:</p><ul><li>[Migração de componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html?lang=pt-BR)</li></ul> |
| **Etapa 2: Transfira outros dados para a Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<ul><li>**Etapa 2a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) para padronizar os dados de experiência do cliente e [definir schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) para o gerenciamento da experiência do cliente.</li><li>**Etapa 2b: crie um conjunto de dados com base no esquema**: os dados da Platform consistem em conjuntos de dados, como conjuntos de dados de email, de CRM, de POS, do Adobe Analytics etc. Cada conjunto de dados consiste de um esquema e lotes de dados. Você pode [criar um conjunto de dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=pt-BR).</li><li>**Etapa 2c: assimilar dados na Experience Platform**: Aqui, você tem várias opções.</li></ul> |
| **Etapa 3: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre conjuntos de dados da Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Espaço de trabalho.<br>Consulte [Criar ou editar uma conexão](/help/connections/create-connection.md). |
| **Etapa 4: Criar visualizações de dados** | Uma visualização de dados é uma visualização “filtrada” dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 5: Relatório dos dados entre canais no Espaço de trabalho** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |

## Guias de início rápido

A seção [Assimilação de dados](../data-ingestion/data-ingestion.md) fornece guias de início rápido sobre o fluxo de trabalho acima. Esses guias de início rápido ilustram como assimilar dados de uma variedade de fontes (incluindo o Adobe Analytics) na Adobe Experience Platform e, em seguida, usar esses dados no Customer Journey Analytics.
