---
title: Visão geral das dimensões
description: Saiba quais são as dimensões e como elas são usadas no Customer Journey Analytics
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Visão geral das dimensões

Dimension são um tipo de componente em Customer Journey Analytics usado para analisar dados. Por exemplo, você usa dimensões ao criar relatórios no [Analysis Workspace](/help/analysis-workspace/home.md) ou no [Report Builder](/help/report-builder/report-buider-overview.md).

as dimensões Customer Journey Analytics são do tipo ilimitado; os valores podem ser numéricos, texto, objetos, listas ou misturas de todos.

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

Ao criar uma visualização de dados, os seguintes componentes baseados em tempo são adicionados por padrão como dimensões à visualização de dados:

- 15 minutos
- 30 minutos
- 5 minutos
- Dia
- Dia do mês
- Dia da semana
- Dia do ano
- Hora
- Hora do dia
- Minuto
- Minuto da hora
- Mês
- Mês do ano
- Trimestre
- Trimestre do ano
- Segundo
- Semana do ano
- Ano

## Adicionar descrições de dimensão

Os administradores de Customer Journey Analytics podem adicionar descrições de dimensões e outros componentes na visualização de dados ou diretamente no Analysis Workspace. Para obter informações sobre como adicionar descrições a dimensões, consulte [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).
