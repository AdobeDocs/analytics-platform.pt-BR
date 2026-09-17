---
title: Customer Journey Analytics Report Builder
description: Descreve como usar o Report Builder para obter dados do Customer Journey Analytics no Excel para relatórios recorrentes.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

Este artigo descreve como [!DNL Report Builder] pode ser usado para implementar o seguinte [caso de uso de exportação de dados](overview.md):

* Relatórios ad hoc e recorrentes

## Introdução

[!DNL Report Builder] [!DNL Report Builder] é um suplemento do Microsoft Excel que extrai dados do Customer Journey Analytics para blocos de dados em uma pasta de trabalho. Os usuários empresariais que já estão familiarizados com o Excel podem criar relatórios recorrentes sem aprender a usar o Analysis Workspace ou o SQL.

## Mais informações

Cada bloco de dados em [!DNL Report Builder] retorna até 50.000 linhas. Para recuperar mais linhas, use as opções **[!UICONTROL Página]** e **[!UICONTROL Linhas]** para obter dados em páginas sequenciais além do limite de 50.000 linhas. Consulte [Filtrar dimensões](/help/report-builder/filter-dimensions.md) para obter mais informações.

Você pode agendar uma pasta de trabalho para entrega por email ou exportá-la para um destino na nuvem, como Amazon S3, Google Cloud Platform ou Azure. Consulte [Agendar pastas de trabalho compartilhando por email](/help/report-builder/schedule-reportbuilder.md) e [Agendar pastas de trabalho exportando para destinos na nuvem](/help/report-builder/report-builder-export.md) para obter mais informações.

Para obter uma introdução sobre como configurar e usar o [!DNL Report Builder], consulte [visão geral do Report Builder](/help/report-builder/rb-overview.md).
