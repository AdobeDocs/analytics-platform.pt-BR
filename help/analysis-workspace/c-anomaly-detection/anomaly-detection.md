---
description: Saiba mais sobre a detecção de anomalias de dados no Analysis Workspace.
title: Visão geral da Detecção de anomalias
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 41%

---

# Visão geral da Detecção de anomalias

Você pode ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Tutorial em vídeo sobre a Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=pt-BR) (4:53)

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, permite identificar quais flutuações estatísticas são relevantes ou não. Em seguida, você pode identificar a causa raiz de uma anomalia verdadeira. Além disso, você pode obter previsões de métricas confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor médio de pedido
* Picos em pedidos com baixa receita
* Picos ou quedas nos registros de avaliação
* Quedas nas exibições da página de aterrissagem
* Picos em eventos de buffer de vídeo
* Picos em taxas de bits de vídeo baixas

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Suporte para granularidade por hora, semana e mês, além da granularidade diária existente.
* Consciência da sazonalidade (como &quot;Black Friday&quot;) e feriados.
