---
description: Mostra exemplos de métricas calculadas.
title: Exemplos de métricas calculadas
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---

# Exemplos de métricas calculadas

Este artigo mostra exemplos de como definir métricas calculadas mais avançadas.

## Taxa de rejeição

Você deseja calcular a taxa de rejeição.

+++ Detalhes

A definição de uma rejeição é assunto para outra discussão, mas, para este exemplo, você define um segmento de eventos com rejeição, em que Início da sessão é igual a 1 e Términos de sessão é igual a 1. Esse segmento é usado para definir a taxa de sessões com rejeição para sessões.


### Segmento

![Rejeitando eventos](assets/example-bounce-bouncedevents.png)

### Métrica calculada

![Taxa de rejeição](assets/example-bounce-rate.png)


### Campos derivados

Como alternativa, você pode definir uma [taxa de rejeição usando campos derivados](/help/data-views/derived-fields/derived-fields.md#bounces).

Os campos derivados fazem parte de uma visualização de dados que tem a vantagem de que nem todos os usuários podem substituir ou modificar a definição de uma métrica de taxa de rejeição. Essa vantagem também introduziu uma limitação. Os usuários que não têm acesso a uma visualização de dados não podem usar campos derivados e precisam recorrer a segmentos e métricas calculadas para definir uma taxa de rejeição.

Consulte para obter mais informações sobre como calcular rejeições e taxa de rejeição no Customer Journey Analytics, esta [publicação do blog](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446).

+++


## Exibições de página condicionais

Você deseja definir uma métrica calculada que calcula apenas as exibições de página das páginas que foram visitadas em mais de 100 sessões.

+++ Detalhes 

![Exibições de página condicionais](assets/conditional-page-views.png)

+++

## Exibições de página para as 30% principais sessões

Você deseja definir uma métrica calculada que calcula apenas as exibições de página das 30% principais sessões.

+++ Detalhes

![Principais 30% de exibições de página](assets/top30-page-views.png)

+++
