---
title: Item de dimensão de Cauda Longa
description: Explica o item de dimensão "Cauda longa" e por que ele aparece no relatório.
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Item de dimensão de Cauda Longa

Se você usar uma dimensão que contém um grande número de valores únicos, às vezes poderá ver um valor no relatório rotulado **[!UICONTROL Cauda longa]**. Esse item de dimensão significa que a arquitetura de relatórios que o CJA usa continha muitos valores únicos para ser processada.

## Arquitetura de processamento CJA e valores exclusivos

O CJA processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Depois que terminar o processamento, ele entregará seu subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se qualquer servidor individual que esteja processando um subconjunto de dados encontrar mais de 500.000 itens de dimensão exclusivos, ele retornará os 500.000 itens de dimensão principais de seu próprio subconjunto e retornará o restante em &#39;[!UICONTROL Long Tail]&#39;. O item de dimensão &#39;[!UICONTROL Long Tail]&#39; visualizado em um relatório do Workspace é o total agregado de cada valor individual do servidor de processamento que excedeu 500 mil valores exclusivos.

## Diferenças entre &quot;Longo caminho&quot; e &quot;Tráfego baixo&quot;

Em versões anteriores do Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento em que eram coletados. Os itens de Dimension foram colocados em &quot;Tráfego baixo&quot; após uma dimensão ter atingido 500 K de valores únicos e aplicado uma filtragem mais agressiva em valores exclusivos de 1M. A contagem de valor único foi redefinida no início de cada mês. Os dados processados eram permanentes; não havia como obter dados existentes do &quot;Tráfego baixo&quot;.

No CJA, os itens de dimensão são colocados apenas em &quot;Cauda longa&quot; se um servidor de processamento individual contiver mais de 500 mil valores únicos. Os dados processados não são permanentes, o que significa que você pode reduzir o item de dimensão &quot;Cauda longa&quot; modificando seu relatório.

## Reduza o item de dimensão &quot;Cauda longa&quot;

Se quiser reduzir o item de dimensão &quot;Cauda longa&quot;, o Adobe recomenda qualquer um dos seguintes:

* Use um [filtro](/help/components/filters/create-filters.md). Os filtros se aplicam no momento em que cada servidor processa um subconjunto de dados. Limitar o número de valores únicos retornados reduz o item de dimensão &quot;Cauda longa&quot;.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contém mais de 500 mil itens de dimensão exclusivos. Se você aplicar um filtro ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir a presença de &quot;Longo caminho&quot; enquanto facilita o consumo de seu relatório. O Adobe pretende melhorar essa experiência à medida que o CJA for sendo desenvolvido.
