---
title: Tabela completa de exportação do Customer Journey Analytics
description: Descreve como usar a funcionalidade Exportar tabela completa para validar seus dados ou usar seus dados para IA/ML.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# Exportar tabela completa

Este artigo descreve como a funcionalidade [!DNL Export full table] pode ser usada para implementar o seguinte [caso de uso de exportação de dados](overview.md):

* Validação de dados
* Disponibilidade para IA/ML

## Introdução

A exportação de dados usando o [!DNL Customer Journey Analytics Full Table Export] permite exportar dados das tabelas de forma livre no Customer Journey Analytics Analysis Workspace.

![Extensão de BI](../assets/export-full-table.png)

## Mais informações

Para exportar o conteúdo completo de qualquer tabela de forma livre criada no Analysis Workspace diretamente para os destinos da nuvem designados, use a funcionalidade Exportar tabela completa.

A exportação de tabela completa aceita até 10 dimensões e 10 métricas por relatório e inclui métricas calculadas e segmentação. Dependendo do nível de licença, você pode exportar 3 milhões, 30 milhões, 150 milhões ou 300 milhões de linhas por exportação, excedendo o limite de 50.000 linhas de outros métodos de exportação. Os destinos compatíveis incluem Zona de aterrissagem de dados da Adobe Experience Platform, Plataforma da Google Cloud, Microsoft Azure, Amazon S3 e Snowflake. Consulte [Vantagens da exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md#advantages) para obter mais informações.

Para obter mais informações, consulte a documentação detalhada em [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md).
