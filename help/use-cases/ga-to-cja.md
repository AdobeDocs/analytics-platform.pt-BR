---
title: Como obter dados do Google Analytics no Adobe Experience Platform para análise no Customer Journey Analytics (CJA)
description: 'Explica como usar o Customer Journey Analytics (CJA) para assimilar seus dados de Google Analytics e firebase no Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Assimilar dados do Google Analytics no Adobe Experience Platform

Esse caso de uso foca em como assimilar os dados do Google Analytics como um conjunto de dados no Adobe Experience Platform. (Isso se aplica aos dados históricos e ao vivo.) Depois de concluído, você pode combinar ambos os conjuntos de dados para obter uma visualização entre dispositivos da jornada do usuário.

Os conjuntos de dados no Experience Platform são compostos de duas coisas: um esquema e os registros reais no conjunto de dados. O esquema (chamamos isso de Modelo de dados de experiência ou XDM para abreviação) é como as colunas do conjunto de dados e é como o blueprint ou as regras que descrevem os dados em si. Na Plataforma, o Adobe fornece dois tipos de esquemas:

* Schemas prontos para uso que permitem mapear os dados do Google Analytics para automaticamente (chamado de schema do evento de experiência)
* Esquemas personalizados para os quais você pode criar e mapear facilmente os dados do Google Analytics

Um dos aspectos mais eficientes do modelo de dados do Adobe é que ele permite padronizar todos os dados de interação do cliente em um esquema comum; isso facilita muito a junção dos dados no CJA.

## Pré-requisitos

Para realizar essas tarefas, você precisa do seguinte acesso e permissões:

* Acesso ao Adobe Experience Platform
* Acesso ao Universal Google Analytics (versão Google Analytics 360) ou ao Google Analytics 4 (versão gratuita ou versão Google Analytics 360)
* Acesso ao Customer Journey Analytics e suas [Permissões de administrador](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR#admin-access-permissions).

A maneira de trazer dados do Google Analytics para o Adobe Experience Platform depende de qual versão do Google Analytics você está usando:

| Se você usar... | Você também precisa desta licença... | E faça isso... |
| --- | --- | --- |
| **Google Analytics universal** | Google Analytics 360 | Execute as etapas 1 a 5 das instruções abaixo |
| **Google Analytics 4** | Versão GA gratuita ou Google Analytics 360 | Execute as etapas 1 e 3 a 5 das instruções abaixo. Não há necessidade da etapa 2. |

## 1. Conecte seus dados do Google Analytics ao BigQuery

Observe que as instruções a seguir são baseadas no Universal Google Analytics.

Consulte [estas instruções](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Transforme as sessões do Google Analytics em eventos no BigQuery

>[!IMPORTANT]
>
>Esta etapa se aplica somente aos clientes do Universal Analytics

Os dados do GA armazenam cada registro em seus dados como sessão de um usuário em vez de eventos individuais. A transformação dos dados torna os dados compatíveis com o Adobe Experience Platform.

Consulte [estas instruções](https://support.google.com/analytics/answer/3437618?hl=en).

É necessário criar um query SQL para transformar os dados do Universal Analytics em um formato compatível com a Experience Platform. Assista a este vídeo para obter instruções:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Exporte eventos Google Analytics no formato JSON para o Google Cloud Storage e salve-os em um bucket

Consulte [estas instruções](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Traga os dados do armazenamento do Google Cloud para o Experience Platform

Assista a este vídeo para obter instruções:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importe eventos GCS para o Adobe Experience Platform e mapeie para o esquema XDM

Esquema de exportação BigQuery (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
