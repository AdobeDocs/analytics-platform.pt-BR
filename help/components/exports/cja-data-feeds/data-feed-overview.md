---
description: Saiba como usar feeds de dados para obter dados brutos do Customer Journey Analytics. Descubra os pré-requisitos para usar os feeds de dados e o que fazer a seguir.
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Visão geral do feed de dados do Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 8c577ff8508f15944ced77aaf20b692c911fdd3e
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 21%

---

# Visão geral dos feeds de dados

Os feeds de dados são uma maneira avançada de obter dados brutos do Customer Journey Analytics. Você pode usar esses dados brutos em outras plataformas fora da Adobe, a critério da sua organização. Os dados são fornecidos em lotes por hora, no final de cada hora, ou em lotes diários, no final de cada dia.

## Pré-requisitos

Verifique se você atende a todos os requisitos a seguir antes de usar os feeds de dados:

* Uma implementação em funcionamento com dados sendo assimilados na Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Sua conta é um administrador de produto do Analytics ou pertence a um perfil de produto com acesso a feeds de dados <!--???-->
* Um bucket configurado em [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] ou [!DNL Azure SAS]

## Introdução

Para começar a usar os feeds de dados no Customer Journey Analytics, primeiro entenda como os feeds de dados no Customer Journey Analytics diferem dos feeds de dados no Adobe Analytics. Depois de entender as diferenças, é possível mapear feeds de dados do Adobe Analytics para o Customer Journey Analytics e, em seguida, começar a criar um feed de dados.

1. [Entender as diferenças entre os feeds de dados no Customer Journey Analytics e no Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Mapear colunas do feed de dados do Adobe Analytics para o Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).
