---
title: Guia de início rápido do Customer Journey Analytics B2B
description: Guia de início rápido da B2B Edition do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 100%

---


# Guia de início rápido da B2B Edition

Para implementar o Customer Journey Analytics B2B Edition, primeiro entenda os conceitos e recursos específicos do B2B. Além disso, você deve entender bem o fluxo de trabalho tradicional para implementar o Customer Journey Analytics.

Este documento se concentra no fluxo de trabalho específico para a implementação do Customer Journey Analytics.

## Pré-requisitos

Os seguintes pré-requisitos se aplicam na implementação do Customer Journey Analytics B2B Edition:

* Você deve ter o [controle de acesso e permissões](/help/technotes/access-control.md) necessários para realizar tarefas de administração no Customer Journey Analytics.
* Você deve ter adquirido o pacote complementar do Customer Journey Analytics B2B Edition.


## Fluxo de trabalho

| Tarefa | Detalhes |
| --- | --- |
| **Etapa 1: enviar dados B2B para a Experience Platform** | Esta etapa, realizada na Experience Platform, envolve várias subetapas:<ul><li>**Etapa 1a: preparar o esquema de dados**: use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) para padronizar dados B2B e [definir esquemas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/rtcdp/schemas/b2b) para seus dados B2B.</li><li>**Etapa 1b: criar um conjunto de dados com base no esquema**: os dados na Platform consistem em conjuntos de dados, como dados de conta, dados de oportunidade, dados de grupos de compra, dados de campanha, dados de lista de marketing, conjuntos de dados de email, conjuntos de dados de CRM, conjuntos de dados de POS e muito mais. Cada conjunto de dados consiste de um esquema e lotes de dados. Você pode [criar um conjunto de dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=pt-BR).</li><li>**Etapa 1c: assimilar dados na Experience Platform**: você tem [várias opções](https://experienceleague.adobe.com/pt-br/docs/experience-platform/ingestion/home).</li></ul> |
| **Etapa 2: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para gerar relatórios sobre conjuntos de dados da Experience Platform, primeiro você precisa estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Workspace. Você tem outras opções ao configurar uma conexão com o B2B Edition. <br>Consulte [Criar ou editar uma conexão](/help/connections/create-connection.md). |
| **Etapa 3: criar visualizações de dados** | Uma visualização de dados é uma visualização *filtrada* dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo-limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados. Você tem mais opções ao configurar uma visualização de dados com o B2B Edition.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 4: Relatório dos dados entre canais no Espaço de trabalho** | Depois de criar conexões e visualizações de dados, analise os dados B2B que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->