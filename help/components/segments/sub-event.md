---
title: Análise de sub-eventos
description: Saiba como a análise de subeventos permite filtrar produtos individuais ou outros contêineres em um evento no Customer Jornada Analytics, eliminando a sangria de atribuição nos relatórios de produtos.
feature: Segmentation
hold: true
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: c504a631398d14479c9a2b70d9ef43ac88e35704
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 0%

---

# Análise de sub-evento

{{release-limited-testing}}

A análise de subeventos permite analisar os dados do evento em um nível mais granular do que o nível do evento. Em vez de filtrar por todo o evento, você pode segmentar em contêineres individuais dentro de eventos. Por exemplo:

- Segmentação em uma categoria de produto específica sem incluir todos os outros produtos comprados na mesma ordem
- Segmentação em uma categoria de ativos específica nos dados de análise de conteúdo?
- Segmentação em um canal de mídia específico nos dados de análise de mídia.


No Customer Journey Analytics, você define containers em uma visualização de dados para a qual deseja usar a análise de subeventos. Sem a análise de subeventos, a segmentação em um atributo de item de contêiner retorna todos os eventos em que qualquer item em um evento corresponde ao atributo de item do contêiner. O resultado é atribuição incorreta e métricas de receita infladas. A análise de subeventos coloca o filtro em linhas de item individuais em um evento e resolve esses problemas.

Na análise de sub-evento, a lógica de exclusão se comporta de forma diferente da exclusão padrão no nível do evento em relação ao contêiner. Quando você exclui atributos de item no contêiner, o segmento retorna eventos que **têm itens** no contêiner, mas não correspondem aos seus critérios de exclusão. O segmento não retorna um evento sem itens.


## Exemplo

Você deseja medir a receita somente da categoria de roupas profissionais. Sem a análise de sub-evento, a aplicação de um segmento para trajes profissionais inclui a receita de cada produto em qualquer pedido (evento) que contenha pelo menos um produto com a categoria de trajes profissionais. Com a análise de subeventos, você define o escopo do filtro para o nível do produto e retorna somente a receita para produtos da categoria de trajes profissionais.

Você também deseja medir a receita online de todas as outras categorias, exceto a categoria de trajes profissionais.

>[!BEGINTABS]

>[!TAB Análise de eventos]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Professional Suits]** no contêiner **[!UICONTROL Eventos]**.

![Painel que mostra a segmentação no nível do evento para conjuntos profissionais de categorias de produtos](./assets/product-category-segmentation-events.png)

Como resultado, todos os pedidos contendo pelo menos um **[!UICONTROL Conjuntos profissionais]** **[!UICONTROL product_category]** são considerados, e a receita de outros produtos nesses pedidos é incluída na métrica **[!UICONTROL Receita]**.Quando você cria relatórios sobre categorias, todos os outros valores para **[!UICONTROL product_category]** são relatados como parte de um pedido que incluía um produto com os **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]**.

>[!TAB Análise de sub-evento]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Incluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Professional Suits]** no contêiner **[!UICONTROL Produtos]**.

![Painel que mostra a segmentação no nível de subevento para conjuntos profissionais de categorias de produtos](./assets/product-category-segmentation-subevents.png)

Como resultado, todos os pedidos contendo pelo menos **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]** são considerados, e somente a receita de produtos pertencentes a **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL product_category]** são incluídos na métrica **[!UICONTROL Receita]**.Ao relatar categorias, somente os **[!UICONTROL Conjuntos Profissionais]** **[!UICONTROL Rproduct_category]** serão relatados.

>[!TAB Análise de sub-evento (excluir)]

No construtor de segmentação ou como parte de um **[!UICONTROL Segmento rápido]**, você especifica **[!UICONTROL Excluir]** o **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL igual]** **[!UICONTROL Professional Suits]** no contêiner **[!UICONTROL Produtos]**.

![Painel que mostra a segmentação no nível de sub-ocorrência para excluir homens da categoria de produto](./assets/product-category-segmentation-subevents-exclude.png)

Para excluir no nível do produto, os eventos que contêm pelo menos um produto são incluídos, então a exclusão no nível do subevento é aplicada dentro desse escopo. Essa exclusão é diferente da exclusão no nível do evento, que exclui todo o evento.

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
