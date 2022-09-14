---
description: Permite visualizar facilmente os dados de comparação no Analysis Workspace, como criar comparações com o mês passado, o ano passado e assim por diante.
title: Visualização de gráficos de combinação
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 5aee0fcc0ec241d946da4ce97dc01eb6274648aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 33%

---

# Gráfico de combinação

O [!UICONTROL Gráfico de combinação] A visualização facilita a criação rápida de uma visualização de comparação sem precisar criar uma tabela primeiro. Você pode ver tendências facilmente em seus dados em uma combinação de linha/barra.

Use um [!UICONTROL Gráfico de combinação] para:

* Comparar os pedidos desta semana com pedidos ao mesmo tempo do mês passado (e do ano passado) - tudo dentro de alguns cliques.
* Analise e compare várias métricas rapidamente (como [!UICONTROL Visitantes únicos] e [!UICONTROL Receita]) entre si no mesmo gráfico.
* Analise uma métrica em relação a uma função (como [!UICONTROL Média acumulada]) ao longo de um horizonte temporal.

Lembre-se de que é possível:

* Adicionar várias comparações em uma única [!UICONTROL Gráfico de combinação].
* Se você adicionar uma ou mais comparações, elas devem ser do mesmo tipo, como [!UICONTROL Comparação de tempo].
* Você pode adicionar até 5 comparações.
* É possível aplicar até 3 filtros (segmentos) a uma métrica.

## Criar um gráfico de Combinação

1. Na lista suspensa Visualizações , no painel à esquerda, arraste a [!UICONTROL Gráfico de combinação] visualização em um painel em branco.

   ![Criar](assets/combo-chart-build.png)

1. Nas listas suspensas, selecione uma dimensão para o eixo X e uma métrica para o eixo Y.

1. Selecione o tipo de [!UICONTROL Comparação de linhas] você deseja usar.

   | Tipo de comparação de linha | Definição |
   | --- | --- |
   | **[!UICONTROL Comparação de tempo]** | O tipo de comparação mais comum - comparando esse período com 4 semanas atrás, por exemplo. Se você selecionou [!UICONTROL Comparação de tempo], faça uma seleção secundária sobre qual período deseja comparar.<p>![Período](assets/combo-time-period.png) |
   | **[!UICONTROL Função]** | Você poderia apresentar uma função como [!UICONTROL Média] na comparação. Consulte uma lista de funções suportadas abaixo.<p>![Funções](assets/combo-functions.png) |
   | **[!UICONTROL Métrica secundária]** | Você pode, por exemplo, comparar [!UICONTROL Receita] para outra métrica.<p>![Duas métricas](assets/combo-2metrics.png) |

   {style=&quot;table-layout:auto&quot;}

1. Clique em **[!UICONTROL Criar]**.

   A saída será semelhante a esta:

   ![Saída](assets/combo-output.png)

   O período atual é mostrado no gráfico de barras e o período de comparação é representado pelo gráfico de linhas. Os pontos no gráfico de linha são conhecidos como &quot;barras&quot;.

## Funções suportadas

Se você escolher **[!UICONTROL Função]** como [!UICONTROL Tipo de comparação de linha], uma função da métrica escolhida será retornada.

| Função | Definição |
| --- | --- |
| **[!UICONTROL Soma da coluna]** | Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão) |
| **[!UICONTROL Média acumulada]** | Retorna a média das últimas N linhas. |
| **[!UICONTROL Medianiz]** | Retorna a mediana de uma métrica em uma coluna. A mediana é o número presente no meio de um conjunto de números, ou seja, metade dos números apresentam valores maiores ou iguais à mediana e metade são menores ou iguais à mediana. |
| **[!UICONTROL Cumulativo]** | A soma cumulativa de N linhas. |
| **[!UICONTROL Máximo da coluna]** | Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. |
| **[!UICONTROL Média]** | Retorna a média aritmética, ou média, de uma métrica. |
| **[!UICONTROL Mínimo da coluna]** | Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. |

{style=&quot;table-layout:auto&quot;}

Este é um exemplo da média cumulativa da métrica Receita:

![Média acumulada](assets/combo-cumul-avg.png)

Este é um exemplo de um gráfico de combinação com as funções Média cumulativa e Média:

![Duas funções](assets/combo-two-functions.png)

## Configurações do gráfico de combinação

Clique no ícone de engrenagem na parte superior direita de um gráfico de combinação para alterar suas configurações.

![Configurações](assets/combo-settings.png)

| Configuração | Definição |
| --- | --- |
| **[!UICONTROL Tipo de visualização]** | Permite alternar para outro tipo de visualização. |
| **[!UICONTROL Granularidade]** | Para visualizações de tendências, você pode alterar a granularidade de tempo (dia, semana, mês etc.) nesta lista suspensa. |
| **[!UICONTROL Geral]** |  |
| **[!UICONTROL Porcentagens]** | Exibe os valores em porcentagens. |
| **[!UICONTROL Legenda visível]** | Permite ocultar o texto detalhado da legenda para a visualização dos Gráficos de combinação. |
| **[!UICONTROL Limite máximo de itens]** | Reduz o número de itens no eixo X. Se você tiver um grande conjunto de dados, poderá mostrar apenas os primeiros 10 itens (ou qualquer valor que escolher). |
| **[!UICONTROL Sobreposições]** | Mostrar ou ocultar os sinalizadores de barras nas linhas. |
| **[!UICONTROL Eixo]** |  |
| **[!UICONTROL Exibir eixo duplo]** | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). Isso é útil quando métricas projetadas têm magnitudes muito diferentes. A cor do eixo duplo corresponde à cor da tabela, a menos que haja várias comparações. Nesse caso, a cor de todas as comparações é cinza. |
| **[!UICONTROL Normalização]** | Força as métricas para proporções iguais. Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| **[!UICONTROL Mostrar eixo x]** | Exiba o eixo x ou oculte-o. |
| **[!UICONTROL Mostrar eixo y]** | Exiba o eixo y ou oculte-o. |
| **[!UICONTROL Âncora do eixo y em zero]** | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |

{style=&quot;table-layout:auto&quot;}
