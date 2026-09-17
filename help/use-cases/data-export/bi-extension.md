---
title: Extensão de BI do Customer Journey Analytics
description: Descreve como usar a extensão BI para trazer dados digitais para suas próprias ferramentas de BI ou Data Lake para usar com conjuntos de dados adicionais.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# Extensão BI

Este artigo descreve como o [!DNL Customer Journey Analytics BI extension] pode ser usado para implementar o seguinte [caso de uso de exportação de dados](overview.md):

* Ferramentas Data Lake, Data Warehouse ou BI

## Introdução

A exportação de dados usando o [!DNL Customer Journey Analytics BI extension] permite exportar dados das visualizações de dados do Customer Journey Analytics.

![Extensão de BI](../assets/bi-extension.png)

## Mais informações

O [!DNL Customer Journey Analytics BI extension] habilita o acesso SQL às [visualizações de dados](/help/data-views/data-views.md) definidas no Customer Journey Analytics. Seus engenheiros de dados e analistas estão mais familiarizados com o Power BI, o Tableau ou outras ferramentas de business intelligence e visualização (mais conhecidas como ferramentas de BI). Agora é possível criar relatórios e painéis com base nas mesmas visualizações de dados que usuários(as) do Customer Journey Analytics usam para criar seus projetos do Analysis Workspace.

A extensão BI retorna dados agregados, não linhas brutas no nível de evento. Por padrão, cada consulta retorna 50 linhas para um intervalo de datas de 30 dias, mas você pode substituir o limite de linhas por no máximo 50.000 linhas e o intervalo de datas pelo seu próprio intervalo personalizado. Consulte [Padrões e limitações](../../data-views/bi-extension.md#defaults-and-limitations) para obter mais informações.

Para obter mais informações, consulte a documentação detalhada sobre a [extensão de BI](../../data-views/bi-extension.md).
