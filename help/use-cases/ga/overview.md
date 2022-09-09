---
title: Migrar dados do Google Analytics para o Customer Journey Analytics
description: Saiba mais sobre o fluxo de trabalho abrangente sobre como mover dados do Google Analytics para o Adobe Experience Platform e visualizar relatórios no Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Migrar dados do Google Analytics para o Customer Journey Analytics

Se você não estiver familiarizado com o Customer Journey Analytics, é possível que sua organização tenha dados existentes em outra plataforma do Analytics, como o Google Analytics. Você pode seguir essas etapas abrangentes para mover esses dados para o Adobe Experience Platform, permitindo exibir os relatórios no Customer Journey Analytics.

Os workflows são fornecidos para dados históricos e coleta de dados atuais. Você pode seguir um ou ambos os fluxos de trabalho, dependendo das necessidades de dados da sua organização.

## Trazer dados históricos do Google Analytics para o Adobe Experience Platform

A inserção de dados históricos (preenchimento retroativo) envolve a exportação de dados do Google e a importação desses dados para o Adobe Experience Platform. Consulte [Assimilar dados do Google Analytics no Adobe Experience Platform](backfill.md).

Depois de trazer os dados históricos para a Plataforma com sucesso, você pode [Configurar o streaming de dados atuais](streaming.md)ou inicie imediatamente os relatórios em dados preenchidos retroativamente no CJA por [Criação de uma conexão](/help/connections/create-connection.md).

## Configurar uma implementação do Google Analytics existente para o Adobe Experience Platform {#configure}

A inserção de dados atuais (streaming) envolve o envio de dados para o Adobe Experience Edge, que encaminha esses dados para o Adobe Experience Platform. Consulte [Configurar dados de Google Analytics de transmissão no Adobe Experience Platform](streaming.md).

## Configurar uma conexão e uma visualização de dados no CJA

Depois de assimilar dados históricos com sucesso e/ou configurar a coleta de dados para o Adobe Experience Platform, é possível [Criar uma conexão](/help/connections/create-connection.md) para permitir que o Customer Journey Analytics faça referência a esses dados.

Use a conexão para criar uma ou mais [Visualizações de dados](/help/data-views/create-dataview.md) para uso no Analysis Workspace.

## Criar relatórios

Depois de configurar dimensões e métricas em uma Exibição de dados, você pode começar a usar o Analysis Workspace para gerar os relatórios desejados. Consulte [Relatório de dados Google Analytics no Customer Journey Analytics](report.md).
