---
title: Introdução ao Customer Journey Analytics
description: Entenda os pré-requisitos e o fluxo de trabalho necessários para implementar o Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '383'
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
| --- | --- |
| **Etapa 1: Se estiver migrando do Adobe Analytics para o CJA, saiba o que precisa fazer.** | Consulte [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). |
| **Etapa 2: Transfira outros dados para a Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<ul><li>**Etapa 2a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) para padronizar os dados de experiência do cliente e [definir schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) para o gerenciamento da experiência do cliente.</li><li>**Etapa 2b: Crie um conjunto de dados com base no esquema**: Os dados na plataforma consistem em conjuntos de dados, como conjuntos de dados de email, conjuntos de dados de CRM, conjuntos de dados de PDV, conjunto de dados do Adobe Analytics etc. Cada conjunto de dados consiste em um esquema e em lotes de dados. Você pode [criar um conjunto de dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=pt-BR).</li><li>**Etapa 2c: Assimilar dados na Experience Platform**: Aqui, você tem várias opções. Veja os [casos de uso de assimilação de dados](/help/data-ingestion/data-ingestion.md) para obter mais informações. |
| **Etapa 3: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre conjuntos de dados da Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Espaço de trabalho.<br>Consulte [Criar uma conexão](/help/connections/create-connection.md). |
| **Etapa 4: Criar visualizações de dados** | Uma visualização de dados é uma visualização “filtrada” dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 5: Relatório dos dados entre canais no Espaço de trabalho** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |
