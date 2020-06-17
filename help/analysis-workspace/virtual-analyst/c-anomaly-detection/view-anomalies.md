---
description: É possível exibir anomalias em uma tabela ou em um gráfico de linhas.
title: Exibir anomalias no Analysis Workspace
uuid: 270a7ea9-6485-4c83-8220-5a2200bd7200
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 91%

---


# Exibir anomalias no Analysis Workspace

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

É possível exibir anomalias em uma tabela ou em um gráfico de linhas.

## Exibir anomalias em uma tabela {#section_869A87B92B574A38B017A980ED8A29C5}

Em uma Tabela de forma livre da série de tempo, cada linha agora é sinalizada automaticamente com uma interrogação cinza-escuro se uma anomalia de dados foi detectada.

![](assets/anomaly_detected.png)

A linha cinza vertical em cada linha indica o valor esperado. Ao passar o mouse sobre a interrogação, é indicado como a anomalia difere do valor esperado (em + ou - %).

## Exibir anomalias em um gráfico de linhas {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

O gráfico de linhas mostra a faixa de confiança verde-claro com os valores anômalos (pontos brancos).

Ao clicar em um ponto branco, ele ficará verde e exibirá:

* A data de ocorrência da anomalia
* O valor bruto da anomalia
* O valor percentual superior ou inferior ao valor esperado, que é representado pela linha sólida verde.

<!--* The Analyze link to start [Contribution Analysis](/help/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md).-->

![](assets/anomaly_linechart.png)

Se você tiver várias métricas no gráfico de linha, podemos mostrar somente as anomalias e você precisa passar o mouse sobre cada uma delas para ver a faixa de confiança para a métrica.

O intervalo de confiança da Detecção de anomalias não dimensiona automaticamente o eixo Y de uma visualização para tornar potencialmente o gráfico mais legível.

Você tem a opção de permitir o dimensionamento do intervalo de confiança no gráfico. Clique no ícone Configurações (engrenagem) e marque **[!UICONTROL Permitir que a detecção de anomalias dimensione o eixo Y]**.

![](assets/scale-y-axis.png)

