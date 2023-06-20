---
title: Item de dimensão de Cauda longa
description: Explica o item de dimensão “Cauda longa” e por que ele aparece no relatório.
feature: FAQ
exl-id: 262a219a-315a-4c9b-a400-48cff119d45d
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 26%

---

# Item de dimensão de cauda longa

Ao usar uma dimensão que contém um grande número de valores únicos, às vezes você recebe um aviso que diz **[!UICONTROL Resultados truncados]**.  Isso significa que o Customer Journey Analytics da arquitetura de relatórios usa muitos valores únicos para ser processado com eficiência. Como resultado. removeu os itens que considerava menos importantes.

## Arquitetura de processamento de Customer Journey Analytics e valores únicos

O Customer Journey Analytics processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Quando o servidor terminar o processamento, ele entregará seu subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se qualquer servidor individual agregar um conjunto de resultados que esteja acima de um limite de tamanho, ele truncará os resultados antes de enviá-los de volta. Isso mantém o tráfego e a agregação da rede dentro de limites para permitir relatórios rápidos.  Como ela trunca os resultados apenas com a visualização de seus próprios dados, é possível (embora improvável) que os itens mostrados no Analysis Workspace tenham valores de métrica incorretos.

O servidor escolhe quais itens serão descartados com base na métrica usada para classificação.  Se essa for uma métrica calculada, talvez não seja óbvio como classificá-la e, portanto, os resultados podem ser menos precisos.  Por exemplo, ao calcular &quot;Receita por pessoa&quot;, o valor total da receita e o número total de pessoas são retornados e agregados antes de fazer a divisão. Como resultado, cada nó escolhe quais itens remover, sem realmente saber como seus resultados afetarão a classificação geral.

## Diferenças entre “Cauda longa” e “Tráfego baixo”

Em versões anteriores do Adobe Analytics, uma arquitetura de processamento diferente era usada. Os dados eram processados no momento da coleta. Os itens de dimensão eram colocados como “Tráfego baixo” quando uma dimensão atingia 500.000 valores únicos e uma filtragem mais agressiva era aplicada ao chegar em 1 milhão de valores únicos. A contagem de &quot;Valor único&quot; foi redefinida no início de cada mês. Os dados processados eram permanentes; não havia como obter dados existentes do “Tráfego baixo”.

No Customer Journey Analytics, os itens de dimensão só são truncados se os resultados de um relatório forem muito grandes. Os dados processados não são permanentes, o que significa que você pode reduzir ou eliminar o truncamento modificando seu relatório.

## Reduzir o item de dimensão de “Cauda longa”

Se quiser reduzir o truncamento de &quot;Cauda longa&quot;, o Adobe recomenda qualquer um dos seguintes procedimentos:

* Use um [filtro](/help/components/filters/create-filters.md). Os filtros são aplicados no momento em que cada servidor processa um subconjunto de dados. Limitar o número de valores únicos retornados reduz o truncamento de &quot;Cauda longa&quot;.
* Use uma pesquisa. Se uma pesquisa for usada, os itens que não corresponderem à pesquisa serão truncados primeiro, aumentando a probabilidade de você ver os itens desejados.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.

Em geral, é difícil consumir um relatório que contém muitos itens de dimensão únicos. Se você aplicar um filtro ou uma dimensão de conjunto de dados de pesquisa, poderá reduzir o truncamento de &quot;Cauda longa&quot; enquanto facilita o consumo de seu relatório.
