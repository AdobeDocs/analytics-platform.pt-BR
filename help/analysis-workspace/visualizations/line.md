---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (com base no tempo)
title: Linha
feature: Visualizations
exl-id: b68aa8dc-2c96-4c49-8d3c-d94804aab479
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 84%

---

# Linha

>[!NOTE]
>
>A visualização de linha será exibida em breve [legendas inteligentes](/help/analysis-workspace/visualizations/intelligent-captions.md).

A visualização de linha representa as métricas que usam uma linha para mostrar como os valores são alterados em um período. Um gráfico de linha pode ser usado apenas quando o horário for usado como uma dimensão.

![Visualização de linha](assets/line-viz.png)

Clique no ícone de engrenagem na parte superior direita da visualização de linha para acessar as [**Configurações de visualização**](freeform-analysis-visualizations.md) disponíveis. As configurações são categorizadas em:

* **Geral**: configurações comuns em tipos de visualização
* **Eixo**: configurações que afetam o eixo x ou y da visualização de linha
* **Sobreposições**: opções para adicionar contexto adicional à série mostrada na visualização de linha.

![Configurações de visualização](assets/viz-settings-modal.png)

## Alterar granularidade

Uma opção suspensa de granularidade nas [configurações de visualização](freeform-analysis-visualizations.md) permite alterar uma visualização com tendência (por exemplo, linha, barra) de diária para semanal, mensal etc. A granularidade também é atualizada na tabela da fonte de dados.

## Mostrar mín. ou máx.

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar mín/máx]**, você pode sobrepor um rótulo de valor mínimo e máximo para realçar rapidamente os picos e vales em uma métrica. Observação: os valores mín./máx. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão.

![Uma sobreposição com o rótulo de valor mínimo e máximo.](assets/min-max-labels.png)

## Mostrar sobreposição de linha de tendência

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar linha de tendências]**, você pode adicionar uma regressão ou linha de tendência de média móvel à sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados.

>[!TIP]
>
>Recomenda-se que linhas de tendência sejam aplicadas a dados que não incluem hoje (dados parciais) ou datas futuras, pois elas distorcerão a linha de tendência. No entanto, se você precisar incluir datas futuras, remova zeros dos dados para evitar distorções nesses dias. Para fazer isso, vá para a tabela de fonte de dados da visualização, escolha a coluna de métrica e ative **[!UICONTROL Configurações de coluna]** > **[!UICONTROL Interpretar zero como nenhum valor]**.

![Linha de tendência linear](assets/show-linear-trendline.png)

Todas as linhas de tendência do modelo de regressão são ajustadas usando mínimos quadrados comuns:

| Modelo | Descrição |
| --- | --- |
| Linear | Cria uma linha reta de melhor ajuste para conjuntos de dados lineares simples e é útil quando os dados aumentam ou diminuem a uma taxa estável. Equação: `y = a + b * x` |
| Logarítmico | Cria uma linha curva de melhor ajuste e é útil quando a taxa de alteração nos dados aumenta ou diminui rapidamente e, em seguida, nivela. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: `y = a + b * log(x)` |
| Exponencial | Cria uma linha curva e é útil quando os dados aumentam ou caem em taxas constantemente crescentes. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a + e^(b * x)` |
| Potência | Cria uma linha curva e é útil para conjuntos de dados que comparam medidas que aumentam a uma taxa específica. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a * x^b` |
| Quadrático | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncavo para cima ou para baixo). Equação: `y = a + b * x + c * x^2` |
| Média móvel | Cria uma linha de tendências suave com base em um conjunto de médias. Também conhecida como média variável, a média móvel usa um número específico de pontos de dados (determinado por sua seleção de &#39;Períodos&#39;), calcula a média deles e usa a média como um ponto na linha. Os exemplos incluem média móvel de sete dias ou média móvel de quatro semanas. |
