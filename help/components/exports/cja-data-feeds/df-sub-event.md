---
title: Componentes de subcontêineres de matrizes e mapas em feeds de dados
description: Saiba como os feeds de dados do Customer Journey Analytics exportam componentes de subcontêiner de campos de matriz e mapa e como consultá-los no data warehouse.
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
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%
---
# Componentes de subcontêiner em feeds de dados

{{release-limited-testing}}

Os componentes do subcontêiner são dimensões e métricas baseadas em campos dentro de uma matriz ou mapa no esquema XDM. Eles permitem analisar dados em um nível mais granular do que o nível do evento, como os produtos individuais em uma compra. Para obter informações sobre como usar esses dados em segmentos, consulte [Subeventos](/help/components/segments/sub-event.md).

Use as informações a seguir para entender como os componentes de subcontêiner de campos de matriz e mapa aparecem nos feeds de dados do Customer Journey Analytics.

## Entender os componentes do subcontêiner

### Componentes do subcontêiner no esquema XDM

No esquema XDM, cada elemento de uma matriz (uma matriz de sequência ou uma matriz de objetos) é um subcontêiner. Cada entrada em um campo de mapa também é um subcontêiner, conforme descrito em [Mapear campos em feeds de dados](#map-fields-in-data-feeds). Dimensões e métricas baseadas nos campos em um subcontêiner são componentes do subcontêiner.

Para exibir subcontêineres no esquema XDM na Adobe Experience Platform, selecione [!UICONTROL **Esquemas**] e expanda um evento que contenha subcontêineres.

No exemplo a seguir, `Product list items` é uma matriz de objetos que contém vários componentes de subcontêiner.

![Esquema XDM contendo uma matriz de objetos e componentes de subcontêiner](assets/df-sub-event-schema.png)

### Diferenças de subcontêiner entre o Analysis Workspace e os feeds de dados

Os componentes de subcontêineres são representados de forma diferente entre o Analysis Workspace e os feeds de dados no Customer Journey Analytics.

| Localização | Como os componentes do subcontêiner são representados |
| --- | --- |
| **Analysis Workspace (no Customer Journey Analytics)** | Selecionáveis como componentes individuais, separados de qualquer hierarquia visível. |
| **Feeds de dados (no Customer Journey Analytics)** | Representado como um grupo, com a hierarquia intacta. |

### Diferenças do subcontêiner entre o Adobe Analytics e o Customer Journey Analytics

Os dados de subcontêineres (como vários detalhes do produto em um único evento de compra) são exibidos de forma diferente nos feeds de dados do Customer Journey Analytics e nos feeds de dados do Adobe Analytics. A tabela a seguir compara como cada produto representa os dados de subcontêineres.

| Produto | Como os dados do subcontêiner aparecem nos feeds de dados | Exemplo: lista de produtos |
| --- | --- | --- |
| **Adobe Analytics** | Nivelado em uma string delimitada em uma única coluna. | Uma lista de produtos contém vários produtos agrupados em uma única sequência:<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | Os componentes do subcontêiner retêm a hierarquia definida no esquema XDM. Embora agrupados na mesma coluna, eles mostram sua hierarquia relacional ao evento principal e aos sub-contêineres irmãos. | Uma lista de produtos mantém sua hierarquia que é definida no esquema XDM como uma matriz:<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### Exemplo de subcontêiner: produtos em um evento de compra

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

Este evento contém dois sub-contêineres, um para cada objeto na matriz `productListItems`. A tabela a seguir mostra quais campos pertencem ao evento e quais pertencem aos seus sub-containers.

| Nível | Campos | O que os campos descrevem |
| --- | --- | --- |
| **Evento** | `eventType`, `timestamp`, `commerce.purchases.value` | A compra como um todo. Cada campo tem um valor para o evento. A métrica **Pedidos** conta `1` para este evento, independentemente de quantos produtos ela contém. |
| **Subcontêiner** | `SKU`, `name`, `quantity`, `priceTotal` em cada objeto `productListItems` | Um produto individual na compra. Cada campo tem um valor por produto. Por exemplo, `quantity` é `1` para a análise sem fio e `2` para a análise de bateria. |

{style="table-layout:auto"}

>[!NOTE]
>
>Os sub-contêineres incluem somente os dados enviados com o evento. A Customer Journey Analytics não reconstrói o conteúdo do carrinho de eventos anteriores, como inclusões ou check-outs do carrinho. Para que os produtos apareçam como sub-contêineres de um evento de compra, sua implementação deve incluí-los em `productListItems` nesse evento de compra.

## Adicionar componentes de subcontêiner a um feed de dados

Ao adicionar um componente de subcontêiner a um feed de dados, uma caixa de diálogo solicita que você adicione os outros componentes do mesmo subcontêiner.

![Caixa de diálogo solicitando que você adicione componentes de subcontêiner relacionados](assets/data-feeds-add-subevent.png)

Os campos do mesmo subcontêiner aparecem na tela como um grupo aninhado recolhível em vez de um item simples.

![Grupo de subcontêineres](assets/data-feeds-subevent-added.png)

Esse grupo reflete a estrutura de dados subjacente.

Na saída do feed de dados, todos esses componentes aparecem como uma matriz aninhada em uma única coluna.

Para obter informações sobre como adicionar componentes, incluindo componentes de subcontêiner, a um feed de dados, consulte [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).

## Consultar dados do subcontainer na saída do feed de dados

Como os dados do subcontêiner [aparecem de forma diferente nos feeds de dados do Customer Journey Analytics](#sub-container-differences-between-adobe-analytics-and-customer-journey-analytics), as consultas usadas para eles são diferentes daquelas usadas para os feeds de dados do Adobe Analytics.

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

## Usar campos de mapa em feeds de dados

Os campos de mapa no esquema XDM armazenam pares de valores-chave. Os feeds de dados exportam cada mapa como uma matriz de objetos, da mesma forma que outros [dados de subcontêiner](#query-sub-container-data-in-data-feed-output). Cada objeto contém a chave do mapa e seu valor como campos separados.

Os nomes de campos na saída vêm das IDs de componente configuradas para o feed de dados, não de nomes fixos como `key` ou `value`. Os exemplos nesta seção usam IDs de componente de exemplo.

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### Mapas simples

Mapas simples são o tipo de mapa que você pode criar em seu próprio esquema. Cada chave é uma string e cada valor é uma string ou um número inteiro.

Por exemplo, um mapa de pesquisa armazena cada pergunta como uma chave e a resposta como um valor:

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

Na saída do feed de dados, `survey_question` e `survey_answer` são as IDs de componente para a chave e o valor:

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### Mapa de identidade

Cada identidade no campo [`identityMap`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/profile/identitymap) é exportada como um objeto. O objeto contém o namespace de identidade (a chave), juntamente com o identificador, o estado autenticado e o sinalizador principal. O namespace se repete para cada identidade nesse namespace.

Somente os atributos do mapa de identidade que existem como dimensões em sua visualização de dados e que você adiciona ao feed de dados são exportados.

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### Mapas aninhados

Alguns campos definidos pela Adobe, como `segmentMembership`, são mapas de mapas. Os feeds de dados os nivelam em uma única matriz, com a chave de primeiro nível e a chave de segundo nível como campos separados em cada objeto. A chave de primeiro nível se repete em cada objeto ao qual se aplica, de modo que nenhum dado ou relacionamento é perdido.

Por exemplo, `segment_namespace` e `segment_id` são as IDs de componente para a chave de primeiro nível e a chave de segundo nível:

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








