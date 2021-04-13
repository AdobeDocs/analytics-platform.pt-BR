---
title: Configurar relatórios do Google Analytics no Customer Journey Analytics
description: null
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 49b49f24dbc68b1d9e843e0f4522123e6792a438
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Configurar relatórios do Google Analytics no Customer Journey Analytics

Este caso de uso explica como obter os dados do Google Analytics no Adobe Experience Platform e

## Pré-requisitos

* Acesso ao Adobe Experience Platform
* Acesso ao Universal Google Analytics (versão Google Analytics 360) ou ao Google Analytics 4 (versão gratuita ou versão Google Analytics 360)
* Acesso ao Customer Journey Analytics

## 1. Conectar dados do Google Analytics ao Adobe Experience Platform

A maneira de trazer dados do Google Analytics para o Adobe Experience Platform depende de qual versão do Google Analytics você está usando:

| Se você usar... | Você também precisa desta licença... | E faça isso... |
| --- | --- | --- |
| **Google Analytics universal** | Google Analytics 360 | Execute as etapas 1 a 5 das instruções abaixo |
| **Google Analytics 4** | Versão GA gratuita ou Google Analytics 360 | Execute as etapas 2 - 5 das instruções abaixo. Não é necessário o passo 1. |

As instruções a seguir são baseadas no Universal Google Analytics.

1. Conecte seus dados do Google Analytics ao BigQuery para transformar alguns dados.
Consulte [estas instruções](https://support.google.com/analytics/answer/3416092?hl=en).

1. (Somente clientes do Universal Analytics) Transforme as sessões do Google Analytics em eventos no BigQuery.
Isso torna os dados compatíveis com o Adobe Experience Platform. Consulte [estas instruções](https://support.google.com/analytics/answer/3437618?hl=en).

   Detalhes: No BigQuery, seus dados de GA aparecerão como uma tabela:

   ![](assets/ga-bigquery.png)
É necessário criar um query SQL para transformar os dados do Universal Analytics em um formato compatível com a Experience Platform. Assista a este vídeo para obter instruções:

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. Exporte eventos Google Analytics no formato JSON para o Google Cloud Storage e salve-os em um bucket.
Consulte [estas instruções](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

1. Traga os dados do armazenamento do Google Cloud para o Experience Platform.
Assista a este vídeo para obter instruções:

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. Importar eventos GCS para o Adobe Experience Platform e mapear para o esquema XDM

Esquema de exportação BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
