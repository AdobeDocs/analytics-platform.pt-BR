---
title: Entender sub-eventos e arrays de objetos nos feeds de dados
description: Saiba como os feeds de dados do Customer Journey Analytics exportam subeventos de matrizes de esquema, preservando a hierarquia em vez de nivelá-los como faz o Workspace.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# Sub-eventos em feeds de dados

{{release-limited-testing}}

[Sub-eventos](/help/components/segments/sub-event.md) no Customer Journey Analytics permitem analisar dados do evento em um nível mais granular do que o nível do evento.

Use as informações a seguir para entender como trabalhar com subeventos nos feeds de dados do Customer Journey Analytics.

## Entender os sub-eventos

### Sub-eventos no esquema XDM

No esquema XDM, cada elemento de uma matriz (uma matriz de cadeia de caracteres ou uma matriz de objetos) é um sub-evento.

Para exibir um evento com subeventos no esquema XDM na Adobe Experience Platform, selecione [!UICONTROL **Esquemas**] e expanda um evento que contenha subeventos.

No exemplo a seguir, `Product list items` é uma matriz de objetos contendo vários sub-eventos.

![Esquema XDM contendo uma matriz de objetos e subeventos](assets/df-sub-event-schema.png)

### Exemplo de sub-evento: Produtos em um evento de compra

Um cliente adquire dois produtos em um único pedido: uma furadeira sem fio e duas baterias de furadeira. Sua implementação envia um único evento de compra que inclui ambos os produtos na matriz de objetos `productListItems`:

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

Este evento contém dois sub-eventos, um para cada objeto na matriz `productListItems`. A tabela a seguir mostra quais campos pertencem ao evento e quais pertencem a seus sub-eventos.

| Nível | Campos | O que os campos descrevem |
| --- | --- | --- |
| **Evento** | `eventType`, `timestamp`, `commerce.purchases.value` | A compra como um todo. Cada campo tem um valor para o evento. A métrica **Pedidos** conta `1` para este evento, independentemente de quantos produtos ela contém. |
| **Subevento** | `SKU`, `name`, `quantity`, `priceTotal` em cada objeto `productListItems` | Um produto individual na compra. Cada campo tem um valor por produto. Por exemplo, `quantity` é `1` para a análise sem fio e `2` para a análise de bateria. |

{style="table-layout:auto"}

>[!NOTE]
>
>Os sub-eventos incluem apenas os dados enviados com o evento. A Customer Journey Analytics não reconstrói o conteúdo do carrinho de eventos anteriores, como inclusões ou check-outs do carrinho. Para que os produtos apareçam como subeventos de um evento de compra, sua implementação deve incluí-los em `productListItems` nesse evento de compra.

## Adicionar dados de subeventos a um feed de dados

Quando você tenta adicionar uma coluna que é um sub-evento ao criar um feed de dados, uma caixa de diálogo é exibida solicitando que você adicione qualquer um dos sub-eventos do par. Na saída do feed de dados, todos esses eventos aparecem em uma única coluna.

## Exibir dados de subeventos na saída do feed de dados

### Diferenças de sub-eventos entre o Analysis Workspace e os feeds de dados

Os sub-eventos são representados de forma diferente entre o Analysis Workspace e os feeds de dados no Customer Journey Analytics.

| Localização | Como os sub-eventos são representados |
| --- | --- |
| **Analysis Workspace (no Customer Journey Analytics)** | Selecionáveis como componentes individuais, separados de qualquer hierarquia visível. |
| **Feeds de dados (no Customer Journey Analytics)** | Representado como um grupo, com a hierarquia intacta. |

### Diferenças de sub-eventos entre o Adobe Analytics e o Customer Journey Analytics

Os dados de subeventos (como vários detalhes do produto em um único evento de compra) são exibidos de forma diferente nos feeds de dados do Customer Journey Analytics e nos feeds de dados do Adobe Analytics. A tabela a seguir compara como cada produto representa dados de subeventos.

| Produto | Como os dados de subeventos aparecem nos feeds de dados | Exemplo: lista de produtos |
| --- | --- | --- |
| **Adobe Analytics** | Nivelado em uma string delimitada em uma única coluna. | Uma lista de produtos contém vários produtos agrupados em uma única sequência:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Os sub-eventos retêm a hierarquia definida no esquema XDM. Embora agrupados na mesma coluna, eles mostram sua hierarquia relacional para o evento principal e os sub-eventos irmãos. | Uma lista de produtos mantém sua hierarquia que é definida no esquema XDM como uma matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Diferenças do Adobe Analytics

