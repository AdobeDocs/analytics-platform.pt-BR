---
title: Configurar dados do streaming Google Analytics no Adobe Experience Platform
description: Saiba como configurar sua implementação para enviar uma camada de dados do Google para o Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Configurar dados do streaming Google Analytics no Adobe Experience Platform

Esta página foca em como assimilar seus dados de Google Analytics ativos no Adobe Experience Platform, permitindo que você faça referência a esse conjunto de dados em uma Exibição de dados no Customer Journey Analytics. Você pode combinar as etapas desta página com [Assimilar dados históricos do Google Analytics no Adobe Experience Platform](backfill.md), que gera um conjunto de dados contendo dados históricos. Combine um conjunto de dados de transmissão com um conjunto de dados de preenchimento retroativo para obter uma visualização contínua dos dados passados e presentes no Customer Journey Analytics.

A configuração da coleta de dados envolve as seguintes etapas:

1. Implementar [Tags do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR). Consulte a [Guia de início rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) para ativar e executar uma implementação básica.
1. Instale o [Extensão da camada de dados do Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Essa extensão atua como uma alternativa à instalação da extensão Web SDK, direcionada especificamente para uma camada de dados do Google.
1. [Criar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) na Coleta de dados do Adobe Experience Platform. Configure o Datastream para enviar dados ao Adobe Experience Platform. No momento, você deve mapear cada objeto de camada de dados do Google para um campo XDM aplicável aqui. O Adobe planeja simplificar esse workflow de mapeamento no futuro.

Depois de implementar e publicar as tags desejadas em seu site, você pode prosseguir para [Criar uma conexão](/help/connections/create-connection.md), em seguida [Criar uma visualização de dados](/help/data-views/create-dataview.md).
