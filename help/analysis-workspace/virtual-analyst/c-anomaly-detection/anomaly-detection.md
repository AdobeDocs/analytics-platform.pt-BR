---
description: Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.
title: Visão geral da Detecção de anomalias
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 88%

---


# Visão geral da Detecção de anomalias

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Detecção de anomalias no YouTube](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, ele permite identificar quais flutuações estatísticas importam ou não. Assim, você pode identificar a causa raiz de uma verdadeira anomalia. Além disso, é possível obter previsões de métrica confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com receita baixa
* Picos ou quedas em registros de avaliação
* Quedas em visualizações da página inicial
* Picos em eventos de buffer de vídeo
* Picos em taxas de vídeo baixas

A Detecção de anomalias e a [Análise de contribuição](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) são fluxos de trabalho principais no Analysis Workspace. Você pode executar a Análise de contribuição em relação a qualquer anomalia diária e incorporar o resultado ao projeto do Analysis Workspace.

>[!IMPORTANT]
>
>A Análise de contribuição ainda não está disponível no Customer Journey Analytics.

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Oferece suporte para granularidade horária, semanal e mensal, além da granularidade diária existente.
* Oferece conscientização de sazonalidade (como “Black Friday”) e feriados.

## Desativar a detecção de anomalias

Você pode desativar a detecção de anomalias ao nível da coluna acessando as configurações de coluna e desmarcando **[!UICONTROL Anomalias]**.

![](assets/turnoff_anomalies.png)
