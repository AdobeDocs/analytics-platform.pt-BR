---
description: Mostra exemplos de métricas filtradas e ponderadas.
title: Métricas filtradas e ponderadas
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 76%

---

# Métricas filtradas e ponderadas

Mostra exemplos de métricas filtradas e ponderadas.

## Taxa de rejeição filtrada {#section_D42F2452E4464948934063EB6F2DAAB4}

Essa métrica filtrada simples mostra a taxa de rejeição das páginas com mais de 100 visitas:

![Janela de resumo que mostra as métricas aplicadas à coluna 1 (Visitas) e à coluna 2 (100) juntamente com a Taxa de rejeição. ](assets/cm_fbr.png)

Tenha em mente que esta fórmula depende de um intervalo de tempo consistente. Se você gerar um relatório para um único dia, qualquer página com mais de 20 visitas merece atenção. Se você gerar um relatório de um mês, pode querer filtrar para incluir mais visitas.

## Taxa de rejeição filtrada com percentil {#section_4F3E6D33A1FD438A932FA662B3510552}

Esse filtro mostra a Taxa de rejeição para os primeiros 30% das páginas, quando classificadas por visitas.

![Se e, em seguida, filtre mostrando a Taxa de rejeição para os 30% principais de páginas classificadas por visitas.](assets/cm_wbr_2.png)

## Métrica ponderada {#section_F2D16B14569948289CF1310F9E6E3FC2}

Suponha que você deseja classificar pela taxa de rejeição em geral, mas ainda quer exibir as páginas com mais visitas no topo da lista. Você pode criar uma Taxa de rejeição ponderada com a seguinte aparência:

![Resumo com definição para Taxa de Rejeição vezes Visitas.](assets/cm_wbr.png)
