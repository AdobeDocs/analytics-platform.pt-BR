---
description: Saiba mais sobre a detecção de anomalias de dados no Analysis Workspace.
title: Como a Detecção de anomalias funciona
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
source-git-commit: 689235eb0b982f4e572282f1c73e4606f9d82b12
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 93%

---

# Visão geral da Detecção de anomalias

Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Tutorial em vídeo sobre a Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=pt-BR) (4:53)

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, ele permite identificar quais flutuações estatísticas importam ou não. Assim, você pode identificar a causa raiz de uma verdadeira anomalia. Além disso, é possível obter previsões de métrica confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com receita baixa
* Picos ou quedas em registros de avaliação
* Quedas em visualizações da página inicial
* Picos em eventos de buffer de vídeo
* Picos em taxas de vídeo baixas

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Oferece suporte para granularidade horária, semanal e mensal, além da granularidade diária existente.
* Oferece conscientização de sazonalidade (como “Black Friday”) e feriados.
