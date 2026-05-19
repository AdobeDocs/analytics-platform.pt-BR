---
title: Usar campos derivados para relatar metas
description: Entenda como você pode usar Campos derivados para relatar metas (metas) em seus projetos do Workspace.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
autotag-review: '2026-05-19T06:55:50.510Z'
TQID: 'https://experienceleague.adobe.com/dTARH-90RV1yHWQX3tqotqum-WizfgFh5mgUeYySI6c'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: f3ca85c1-72de-4df2-97ed-05753cd77c47
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 9%

---

# Usar campos derivados para relatar metas

Este caso de uso descreve como usar a força de campos derivados para definir metas para uma dimensão específica e, em seguida, usar essas metas em seu projeto do Workspace.

Se você não estiver familiarizado com os campos derivados, consulte o [tutorial](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=pt-BR) e a [documentação](/help/data-views/derived-fields/derived-fields.md) para obter uma introdução.


## Definir metas

Para definir metas, crie um novo campo derivado em que você defina explicitamente valores numéricos personalizados direta ou indiretamente usando os valores resultantes das regras anteriores na definição do campo derivado.


### Metas de pedidos mensais de vale-presente

Você deseja definir metas explicitamente para seus pedidos de cartão-presente por quatro meses, de julho de 2023 a outubro de 2023. Para fazer isso:

1. Crie um novo campo derivado com o nome `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Defina valores estáticos, usando uma REGRA CASE WHEN para cada mês, definindo um **[!UICONTROL Valor numérico personalizado]**. Consulte a regra de Metas mensais do produto abaixo.

   ![Metas Mensais Do Produto](assets/goals-derived-field-product-goals-1.png)


### Metas de receita do canal de marketing

Você deseja definir uma meta de receita mensal para cada canal de marketing. Para fazer isso:

1. Crie um novo campo derivado, usando o [Modelo de função de canais de marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) com o nome `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Defina todas as regras para identificar corretamente cada um dos canais de marketing com base em uma combinação das regras URL PARSE e CASE WHEN. Por exemplo:

   ![Definição de regras para o campo derivado de canal de marketing](assets/goals-derived-field-marketing-channel-1.png)

1. Defina explicitamente valores estáticos, representando metas mensais de receita, para os canais de marketing específicos em uma regra CASE WHEN final, definindo um **[!UICONTROL Valor numérico personalizado]**. Consulte a regra [!DNL Monthly Goal] abaixo.

   ![Metas mensais](assets/goals-derived-field-marketing-channel-2.png)



## Usar metas

Para usar metas em seu projeto do Workspace, você usa a funcionalidade de métrica calculada para &quot;normalizar&quot; o campo derivado de volta ao valor estático original. Essa normalização é necessária, pois os valores estáticos definidos para os campos derivados que definem metas são incrementados com cada evento.

### Metas de pedidos mensais de vale-presente

1. Crie um campo de métrica calculada chamado `Monthly Gift Certificate Orders Goal`, definido como:

   ![Meta dos pedidos](assets/calculated-metric-ordersgoals.png)

1. Você pode criar campos calculados adicionais, por exemplo `% of Monthly Gift Certificate Orders Goal`, para mostrar o progresso real em relação às metas, por exemplo:

   ![Porcentagem da meta de pedidos](assets/calculated-metric-ordersgoalspercent.png)

Você pode usar essas métricas calculadas para relatar o progresso em tabelas e visualizações de forma livre. Por exemplo:

![Tabela de forma livre mostrando as metas de receita de marketing](assets/freeform-table-marketing-channel-revenue-goals.png)




### Metas de receita do canal de marketing

1. Crie um campo de métrica calculada chamado `Marketing Channel Revenue Goal`, definido como:

   ![Meta de receita](assets/calculated-metric-revenuegoals.png)

1. Você pode criar campos calculados adicionais, por exemplo `% of Marketing Channel Revenue Goal`, para mostrar o progresso real em relação às metas, por exemplo:

   ![Porcentagem da meta de receita](assets/calculated-metric-revenuegoalspercent.png)

Você pode usar essas métricas calculadas para relatar o progresso em tabelas e visualizações de forma livre. Por exemplo:

![Tabela de forma livre mostrando as metas de receita de marketing](assets/freeform-table-product-order-goals.png)
