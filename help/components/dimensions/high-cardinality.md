---
title: Dimension com muito alta cardinalidade em Customer Journey Analytics
description: Descreve as práticas recomendadas para lidar com dimensões de alta cardinalidade no Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 9af5c74164462851ac4a6cbc4764569789f677fc
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---


# Dimension com uma cardinalidade muito alta

O Customer Journey Analytics (CJA) não coloca limites no número de valores únicos ou itens de dimensão que podem ser relatados em uma única dimensão. No entanto, em algumas circunstâncias, dimensões com um número extremamente grande de itens únicos - também conhecidos como dimensões de alta cardinalidade - podem afetar o que pode ser relatado.

## Limitações

Dependendo do número de eventos em uma conexão CJA específica, as duas limitações a seguir podem ocorrer juntamente com dimensões de alta cardinalidade:

### 1. As contagens de linhas podem não ser relatáveis com precisão

As contagens de linhas em dimensões de alta cardinalidade podem não ser exatamente reportáveis. Quando isso acontecer, as tabelas de forma livre fornecerão uma indicação, conforme mostrado abaixo:

![](assets/high-cardinality.png)

### 2. As Métricas calculadas podem usar estimativas para algumas funções e para classificar

Quando usadas com dimensões altamente cardinais, algumas funções de Métrica calculada podem retornar estimativas, incluindo: Máximo da coluna, Mínimo da coluna, Contagem de linhas, Média, Média, Percentual, Quartil, Desvio padrão, Variação, Funções de regressão e Funções T e Z.

Além disso, a classificação de uma coluna de tabela usando uma métrica calculada pode ser baseada em uma estimativa e nem sempre refletir a ordem de classificação exata. Uma mensagem de aviso será exibida para avisá-lo de que estimativas podem ter sido usadas.

Esteja ciente de que, embora as métricas calculadas possam, às vezes, retornar estimativas, os totais da coluna são sempre precisos e nunca se baseiam em estimativas. Da mesma forma, ao usar métricas padrão, as estimativas nunca são usadas e sempre refletem ordens de classificação exatas.

### Onde todos os valores de dimensão são considerados

Embora haja limitações para algumas métricas calculadas e contagens de linhas de dimensão, esteja ciente de que os recursos a seguir sempre consideram todos os valores únicos em qualquer dimensão, independentemente de uma dimensão ser altamente cardinal ou não:

* Atribuição de métrica e alocação de dimensão
* Pesquisas de item de linha aplicadas a uma tabela de forma livre
* Filtros que usam dimensões ou itens de dimensão
* A função distinta da contagem aproximada em Métricas calculadas
* Incluir/excluir lógica aplicada a qualquer métrica ou dimensão em uma Exibição de dados
* Conjuntos de dados de pesquisa adicionados a uma conexão

## Práticas recomendadas para trabalhar com dimensões cardeal

Para eliminar os avisos ou estimativas que podem ocorrer ao usar dimensões com alta cardinalidade, recomendamos que você reduza o número de linhas consideradas em seu relatório usando um dos seguintes métodos:

* Adicione um filtro à coluna ou painel afetado.
* Aplique uma pesquisa à tabela de forma livre.
* Aplique um detalhamento às linhas de interesse ou use a dimensão altamente cardinal como uma dimensão de detalhamento
* Adicione critérios de inclusão/exclusão à configuração da Exibição de dados da dimensão para restringir o número de valores únicos presentes na dimensão.

O uso dessas técnicas geralmente pode eliminar quaisquer estimativas ou avisos indesejáveis que você tenha ao usar dimensões cardeal altas.