### Como a saída difere entre os feeds de dados do Adobe Analytics e do Customer Journey Analytics

Os dados de subeventos (como vários detalhes do produto em um único evento de compra) são exibidos de forma diferente nos feeds de dados do Customer Journey Analytics e nos feeds de dados do Adobe Analytics. A tabela a seguir compara como cada produto representa dados de subeventos.

| Produto | Como os dados de subeventos aparecem nos feeds de dados | Exemplo: lista de produtos |
| --- | --- | --- |
| **Adobe Analytics** | Nivelado em uma string delimitada em uma única coluna. | Uma lista de produtos contém vários produtos agrupados em uma única sequência:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Os sub-eventos retêm a hierarquia definida no esquema XDM. Embora agrupados na mesma coluna, eles mostram sua hierarquia relacional para o evento principal e os sub-eventos irmãos. | Uma lista de produtos mantém sua hierarquia que é definida no esquema XDM como uma matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Como os sub-eventos diferem entre a saída do Analysis Workspace e dos feeds de dados

Os sub-eventos são representados de forma diferente entre o Analysis Workspace e os feeds de dados no Customer Journey Analytics.

| Localização | Como os sub-eventos são representados |
| --- | --- |
| **Analysis Workspace** | Selecionáveis como componentes individuais, separados de qualquer hierarquia visível. |
| **Feeds de dados** | Representado como um grupo, com a hierarquia intacta. |


## Exibir dados de subeventos na saída do feed de dados

Os dados de subeventos (como vários detalhes do produto em um único evento de compra) são exibidos de forma diferente nos feeds de dados do Customer Journey Analytics e nos feeds de dados do Adobe Analytics. A tabela a seguir compara como cada produto representa dados de subeventos.

| Produto | Como os dados de subeventos aparecem nos feeds de dados | Exemplo: lista de produtos |
| --- | --- | --- |
| **Adobe Analytics** | Nivelado em uma string delimitada em uma única coluna. | Uma lista de produtos contém vários produtos agrupados em uma única sequência:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Os sub-eventos retêm a hierarquia definida no esquema XDM. Embora agrupados na mesma coluna, eles mostram sua hierarquia relacional para o evento principal e os sub-eventos irmãos. | Uma lista de produtos mantém sua hierarquia que é definida no esquema XDM como uma matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Consultar dados de subeventos na saída do feed de dados

Como os dados de subeventos [aparecem de forma diferente nos feeds de dados do Customer Journey Analytics](#view-sub-event-data-in-data-feed-output), as consultas usadas para eles são diferentes daquelas usadas para os feeds de dados do Adobe Analytics.

Os exemplos a seguir mostram como localizar eventos que incluem um produto específico. Os exemplos usam a sintaxe do Google BigQuery. Outros data warehouses, como Snowflake e Databricks, oferecem suporte à mesma abordagem com pequenas diferenças de sintaxe.

+++ Consultar dados do produto nos feeds de dados do Customer Journey Analytics

Nos feeds de dados do Customer Journey Analytics, os mesmos dois produtos aparecem como uma matriz de objetos na coluna `product_list_items`. Nenhuma análise de delimitador é necessária:

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

A forma como você grava a consulta depende de se você deseja uma linha por evento ou uma linha por produto correspondente.

**Retornar uma linha por evento**

Para filtrar eventos sem alterar o número de linhas, use `UNNEST` dentro de uma subconsulta `EXISTS`:

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

Esta consulta retorna uma linha para cada evento correspondente, com a matriz `product_list_items` completa intacta, independentemente de quantos produtos na matriz sejam correspondentes.

**Retornar uma linha por produto correspondente**

Para retornar uma linha para cada produto correspondente, mova `UNNEST` para a cláusula `FROM` externa:

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

Um evento com mais de um produto correspondente aparece como várias linhas, e as colunas do evento, como `row_id`, se repetem em cada linha. Use essa abordagem somente quando precisar de detalhes no nível do produto. Para contar eventos nos resultados, use `COUNT(DISTINCT row_id)` em vez de contar linhas.

Essa abordagem se aplica a qualquer campo de matriz no esquema XDM, não apenas aos produtos.

+++

+++ Consultar dados do produto nos feeds de dados do Adobe Analytics

Nos feeds de dados do Adobe Analytics, um evento com dois produtos comprados juntos aparece como uma única cadeia de caracteres delimitada na coluna `product_list`:

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

Para localizar eventos que incluem uma Análise sem Fio, analise essa string com uma expressão regular:

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++






