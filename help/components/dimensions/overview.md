---
title: Visão geral das dimensões
description: Saiba o que são dimensões e como são usadas no Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 65b4339b4a1b27c41cfe442482a54661989d704b
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 26%

---

# Visão geral das dimensões

Dimensões são um tipo de componente no Customer Journey Analytics usado para analisar dados. Por exemplo, você usa dimensões ao criar relatórios no [Analysis Workspace](/help/analysis-workspace/home.md) ou no [Report Builder](/help/report-builder/rb-overview.md).

As dimensões do Customer Journey Analytics são do tipo ilimitado; os valores podem ser numéricos, texto, objetos, listas ou misturas de todos.

Um relatório básico no Customer Journey Analytics mostra linhas de dimensões (geralmente valores de sequência) em relação a uma coluna de métricas (geralmente valores numéricos).

Por exemplo, se você combinasse a dimensão Página com a métrica Pessoas, receberia um relatório classificado mostrando suas páginas mais visitadas por pessoas:

| Página | Pessoas |
| --- | ---: |
| Página inicial | 800 |
| Página do produto | 500 |
| Página de compra | 100 |

{style="table-layout:fixed"}

Cada dimensão representa uma parte ou uma faceta diferente do site. É possível combinar uma ou mais dessas dimensões com uma ou mais métricas para criar o relatório desejado.


## Criar dimensões

Os administradores do Customer Journey Analytics podem [criar dimensões em uma visualização de dados](/help/data-views/create-dataview.md#components).

## Dimensões padrão

Ao criar uma visualização de dados, os seguintes componentes são adicionados por padrão como dimensões à visualização de dados:

{{standard-dimensions}}


## Adicionar descrições de dimensão

Os administradores do Customer Journey Analytics podem adicionar descrições de dimensões e outros componentes na visualização de dados ou diretamente no Analysis Workspace. Para obter informações sobre como adicionar descrições a dimensões, consulte [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).
