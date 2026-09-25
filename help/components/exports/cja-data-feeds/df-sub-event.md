---
title: Entender sub-eventos e arrays de objetos nos feeds de dados
description: Saiba como os feeds de dados do Customer Journey Analytics exportam subeventos de matrizes de esquema, preservando a hierarquia em vez de nivelá-los como faz o Workspace.
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# Sub-eventos em feeds de dados

{{release-limited-testing}}

No esquema XDM, qualquer item que seja uma matriz (string ou objeto) é um sub-evento. Os sub-eventos no Customer Journey Analytics são representados em exportações de feed de dados com sua hierarquia.

No Adobe Analytics, os subeventos são representados como uma única coluna.

Use as informações a seguir para entender como trabalhar com subeventos nos feeds de dados do Customer Journey Analytics.

## Sub-eventos no esquema XDM, Workspace e feeds de dados

Você define sub-eventos no esquema XDM, como matrizes de sequência ou matrizes de objeto.

Esses subeventos são representados de forma diferente, dependendo se você os visualiza no Analysis Workspace ou nos feeds de dados.

| Localização | Como os sub-eventos são representados |
| --- | --- |
| **Analysis Workspace** | Objetos individuais em uma matriz de objetos podem ser selecionados como componentes individuais, separados de qualquer hierarquia visível. |
| **Feeds de dados** | Objetos em uma matriz de objetos são representados como um grupo, com sua hierarquia intacta. |

## Adicionar dados de subeventos a um feed de dados

Quando você tenta adicionar uma coluna que é um sub-evento ao criar um feed de dados, uma caixa de diálogo é exibida permitindo adicionar todos os sub-eventos de peer. Todos esses eventos serão exibidos em uma única coluna da saída do feed de dados.

## Exibir dados de subeventos na saída do feed de dados

Os dados de subeventos (como vários produtos em um único evento) são exibidos de forma diferente nos feeds de dados do Customer Journey Analytics e nos feeds de dados do Adobe Analytics. A tabela a seguir compara como cada produto representa dados de subeventos.

| Produto | Como os dados de subeventos aparecem nos feeds de dados | Exemplo: lista de produtos |
| --- | --- | --- |
| **Adobe Analytics** | Nivelado em uma string delimitada em uma única coluna. | Uma lista de produtos contém vários produtos agrupados em uma única sequência:<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Os sub-eventos mantêm a hierarquia definida no esquema XDM. Eles permanecem agrupados na mesma coluna, junto com seu evento principal e seus sub-eventos irmãos. | Uma lista de produtos mantém sua hierarquia que é definida no esquema XDM como uma matriz:<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Consultar dados de subeventos na saída do feed de dados

Como os dados de subeventos [aparecem de forma diferente nos feeds de dados do Customer Journey Analytics](#customer-journey-analytics-vs-adobe-analytics), as consultas usadas para eles são diferentes daquelas usadas para os feeds de dados do Adobe Analytics.

Os exemplos a seguir mostram como localizar eventos que incluem um produto específico. Os exemplos usam a sintaxe do Google BigQuery. Outros data warehouses, como Snowflake e Databricks, oferecem suporte à mesma abordagem com pequenas diferenças de sintaxe.

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






