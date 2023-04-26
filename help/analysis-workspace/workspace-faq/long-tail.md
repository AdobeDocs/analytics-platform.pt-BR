---
title: Item de dimensão de Cauda longa
description: Explica o item de dimensão “Cauda longa” e por que ele aparece no relatório.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: 5603eef365365cea941ba5b261aeb56e58a84236
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 38%

---

# Aviso de truncamento

Ao usar uma dimensão que contém um grande número de valores únicos, às vezes você emite um aviso que diz **[!UICONTROL Resultados truncados]**.  Isso significa que a arquitetura de relatórios que o CJA usa continha muitos valores únicos para ser processada com eficiência e, portanto, removeu os itens que ele achava serem menos importantes.

## Arquitetura de processamento do CJA e valores únicos

O CJA processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Depois de terminar o processamento, ele entrega o subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se um servidor individual agregar um conjunto de resultados que esteja acima de um limite de tamanho, ele truncará os resultados antes de enviá-los de volta.  Isso mantém o tráfego e a agregação da rede com limites para permitir relatórios rápidos.  Como ele trunca os resultados apenas com a visualização dos próprios dados, é possível (mas improvável) que os itens mostrados no Analysis Workspace tenham valores de métrica incorretos.

Ele escolhe quais itens devem ser descartados com base na métrica usada para a classificação.  Se essa for uma métrica calculada, pode não ser óbvio como classificá-la, e portanto os resultados podem ser menos precisos.  Por exemplo, ao calcular a receita por visitante, a quantidade total de receita e o número total de visitantes são retornados e agregados antes de fazer a divisão e, portanto, cada nó escolhe muito quais itens remover sem saber realmente como seus resultados afetarão a classificação geral.

## Diferenças entre “Cauda longa” e “Tráfego baixo”

Em versões anteriores do Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento da coleta. Os itens de dimensão eram colocados como “Tráfego baixo” quando uma dimensão atingia 500.000 valores únicos e uma filtragem mais agressiva era aplicada ao chegar em 1 milhão de valores únicos. A contagem de valor único era redefinida no início de cada mês. Os dados processados eram permanentes; não havia como obter dados existentes do “Tráfego baixo”.

No CJA, os itens de dimensão só são truncados se os resultados de um relatório forem muito grandes. Os dados processados não são permanentes, o que significa que é possível reduzir ou eliminar o truncamento modificando seu relatório.

## Reduzir o item de dimensão de “Cauda longa”

Se quiser reduzir o truncamento &quot;Long Tail&quot;, o Adobe recomenda qualquer um dos seguintes procedimentos:

* Use um [filtro](/help/components/filters/create-filters.md). Os filtros são aplicados no momento em que cada servidor processa um subconjunto de dados. Limitar o número de valores únicos retornados reduz o truncamento de &quot;Cauda longa&quot;.
* Use uma pesquisa.  Se uma pesquisa for usada, esses itens que não correspondem à pesquisa serão truncados primeiro tornando mais provável que você veja os itens desejados.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contém muitos itens de dimensão únicos. Se você aplicar um filtro ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir o truncamento de &quot;Cauda longa&quot;, facilitando o consumo de seu relatório.
