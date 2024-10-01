---
description: Mostra exemplos de métricas calculadas.
title: Exemplos de métricas calculadas
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Exemplos de métricas calculadas

Este artigo mostra exemplos de como definir métricas calculadas mais avançadas.

## Taxa de rejeição

Você deseja calcular a taxa de rejeição.

+++ Detalhes

A definição de uma rejeição é assunto para outra discussão, mas para este exemplo, você define um filtro de Eventos rejeitados, em que Início da sessão é igual a 1 e Términos de sessão é igual a 1. Use esse filtro para definir a taxa de sessões com rejeição para sessões.


### Filtro

![Rejeitando eventos](assets/example-bounce-bouncedevents.png)

### Métrica calculada

![Taxa de rejeição](assets/example-bounce-rate.png)


### Campos derivados

Como alternativa, você pode definir uma [taxa de rejeição usando campos derivados](/help/data-views/derived-fields/derived-fields.md#bounces).

Os campos derivados fazem parte de uma visualização de dados que tem a vantagem de que nem todos os usuários podem substituir ou modificar a definição de uma métrica de taxa de rejeição. Essa vantagem também introduziu uma limitação. Os usuários que não têm acesso a uma visualização de dados não podem usar campos derivados e precisam recorrer a filtros e métricas calculadas para definir uma taxa de rejeição.

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
