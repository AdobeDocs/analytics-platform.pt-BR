---
title: Visão geral de dimensões
description: Saiba o que são dimensões e como elas são usadas no Customer Journey Analytics.
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Visão geral de dimensões

Dimensões são um tipo de componente no Customer Journey Analytics usado para analisar dados. Por exemplo, você pode usar dimensões ao criar relatórios no [Analysis Workspace](/help/analysis-workspace/home.md) ou no [Report Builder](/help/report-builder/rb-overview.md).

As dimensões do Customer Journey Analytics são ilimitadas; os valores podem ser números, textos, objetos, listas ou uma combinação desses elementos. 

Um relatório básico no Customer Journey Analytics mostra linhas de dimensões (geralmente valores de string) em relação a uma coluna de métricas (geralmente valores numéricos).

Por exemplo, se você combinar a dimensão Página com a métrica Pessoas, o resultado será um relatório classificado com as páginas mais visitadas pelas pessoas:

| Página | Pessoas |
| --- | ---: |
| Página inicial | 800 |
| Página do produto | 500 |
| Página de compra | 100 |

{style="table-layout:fixed"}

Cada dimensão representa uma parte ou uma faceta diferente do site. É possível combinar uma ou mais dessas dimensões com uma ou mais métricas para criar o relatório desejado.


## Criar dimensões

Admins do Customer Journey Analytics podem [criar dimensões em uma visualização de dados](/help/data-views/create-dataview.md#components).

## Dimensões padrão

Ao criar uma visualização de dados, os seguintes componentes são adicionados por padrão como dimensões à visualização de dados:

{{standard-dimensions}}


## Adicionar descrições de dimensão

Admins do Customer Journey Analytics podem adicionar descrições para dimensões e outros componentes na visualização de dados ou diretamente no Analysis Workspace. Para obter informações sobre como adicionar descrições a dimensões, consulte [Adicionar descrições de componentes](/help/components/add-component-descriptions.md).

>[!MORELIKETHIS]
>
>[Descubra insights do cliente mais profundos com o recurso Profundidade do evento](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947?profile.language=pt#M576)
>

