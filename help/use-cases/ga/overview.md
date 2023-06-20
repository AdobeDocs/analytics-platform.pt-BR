---
title: Migrar dados do Google Analytics para o Customer Journey Analytics
description: Saiba mais sobre o fluxo de trabalho abrangente que permite mover dados do Google Analytics para a Adobe Experience Platform e visualizar relatórios no Customer Journey Analytics.
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 87%

---

# Migrar dados do Google Analytics para o Customer Journey Analytics

Se você não estiver familiarizado com o Customer Journey Analytics, é possível que a sua organização tenha dados existentes em outra plataforma do Analytics, como o Google Analytics. Você pode seguir essas etapas abrangentes para mover esses dados para a Adobe Experience Platform, permitindo visualizar relatórios no Customer Journey Analytics.

Os fluxos de trabalho são fornecidos tanto para dados históricos quanto para a coleção de dados atual. Você pode seguir um ou ambos os fluxos de trabalho, dependendo das necessidades de dados da sua organização.

## Trazer dados históricos do Google Analytics para a Adobe Experience Platform

A ingestão de dados históricos (preenchimento retroativo) envolve a exportação de dados do Google e a importação desses dados para a Adobe Experience Platform. Consulte [Ingestão de dados do Google Analytics na Adobe Experience Platform](backfill.md).

Depois de trazer os dados históricos para a Platform com sucesso, você pode [Configurar transmissão de dados atuais](streaming.md), ou comece imediatamente a relatar dados preenchidos retroativamente no Customer Journey Analytics por [Criação de uma conexão](/help/connections/create-connection.md).

## Configurar uma implementação do Google Analytics existente para a Adobe Experience Platform {#configure}

A ingestão de dados atuais (transmissão) envolve o envio de dados para o Adobe Experience Edge, que então encaminha esses dados para a Adobe Experience Platform. Consulte [Configurar a transmissão de dados do Google Analytics na Adobe Experience Platform](streaming.md).

## Configurar uma conexão e uma visualização de dados no Customer Journey Analytics

Depois de assimilar dados históricos com sucesso e/ou configurar a coleção de dados na Adobe Experience Platform, é possível [Criar uma conexão](/help/connections/create-connection.md) para permitir que o Customer Journey Analytics referencie esses dados.

Use a conexão para criar uma ou mais [Visualizações de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace.

## Criar relatórios

Depois de configurar dimensões e métricas em uma visualização de dados, você pode começar a usar o Analysis Workspace para gerar os relatórios desejados. Consulte [Relatório de dados do Google Analytics no Customer Journey Analytics](report.md).
