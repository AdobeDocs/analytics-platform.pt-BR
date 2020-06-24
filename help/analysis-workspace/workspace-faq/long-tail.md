---
title: Valor de dimensão Longo da Cauda
description: Explica o valor da dimensão "Cauda longa" e por que ela aparece no relatórios.
translation-type: tm+mt
source-git-commit: 8f59697b2bb282a1057267131343229e12dd5111
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Valor de dimensão Longo da Cauda

Se você usar uma dimensão que contém um grande número de valores únicos, às vezes você pode ver um valor no relatórios chamado &quot;Cauda longa&quot;. Esse valor de dimensão significa que a arquitetura do relatórios que o CJA usa continha muitos valores únicos para ser processada.

## Arquitetura de processamento CJA e valores únicos

O CJA processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado para vários servidores. Os dados por servidor de processamento são agrupados por ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Quando terminar o processamento, ele enviará seu subconjunto de dados processados para um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados na forma de um relatório do Workspace.

Se um servidor individual que processa um subconjunto de dados encontrar mais de 500.000 valores de dimensão únicos, ele retornará os 500.000 valores de dimensão principais de seu próprio subconjunto, em seguida, retornará o restante em &#39;Longa Cauda&#39;. O valor da dimensão &#39;Longa Cauda&#39; visto em um relatório da Workspace é o total agregado dos valores individuais de cada servidor de processamento que excederam 500 mil valores únicos.

## Diferenças entre &#39;Longa Cauda&#39; e &#39;Baixo Tráfego&#39;

Nas versões anteriores do Adobe Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento em que eram coletados. Os valores de dimensão foram colocados em &quot;Baixo tráfego&quot; depois que uma dimensão alcançou valores exclusivos de 500K e aplicou uma filtragem mais agressiva em valores exclusivos de 1M. A contagem de valores únicos foi redefinida no início de cada mês do calendário. Os dados processados eram permanentes; não havia como obter os dados existentes do &quot;tráfego baixo&quot;.

No CJA, os valores de dimensão são colocados somente em &#39;Longa Cauda&#39; se um servidor de processamento individual contiver mais de 500K valores únicos. Os dados processados não são permanentes, o que significa que você pode reduzir o valor da dimensão &#39;Longa Cauda&#39; modificando seu relatório.

## Reduza o valor da dimensão &quot;Longa Cauda&quot;

Se você quiser reduzir o valor da dimensão &quot;Longa Cauda&quot;, a Adobe recomenda qualquer uma das seguintes opções:

* Use um segmento. Os segmentos se aplicam no momento em que cada servidor processa um subconjunto de dados. A limitação do número de valores únicos que eles retornam reduz o valor da dimensão &#39;Longa Cauda&#39;.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam valores de dimensão do conjunto de dados de evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contenha mais de 500 mil valores de dimensão únicos. Se você aplicar um segmento ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir a presença de &quot;Longa Cauda&quot; enquanto facilita o consumo do relatório. A Adobe planeja melhorar essa experiência com o desenvolvimento do CJA.
