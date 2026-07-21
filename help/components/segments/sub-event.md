---
title: Análise de sub-eventos
description: Saiba como a análise de subeventos permite filtrar produtos individuais ou outros contêineres em um evento no Customer Jornada Analytics, eliminando a sangria de atribuição nos relatórios de produtos.
feature: Segmentation
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 3fcb9c403ace295c1a7e62c21d8bb444a4f9c011
workflow-type: tm+mt
source-wordcount: 636
ht-degree: 9%

---

# Análise de sub-evento

{{release-limited-testing}}

A análise de subeventos permite analisar os dados do evento em um nível mais granular do que o nível do evento. Em vez de filtrar eventos inteiros, você pode segmentar em contêineres individuais dentro de eventos. Por exemplo:

* Segmentação em uma categoria de produto específica sem incluir todos os outros produtos comprados na mesma ordem.
* Segmentação em uma categoria de ativos específica nos dados de análise de conteúdo.
* Segmentação em um canal de mídia específico nos dados de análise de mídia.

No Customer Journey Analytics, você define containers em uma visualização de dados para a qual deseja usar a análise de subeventos. Sem a análise de subeventos, a segmentação em um atributo de item de contêiner retorna todos os eventos, sessões, pessoas, contas (globais) [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, grupos de compras [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, oportunidades [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} ou outros [contêineres](/help/data-views/create-dataview.md#containers-1) definidos por você. O resultado é atribuição incorreta e métricas de receita infladas. A análise de subeventos coloca o filtro em linhas de contêiner individuais em um evento e resolve esses problemas.

Na análise de sub-eventos, a lógica de exclusão se comporta de forma diferente da exclusão padrão no nível do evento em relação ao contêiner. Quando você exclui atributos de item no contêiner, o segmento retorna eventos que **têm itens** no contêiner, mas não correspondem aos seus critérios de exclusão. O segmento não retorna eventos sem itens.


## Exemplo

Você deseja medir a receita somente da categoria de roupas profissionais. Sem a análise de sub-evento, a aplicação de um segmento para trajes profissionais inclui a receita de cada produto em qualquer pedido (evento) que contenha pelo menos um produto com a categoria de trajes profissionais. Com a análise de subeventos, você define o escopo do filtro para o nível do produto e retorna somente a receita para produtos da categoria de trajes profissionais.

Você também deseja medir a receita online de todas as outras categorias, exceto a categoria de trajes profissionais.

>[!BEGINTABS]

>[!TAB Análise de eventos]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Professional Suits]** no contêiner **[!UICONTROL Eventos]**.

![Painel que mostra a segmentação no nível do evento para conjuntos profissionais de categorias de produtos](./assets/product-category-segmentation-events.png)

Como resultado, todos os pedidos contendo pelo menos um **[!UICONTROL Conjuntos profissionais]** **[!UICONTROL product_category]** são considerados, e a receita de outros produtos nesses pedidos é incluída na métrica **[!UICONTROL Receita]**.
Quando você cria relatórios sobre categorias, todos os outros valores para **[!UICONTROL product_category]** são relatados como parte de um pedido que incluía um produto com os **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]**.

>[!TAB Análise de sub-evento]

Você definiu um **[!UICONTROL Detalhes do produto]** [contêiner personalizado](/help/data-views/create-dataview.md#containers) na sua visualização de dados para fins de análise de subeventos em produtos.

![Contêiner de detalhes do produto](assets/product-details-container.png)

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Trajes profissionais]** no contêiner **[!UICONTROL Detalhes do produto]**.

![Painel que mostra a segmentação no nível de subevento para conjuntos profissionais de categorias de produtos](./assets/product-category-segmentation-subevents.png)

Como resultado, todos os pedidos contendo pelo menos **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]** são considerados, e somente a receita de produtos pertencentes a **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]** são incluídos na métrica **[!UICONTROL Receita]**.
Ao relatar categorias, somente os **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]** serão relatados.

>[!TAB Análise de sub-evento (excluir)]

Você definiu um **[!UICONTROL Detalhes do produto]** [contêiner personalizado](/help/data-views/create-dataview.md#containers) na sua visualização de dados para fins de análise de subeventos em produtos.

![Contêiner de detalhes do produto](assets/product-details-container.png)

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Excluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Professional Suits]** no contêiner **[!UICONTROL Detalhes do produto]**.

![Painel que mostra a segmentação no nível de sub-ocorrência para excluir homens da categoria de produto](./assets/product-category-segmentation-subevents-exclude.png)

Para excluir no nível do produto, os eventos que contêm pelo menos um produto são incluídos, então a exclusão no nível do subevento é aplicada dentro desse escopo. Essa exclusão é diferente da exclusão no nível do evento, que exclui todo o evento.

>[!ENDTABS]
