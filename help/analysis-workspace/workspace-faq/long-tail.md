---
title: Item de dimensão de Cauda longa
description: Explica o item de dimensão “Cauda longa” e por que ele aparece no relatório.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '437'
ht-degree: 100%

---

# Item de dimensão de Cauda longa

Se você usar uma dimensão que contém um grande número de valores únicos, às vezes poderá ver um valor no relatório rotulado como **[!UICONTROL Cauda longa]**. Esse item de dimensão significa que a arquitetura de relatórios que o CJA usa continha muitos valores únicos para ser processada.

## Arquitetura de processamento do CJA e valores únicos

O CJA processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Depois de terminar o processamento, ele entrega o subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se qualquer servidor individual, que esteja processando um subconjunto de dados, encontrar mais de 500.000 itens de dimensão únicos, ele retorna os 500.000 itens de dimensão principais de seu próprio subconjunto e, em seguida, retorna o restante como “[!UICONTROL Cauda longa]”. O item de dimensão “[!UICONTROL Cauda longa]”, visto em um relatório do Workspace, é o total agregado de cada valor de um servidor de processamento individual que excedeu 500.000 valores únicos.

## Diferenças entre “Cauda longa” e “Tráfego baixo”

Em versões anteriores do Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento da coleta. Os itens de dimensão eram colocados como “Tráfego baixo” quando uma dimensão atingia 500.000 valores únicos e uma filtragem mais agressiva era aplicada ao chegar em 1 milhão de valores únicos. A contagem de valor único era redefinida no início de cada mês. Os dados processados eram permanentes; não havia como obter dados existentes do “Tráfego baixo”.

No CJA, os itens de dimensão são colocados em “Cauda longa” apenas se um servidor de processamento individual contiver mais de 500.000 valores únicos. Os dados processados não são permanentes, o que significa que você pode reduzir o item de dimensão de “Cauda longa” modificando seu relatório.

## Reduzir o item de dimensão de “Cauda longa”

Se desejar reduzir o item de dimensão de “Cauda longa”, a Adobe recomenda qualquer um dos seguintes métodos:

* Use um [filtro](/help/components/filters/create-filters.md). Os filtros são aplicados no momento em que cada servidor processa um subconjunto de dados. Limitar o número de valores únicos retornados reduz o item de dimensão de “Cauda longa”.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contém mais de 500.000 itens de dimensão únicos. Se você aplicar um filtro ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir a presença de “Cauda longa” enquanto facilita o consumo de seu relatório. A Adobe pretende melhorar essa experiência à medida que o CJA for sendo desenvolvido.
