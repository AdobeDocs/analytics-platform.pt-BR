---
title: Migrar dados do Google Analytics
description: Saiba mais sobre o fluxo de trabalho abrangente que permite mover dados do Google Analytics para a Adobe Experience Platform e visualizar relatórios no Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# Migrar dados do Google Analytics

>[!BEGINSHADEBOX]

Este guia aborda a migração de dados para administradores do. Se você for um analista procurando encontrar seus relatórios do GA4 no Customer Journey Analytics, consulte [Transição do Google Analytics 4 para o Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md) e [Relatórios do GA4 no Customer Journey Analytics](/help/getting-started/ga-to-cja/reports.md).

>[!ENDSHADEBOX]

Se você não estiver familiarizado com o Customer Journey Analytics, é possível que a sua organização tenha dados existentes em outra plataforma do Analytics, como o Google Analytics. Você pode seguir essas etapas abrangentes para mover esses dados para a Adobe Experience Platform, permitindo visualizar relatórios no Customer Journey Analytics.

Os fluxos de trabalho são fornecidos tanto para dados históricos quanto para a coleção de dados atual. Você pode seguir um ou ambos os fluxos de trabalho, dependendo das necessidades de dados da sua organização.

## Trazer dados históricos do Google Analytics para a Adobe Experience Platform

A ingestão de dados históricos (preenchimento retroativo) envolve a exportação de dados do Google e a importação desses dados para a Adobe Experience Platform. Consulte [Ingestão de dados do Google Analytics na Adobe Experience Platform](backfill.md).

Depois de trazer os dados históricos para a Platform com êxito, você pode [Configurar a transmissão de dados atuais](streaming.md) ou iniciar imediatamente os relatórios de dados preenchidos retroativamente na Customer Journey Analytics ao [Criar uma conexão](/help/connections/create-connection.md).

## Configurar uma implementação do Google Analytics existente para a Adobe Experience Platform {#configure}

A ingestão de dados atuais (transmissão) envolve o envio de dados para a Adobe Experience Platform Edge Network, que então encaminha esses dados para a Adobe Experience Platform. Consulte [Configurar a transmissão de dados do Google Analytics na Adobe Experience Platform](streaming.md).

## Configurar uma conexão e uma visualização de dados no Customer Journey Analytics

Depois de assimilar dados históricos com sucesso e/ou configurar a coleção de dados na Adobe Experience Platform, é possível [Criar uma conexão](/help/connections/create-connection.md) para permitir que o Customer Journey Analytics referencie esses dados.

Use a conexão para criar uma ou mais [Visualizações de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace.

## Criar relatórios

Depois de configurar dimensões e métricas em uma visualização de dados, você pode começar a usar o Analysis Workspace para gerar os relatórios desejados. Consulte [Relatório de dados do Google Analytics no Customer Journey Analytics](report.md).
