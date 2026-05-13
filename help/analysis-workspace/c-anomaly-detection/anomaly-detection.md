---
description: Saiba mais sobre a detecção de anomalias de dados no Analysis Workspace.
title: Visão geral da Detecção de anomalias
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
TQID: https://experienceleague.adobe.com/beFLMQfzXJUoCbg6fSLpFqcbaB7GSuo6SHroSS6V5wI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: aff2ef09-fc60-4018-9197-e2befd623064
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 83%

---

# Visão geral da Detecção de anomalias

É possível ver e analisar anomalias de dados de forma contextual no Analysis Workspace.

[Tutorial em vídeo sobre a Detecção de anomalias](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=pt-BR) (4:53)

A Detecção de anomalias oferece um método estatístico para determinar como uma certa métrica foi alterada com relação aos dados anteriores.

A Detecção de anomalias permite separar os &quot;sinais verdadeiros&quot; do &quot;barulho&quot; e identificar possíveis fatores que contribuem para os sinais ou as anomalias. Em outras palavras, permite identificar quais flutuações estatísticas são relevantes ou não. Em seguida, você pode identificar a causa raiz de uma anomalia verdadeira. Além disso, você pode obter previsões de métricas confiáveis (KPI).

Exemplos de anomalias que você pode investigar incluem:

* Quedas drásticas no valor diário de pedidos
* Picos em pedidos com baixa receita
* Picos ou quedas em registros de avaliação
* Quedas nas exibições da página de destino
* Picos em eventos de buffer de vídeo
* Picos em taxas de bits de vídeo baixas

O algoritmo de detecção de anomalias do Analysis Workspace inclui

* Suporte para granularidade horária, semanal e mensal, além da granularidade diária já existente.
* Percepção da sazonalidade (como “Black Friday”) e feriados.
