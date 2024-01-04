---
title: Configurar transmissão de dados do Google Analytics para a Adobe Experience Platform
description: Saiba como configurar sua implementação para enviar uma camada de dados do Google para a Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 100%

---

# Configurar transmissão de dados do Google Analytics para a Adobe Experience Platform

Esta página foca em como assimilar seus dados em tempo real do Google Analytics na Adobe Experience Platform, permitindo que você referencie esse conjunto de dados em uma Visualização de dados no Customer Journey Analytics. Você pode combinar as etapas desta página com a [Ingestão de dados históricos do Google Analytics na Adobe Experience Platform](backfill.md), que gera um conjunto de dados contendo dados históricos. Combine um conjunto de dados de transmissão com um conjunto de dados de preenchimento retroativo para obter uma visualização contínua de dados anteriores e atuais no Customer Journey Analytics.

A configuração da coleção de dados envolve as seguintes etapas:

1. Implementar [Tags para a Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR). Consulte o [Guia de início rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=pt-BR) para ativar e executar uma implementação básica.
1. Instalar a [Extensão da camada de dados do Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=pt-BR). Essa extensão atua como uma alternativa à instalação da extensão do SDK da Web, direcionada especificamente para uma camada de dados do Google.
1. [Criar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=pt-BR) na coleção de dados da Adobe Experience Platform. Configurar a sequência de dados para enviar dados à Adobe Experience Platform. No momento, você deve mapear aqui cada objeto de camada de dados do Google para um campo XDM aplicável. A Adobe planeja simplificar esse fluxo de trabalho de mapeamento no futuro.

Depois de implementar e publicar as tags desejadas em seu site, você pode prosseguir para [Criar uma conexão](/help/connections/create-connection.md) e, em seguida, [Criar uma visualização de dados](/help/data-views/create-dataview.md).
