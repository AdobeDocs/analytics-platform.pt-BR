---
title: Configurar relatórios do Google Analytics no Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Configurar relatórios do Google Analytics no Customer Journey Analytics

configuração do Conector de armazenamento do Google Cloud,

configurar o Google Tag Manager

Esquema de exportação BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. Converter sessões do GA em eventos no Big Query
1. Exportar eventos do Google Analytics para o Google Cloud Storage
1. Importar eventos GCS para o Adobe Experience Platform e mapear para o esquema XDM

## Pré-requisitos

* Acesso ao Adobe Experience Platform
* Acesso ao Universal Google Analytics (versão Google Analytics 360) ou ao Google Analytics 4 (versão gratuita ou versão Google Analytics 360)
* Acesso ao Customer Journey Analytics

## Conectar dados do Google Analytics ao Adobe Experience Platform

A maneira de trazer dados do Google Analytics para o Adobe Experience Platform depende de qual versão do Google Analytics você está usando:

| Se você usar... | Você também precisa desta licença... | E faça isso... |
| --- | --- | --- |
| **Google Analytics universal** | Google Analytics 360 | Execute as etapas 1 - x das instruções abaixo |
| **Google Analytics 4** | Versão GA gratuita ou Google Analytics 360 | Não é necessário o passo x nas instruções abaixo. |

As instruções a seguir são baseadas no Universal Google Analytics.

1. Conecte seus dados do Google Analytics ao BigQuery e
Consulte [estas instruções](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Somente clientes do Universal Analytics) Transforme as sessões do Google Analytics em eventos no BigQuery.
Consulte [estas instruções](https://support.google.com/analytics/answer/3437618?hl=en).
1. Exporte Google Analytics para o Armazenamento do Google Cloud.
Consulte [estas instruções](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
