---
title: Item de dimensão Longo
description: Explica o item de dimensão "Cauda longa" e por que ele aparece no relatórios.
translation-type: tm+mt
source-git-commit: ff1a11a18de0825b6338de98865e3bddeef14f39
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Item de dimensão Longo

Se você usar uma dimensão que contém um grande número de valores únicos, às vezes você pode ver um valor no relatórios chamado &quot;Cauda longa&quot;. Esse item de dimensão significa que a arquitetura do relatórios que o CJA usa continha muitos valores únicos para que fosse processada.

## Arquitetura de processamento CJA e valores únicos

O CJA processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado para vários servidores. Os dados por servidor de processamento são agrupados por ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Quando terminar o processamento, ele enviará seu subconjunto de dados processados para um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados na forma de um relatório do Workspace.

Se qualquer servidor individual que estiver processando um subconjunto de dados encontrar mais de 500.000 itens de dimensão únicos, ele retornará os 500.000 itens de dimensão principais de seu próprio subconjunto e retornará o restante em &#39;Longa Cauda&#39;. O item de dimensão &#39;Longa Cauda&#39; visto em um relatório da Workspace é o total agregado dos valores individuais de cada servidor de processamento que excederam 500 mil valores únicos.

## Diferenças entre &#39;Longa Cauda&#39; e &#39;Baixo Tráfego&#39;

Nas versões anteriores do Adobe Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento em que eram coletados. Os itens de Dimension foram colocados em &#39;Baixo tráfego&#39; depois que uma dimensão alcançou valores exclusivos de 500K e aplicou uma filtragem mais agressiva em valores exclusivos de 1M. A contagem de valores únicos foi redefinida no início de cada mês do calendário. Os dados processados eram permanentes; não havia como obter os dados existentes do &quot;tráfego baixo&quot;.

No CJA, os itens de dimensão são colocados somente em &#39;Longa Cauda&#39; se um servidor de processamento individual contiver mais de 500K valores únicos. Os dados processados não são permanentes, o que significa que você pode reduzir o item de dimensão &#39;Longa Cauda&#39; modificando seu relatório.

## Reduzir o item de dimensão &quot;Longa Cauda&quot;

Se você quiser reduzir o item de dimensão &quot;Longa Cauda&quot;, o Adobe recomenda qualquer uma das seguintes opções:

* Use um filtro. Os filtros se aplicam no momento em que cada servidor processa um subconjunto de dados. A limitação do número de valores únicos que eles retornam reduz o item de dimensão &#39;Longa Cauda&#39;.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados de evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contenha mais de 500 mil itens de dimensão exclusivos. Se você aplicar um segmento ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir a presença de &quot;Longa Cauda&quot; enquanto facilita o consumo do relatório. A Adobe planeja melhorar essa experiência à medida que a CJA for desenvolvendo mais.
