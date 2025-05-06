---
title: Guia de início rápido do Customer Journey Analytics B2B
description: Guia de início rápido para a B2B edition do Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---


# Guia de início rápido do B2B edition

{{draft-b2b}}

Para implementar o Customer Journey Analytics B2B edition, primeiro entenda os conceitos e recursos específicos do B2B. Além disso, você deve estar familiarizado com o fluxo de trabalho tradicional para implementar o Customer Journey Analytics.

Este documento se concentra no workflow específico para a implementação do Customer Journey Analytics.

## Pré-requisitos

Para implementar o Customer Journey Analytics B2B edition, os seguintes pré-requisitos se aplicam:

* Você tem o [controle de acesso e permissões](/help/technotes/access-control.md) necessários para fornecer tarefas de administração no Customer Journey Analytics.
* Você adquiriu o pacote complementar do Customer Journey Analytics B2B edition.


## Fluxo de trabalho

| Tarefa | Detalhes |
| --- | --- |
| **Etapa 1: Obter dados B2B no Experience Platform** | Esta etapa, executada no Experience Platform, envolve várias subetapas:<ul><li>**Etapa 1a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home) para padronizar dados B2B e [definir esquemas](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b) para seus dados B2B.</li><li>**Etapa 1b: Crie um conjunto de dados com base no esquema**: Os dados na plataforma consistem em conjuntos de dados, como dados de conta, dados de oportunidade, dados de grupo de compras, dados de campanha, dados da lista de marketing, conjuntos de dados de email, conjuntos de dados de CRM, conjuntos de dados de PDV e muito mais. Cada conjunto de dados consiste de um esquema e lotes de dados. Você pode [criar um conjunto de dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=pt-BR).</li><li>**Etapa 1c: Assimilar dados na Experience Platform**: Você tem [várias opções](https://experienceleague.adobe.com/pt-br/docs/experience-platform/ingestion/home).</li></ul> |
| **Etapa 2: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre conjuntos de dados do Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Workspace. Você tem opções adicionais ao configurar uma conexão com o B2B edition. <br>Consulte [Criar ou editar uma conexão](/help/connections/create-connection.md). |
| **Etapa 3: Criar visualizações de dados** | Uma exibição de dados é uma exibição *filtrada* dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição e muito mais. É possível criar várias visualizações de dados para um único conjunto de dados. Você tem opções adicionais ao configurar uma visualização de dados com o B2B edition.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 4: Relatório dos dados entre canais no Espaço de trabalho** | Depois de criar conexões e visualizações de dados, analise os dados B2B que você trouxe usando o poder e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->