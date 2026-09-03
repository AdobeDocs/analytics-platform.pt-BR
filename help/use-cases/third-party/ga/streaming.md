---
title: Configurar dados de transmissão do Google Analytics
description: Saiba como configurar sua implementação para enviar uma camada de dados do Google para a Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T09:49:39.181Z'
TQID: 'https://experienceleague.adobe.com/xav7bGdbGLjYXm70GJBSxnDMfNDZpYp5qij1IqkaZSY'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: e1bd5a34-b16e-477b-84cc-247fa0793f4b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 90%

---

# Configurar dados de transmissão do Google Analytics

Esta página foca em como assimilar seus dados em tempo real do Google Analytics na Adobe Experience Platform, permitindo que você referencie esse conjunto de dados em uma Visualização de dados no Customer Journey Analytics. Você pode combinar as etapas desta página com a [Ingestão de dados históricos do Google Analytics na Adobe Experience Platform](backfill.md), que gera um conjunto de dados contendo dados históricos. Combine um conjunto de dados de transmissão com um conjunto de dados de preenchimento retroativo para obter uma visualização contínua de dados anteriores e atuais no Customer Journey Analytics.

A configuração da coleção de dados envolve as seguintes etapas:

1. Implementar [Tags para a Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR). Consulte o [Guia de início rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=pt-BR) para ativar e executar uma implementação básica.
1. Instalar a [Extensão da camada de dados do Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=pt-BR). Essa extensão atua como uma alternativa à instalação da extensão do SDK da Web, direcionada especificamente para uma camada de dados do Google.
1. [Criar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=pt-BR) na coleção de dados da Adobe Experience Platform. Configurar a sequência de dados para enviar dados à Adobe Experience Platform. No momento, você deve mapear aqui cada objeto de camada de dados do Google para um campo XDM aplicável. A Adobe planeja simplificar esse fluxo de trabalho de mapeamento no futuro.

Depois de implementar e publicar as marcas desejadas em seu site, você pode prosseguir para [criar uma conexão](/help/connections/create-connection.md) e, em seguida, [criar uma visualização de dados](/help/data-views/create-dataview.md).
