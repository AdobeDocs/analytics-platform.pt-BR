---
title: Item de dimensão de Resultados Truncado
description: Explica o item de dimensão "Resultados truncados" e por que ele aparece no relatório.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: f0fa126a23e6c99f89db82c91c98b6628d43a983
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 12%

---

# Item de dimensão de Resultados Truncado

Ao usar uma dimensão que contém muitos valores únicos, os resultados do relatório podem ser muito grandes para processamento.  Para evitar lentidão em todo o sistema, os resultados são truncados com a remoção dos itens considerados menos importantes.  Isso é indicado em um painel de Forma livre ao adicionar as palavras &quot;mais de&quot; no indicador de paginação, por exemplo, &quot;Linhas: 1-400 de mais de 9.819.653&quot;.

Em alguns casos, como classificar por uma métrica calculada, é impossível saber quais itens de dimensão são os menos importantes.  Quando isso acontece, um ícone de aviso é colocado na métrica calculada explicando esse problema e vinculando a [alguma documentação](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/dimensions/high-cardinality.html?lang=en).

## Arquitetura de processamento de Customer Journey Analytics e valores únicos

O Customer Journey Analytics processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Quando o servidor terminar o processamento, ele entregará seu subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se qualquer servidor individual agregar um conjunto de resultados que esteja acima de um limite de tamanho, ele truncará os resultados antes de enviá-los de volta. Essa otimização mantém o tráfego de rede e a agregação dentro de limites para permitir relatórios rápidos. Como cada servidor de processamento trunca os resultados somente com a exibição de seus próprios dados, é possível que os itens mostrados no Analysis Workspace tenham valores de métrica ligeiramente inativos.

O servidor escolhe quais itens de dimensão serão descartados com base na métrica usada para classificação. Se a métrica de classificação for uma métrica calculada, o servidor utilizará métricas da métrica calculada para determinar quais itens de dimensão serão truncados. Como as métricas calculadas podem conter várias métricas de importância variável, os resultados podem ser menos precisos. Por exemplo, ao calcular &quot;Receita por pessoa&quot;, o valor total da receita e o número total de pessoas são retornados e agregados antes de fazer a divisão. Como resultado, cada nó escolhe quais itens serão removidos sem saber como seus resultados afetam a classificação geral.

## Diferenças de &quot;Tráfego baixo&quot;

Em versões anteriores do Adobe Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento da coleta. Os itens de Dimension foram colocados como &quot;Tráfego baixo&quot; depois que uma dimensão atingiu 500.000 valores únicos e aplicou uma filtragem mais agressiva em um milhão de valores únicos. A contagem de &quot;Valor único&quot; foi redefinida no início de cada mês. Os dados processados eram permanentes; não havia como obter dados existentes do “Tráfego baixo”.

No Customer Journey Analytics, os itens de dimensão só são truncados se os resultados de um relatório forem muito grandes. Os dados processados não são permanentes, o que significa que você pode reduzir ou eliminar o truncamento modificando seu relatório.

## Reduzir o item de dimensão &quot;Resultados truncados&quot;

Se você quiser reduzir o número de eventos no item de dimensão &quot;Resultados truncados&quot;, o Adobe recomenda qualquer um dos seguintes procedimentos:

* Use um [Filtro](/help/components/filters/create-filters.md). Os filtros são aplicados no momento em que cada servidor processa um subconjunto de dados. Limitar o número de valores únicos retornados reduz o item de dimensão &quot;Resultados truncados&quot;.
* Use uma pesquisa. Se uma pesquisa for usada, os itens que não correspondem à pesquisa serão removidos dos resultados do relatório, aumentando a probabilidade de você ver os itens desejados.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.
