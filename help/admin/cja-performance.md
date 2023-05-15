---
title: Otimizar o desempenho do CJA
description: Práticas recomendadas sobre como otimizar o desempenho do CJA
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: 98360149433689ae89a9f093bbfad24ebc92db17
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 93%

---


# Otimizar o desempenho do CJA

>[!NOTE]
>
>Para otimizar os fatores de desempenho do Workspace, consulte [Otimizar [!UICONTROL Analysis Workspace] desempenho](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Esses fatores influenciam o desempenho geral do CJA:

| Fator | Definição | Influenciado por | Otimização |
| --- | --- | --- | --- |
| Complexidade de filtro | Filtros complexos podem ter um impacto significativo no desempenho do projeto. | Veja a seguir alguns fatores que adicionam complexidade a um filtro (em ordem decrescente de impacto): <ul><li>Operadores de “contém”, “contem qualquer um de”, “corresponde”, “começa com” ou “termina com” </li><li>Filtragem sequencial, especialmente quando restrições de dimensão (Dentro/Depois de) são usadas </li><li>Número de itens de dimensão exclusivos em dimensões usadas no filtro (por exemplo, uma Página = “A” que contiver 10 itens exclusivos será mais rápida que uma Página = “A” que contiver 100.000 itens exclusivos) </li><li>O número de diferentes dimensões usadas (por exemplo, Página = “Home” e Página = “Search results” será mais rápido que eVar 1 = “red” e eVar 2 = “blue”)</li><li>Muitos operadores OR (em vez de AND)</li><li>Contêineres aninhados que variam no escopo (por exemplo, “Hit” dentro de “Visit” dentro de “Visitante”)</li></ul> | Embora alguns dos fatores de complexidade não possam ser evitados, procure por oportunidades para reduzir a complexidade de seus filtros. Em geral, quanto mais específico você puder ser com os critérios de filtro, melhor. Por exemplo:<ul><li>Com contêineres, usar um único contêiner na parte superior do filtro será mais rápido que uma série de contêineres aninhados.</li><li>Com operadores, “igual” será mais rápido que “contém” e “é igual a qualquer um de” será mais rápido que “contem qualquer um de”.</li><li>Com muitos critérios, operadores AND serão mais rápidos que uma série de operadores OR.</li></ul> Procure oportunidades para reduzir muitas declarações OR em uma única declaração “é igual a qualquer um de”.<br> |
| Complexidade de visualização (filtros, métricas, filtros) | O tipo de visualização (por exemplo, fallout ou tabela de forma livre) adicionado a um projeto não influencia muito o desempenho do projeto. É a complexidade da visualização que aumentará o tempo de processamento. | Fatores que adicionam complexidade à visualização incluem:<ul><li>Intervalo de dados solicitado</li><li>Números de filtros aplicados; por exemplo, filtros usados como linhas de uma tabela de forma livre</li><li>Uso de filtros complexos</li><li>Linhas ou colunas de [itens estáticas](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) em tabelas de forma livre</li><li>Filtros aplicados a linhas em tabelas de forma livre</li><li>Número de métricas incluídas, especialmente métricas calculadas que usam filtros</li></ul> | Se você observar que seus projetos não estão carregando tão rápido quanto gostaria, tente substituir alguns filtros por eVars e filtros, se possível.<br><br>Se você estiver sempre usando filtros e métricas calculadas em dados importantes para sua empresa, tente aprimorar sua implementação para capturar esses dados de forma mais direta. O uso de um gerenciador de tags, como o Adobe Experience Platform Launch, e das regras de processamento da Adobe facilita e agiliza as alterações na implementação. |
| Capacidade do data center | A capacidade de geração de relatórios que você e outros clientes compartilham em um data center da Adobe. | Isso é afetado pelo número de queries simultâneas feitas pela sua organização e outras organizações em seu data center. | Sua organização tem direito a uma capacidade definida e, se o sistema não estiver sobrecarregado, a Adobe transferirá mais capacidade para você, acima e além da capacidade permitida a você. |
