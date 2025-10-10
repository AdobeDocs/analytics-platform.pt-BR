---
title: Uso de matrizes de objetos
description: Saiba como o Customer Journey Analytics cria relatórios sobre hierarquias de dados.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 61%

---

# Uso de matrizes de objetos

Alguns esquemas da plataforma podem ter matrizes de objetos. A Adobe Customer Journey Analytics oferece suporte à assimilação e aos relatórios de arrays de objetos em dados de evento, pesquisa e perfil. Um dos exemplos mais comuns seria um carrinho de compras, que contém vários produtos. Cada produto tem um nome, SKU, categoria, preço, quantidade e qualquer outra dimensão que você quiser rastrear. Todas essas facetas têm requisitos separados, mas todos devem se encaixar na mesma ocorrência.

Em versões anteriores do Adobe Analytics, esse recurso era realizado usando a variável `products`. Era uma string concatenada separada por ponto-e-vírgula (`;`) para separar facetas de um produto, enquanto vírgulas (`,`) delineavam produtos. Era a única variável com suporte limitado a &quot;matrizes de objetos&quot;. Variáveis multivalor, como variáveis de listas, podem oferecer suporte ao equivalente a matrizes, mas não a &quot;matrizes de objetos&quot;. O Customer Journey Analytics amplia esse conceito ao oferecer suporte arbitrariamente a hierarquias profundas em uma única linha de dados, um recurso indisponível em qualquer versão anterior do Adobe Analytics.

## Mesmo exemplo de evento

O evento a seguir é um objeto JSON que representa uma compra feita por um cliente de uma máquina de lavar e secar.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Ao criar uma visualização de dados, as seguintes dimensões e métricas estão disponíveis (com base no esquema):

* **Dimensões:**
   * ID
   * produto : SKU
   * produto : nome
   * produto : order_id
   * produto : garantia : cobertura
   * produto : garantia : comprimento
   * produto : garantia : nome
   * produto : garantia : tipo
* **Métricas:**
   * produto : ordens
   * produto : unidades
   * produto : receita
   * produto : garantia
   * produto : garantia : receita

### Exemplos de mesmos eventos (comportamento do relatório)

Usando apenas o evento acima, as tabelas a seguir mostram os relatórios do Workspace com algumas combinações de dimensão e métrica.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

O Customer Journey Analytics observa seletivamente a dimensão e as métricas do objeto com base na tabela.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Se você quiser relatar apenas a receita da garantia, o projeto terá a seguinte aparência:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

O Customer Journey Analytics analisa essas partes do evento para gerar o relatório:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Como a secadora não incluiu uma garantia, ela não está na tabela.

Como é possível combinar qualquer dimensão com qualquer métrica, a tabela a seguir mostra como os dados seriam usados com itens de dimensão não especificados:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Um pedido de produto existe sem um nome de garantia vinculado a ele, portanto, o item da dimensão atribui a “Não especificado”. A mesma situação também se aplica ao pedido de garantia do produto:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Observe as ordens que não têm um nome vinculado a elas. Esses são os pedidos atribuídos ao item de dimensão “Não especificado”.

### Combinar métricas

O Customer Journey Analytics não combina nativamente métricas com nomes semelhantes se estiverem em níveis de objeto diferentes.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Entretanto, é possível criar uma métrica calculada que combine as métricas desejadas:

Métrica calculada “Receita total”: `[product : revenue] + [product : warranty : revenue]`

A aplicação dessa métrica calculada exibe os resultados desejados:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |



## Limitações

As limitações se aplicam aos arrays nos dados usados pelo Customer Journey Analytics e modelados como parte de um esquema no Experience Platform. Consulte [Limites do modelo de dados](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-model-limits) e [Limites de tamanho de dados](https://experienceleague.adobe.com/en/docs/experience-platform/profile/guardrails#data-size-limits) nas [Medidas de proteção padrão para dados e segmentação do Perfil do cliente em tempo real](https://experienceleague.adobe.com/pt-br/docs/experience-platform/profile/guardrails).

