---
title: Uso de arrays de objetos
description: Entenda como o CJA cria relatórios sobre hierarquias de dados.
translation-type: tm+mt
source-git-commit: 6229c5bb08f6f153c625932ed06e85030bc08c5a
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 100%

---


# Uso de arrays de objetos

Alguns esquemas da plataforma podem ter arrays de objetos. Um dos exemplos mais comuns seria um carrinho de compras, que contém vários produtos. Cada produto tem um nome, SKU, categoria, preço, quantidade e qualquer outra dimensão que você quiser rastrear. Todas essas facetas têm requisitos separados, mas todos devem se encaixar na mesma ocorrência.

Em versões anteriores do Adobe Analytics, esse recurso era realizado usando a variável `products`. Era uma string concatenada separada por ponto-e-vírgula (`;`) para separar facetas de um produto, enquanto vírgulas (`,`) delineavam produtos. Era a única variável com suporte limitado a &quot;arrays de objetos&quot;. Variáveis multivalor, como variáveis de listas, podem oferecer suporte ao equivalente a arrays, mas não a &quot;arrays de objetos&quot;. O CJA amplia esse conceito ao oferecer suporte arbitrariamente a hierarquias profundas em uma única linha de dados, um recurso indisponível em qualquer versão anterior do Adobe Analytics.

## Mesmo exemplo de ocorrência

A seguinte ocorrência é um objeto JSON que representa uma compra feita por um cliente de uma máquina de lavar e secar.

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
   * produto : SKU
   * produto : nome
   * produto : order_id
   * produto : garantia : cobertura
   * produto : garantia : comprimento
   * produto : garantia : nome
   * produto : garantia : tipo
* **Métricas:**
   * produto : ordens
   * produto : unidades
   * produto : receita
   * produto : garantia
   * produto : garantia : receita

### Exemplos de ocorrências idênticas (comportamento do relatório)

Usando apenas a ocorrência acima, as tabelas a seguir mostram os relatórios do Workspace com algumas combinações de dimensão e métrica.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

O CJA observa seletivamente a dimensão e as métricas do objeto com base na tabela.

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

O CJA observa essas partes da ocorrência para gerar o relatório:

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

O CJA não combina nativamente métricas com nomes semelhantes se estiverem em níveis de objeto diferentes.

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
