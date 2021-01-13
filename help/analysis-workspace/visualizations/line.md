---
description: Use a visualização de linha para descrever conjuntos de dados com tendência (de acordo com o tempo)
title: Linha
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 65%

---


# Linha

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

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar mín/máx]**, você pode sobrepor um rótulo de valor mínimo e máximo para realçar rapidamente os picos e vales em uma métrica. Observação: Os valores min/max são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores dentro de uma dimensão.

![Mostrar mín/máx](assets/min-max-labels.png)

## Mostrar sobreposição de linha de tendência

Em **[!UICONTROL Configurações de visualização]** > **[!UICONTROL Sobreposições]** > **[!UICONTROL Mostrar linha de tendência]**, você pode optar por adicionar uma regressão ou mover a linha de tendência média para a sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados.

>[!TIP]
>
>Recomenda-se que as linhas de tendência sejam aplicadas aos dados que não incluem datas atuais (dados parciais) ou futuras, já que isso distorcerá a linha de tendência. No entanto, se você precisar incluir datas futuras, remova zeros dos dados para evitar inclinações para esses dias. Para fazer isso, vá para a tabela de fonte de dados da visualização, escolha sua coluna de métrica e ative **[!UICONTROL Configurações de coluna]** > **[!UICONTROL Interpretar zero como nenhum valor]**.

![Linha de tendência linear](assets/show-linear-trendline.png)

Todas as tendências do modelo de regressão são são ajustadas usando quadrados mínimos normais:

| Modelo | Descrição |
| --- | --- |
| Linear | Cria uma linha reta de melhor ajuste para conjuntos de dados lineares simples e é útil quando os dados aumentam ou diminuem a uma taxa estável. Equação: `y = a + b * x` |
| Logarítmico | Cria uma linha curva de melhor ajuste e é útil quando a taxa de alteração nos dados aumenta ou diminui rapidamente e, em seguida, nivela. Uma linha de tendência logarítmica pode usar valores negativos e positivos. Equação: `y = a + b * log(x)` |
| Exponencial | Cria uma linha curva e é útil quando os dados aumentam ou caem em taxas constantemente crescentes. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a + e^(b * x)` |
| Potência | Cria uma linha curva e é útil para conjuntos de dados que comparam medidas que aumentam a uma taxa específica. Essa opção não deve ser usada se os dados contiverem valores zero ou negativos. Equação: `y = a * x^b` |
| Quadrático | Encontra o melhor ajuste para um conjunto de dados em forma de parábola (côncavo para cima ou para baixo). Equação: `y = a + b * x + c * x^2` |
| Média móvel | Cria uma linha de tendência suave com base em um conjunto de médias. Também conhecida como média móvel, uma média móvel usa um número específico de pontos de dados (determinado pela seleção de &quot;Períodos&quot;), faz a média deles e usa a média como um ponto na linha. Os exemplos incluem média móvel de 7 dias ou média móvel de 4 semanas. |
