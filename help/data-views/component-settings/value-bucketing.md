---
title: Configurações do componente de agrupar valores em buckets
description: Combinar valores numéricos em uma dimensão.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 100%
---
# Configurações do componente [!UICONTROL Agrupamento de valores em buckets] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Agrupamento de valores em buckets"
>abstract="Valores de bloco em intervalos específicos. Estes intervalos aparecem como itens de dimensão nos relatórios."

<!-- markdownlint-enable MD034 -->


Ao criar ou editar uma visualização de dados, o agrupamento de valores em buckets permite combinar valores numéricos com base em um intervalo. Essa função está disponível apenas para dimensões que utilizam tipos de dados Integer ou Double do esquema.

![Agrupamento de valores em buckets](../assets/value-bucketing.png)

O agrupamento de valores em buckets é importante quando você deseja agrupar intervalos, em vez de tratar cada número único como um item de dimensão separado. Por exemplo, um bucket “Entre 5 e 10” será exibido como um item de linha “5 a 10” no Analysis Workspace.

Se você quiser a flexibilidade de criar relatórios sobre dimensões agrupadas em buckets ou não agrupadas, arraste duas cópias do componente para a lista de dimensões disponíveis. Habilite o agrupamento em buckets em uma dimensão e desabilite na outra.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Valor do bloco] | Uma caixa de seleção que permite habilitar o agrupamento em buckets. |
| [!UICONTROL Menos que] | O limite superior do primeiro bucket de dimensão. |
| [!UICONTROL Incluindo] [!UICONTROL e menor que] | Limites dos buckets subsequentes. |
| [!UICONTROL Maior que ou igual a] | O limite inferior do último bucket de dimensão. |
| [!UICONTROL Adicionar bloco] | Permite adicionar outro bucket ao agrupamento de dimensões numéricas em buckets. Você pode adicionar até 20 buckets em uma única dimensão. |

{style="table-layout:auto"}
