---
title: Usar CJA com matrizes de objetos
description: Entenda como o CJA relata sobre hierarquias de dados.
translation-type: tm+mt
source-git-commit: b7cd74f3fe2f0222e78452f58a7c387f6e0c86d2
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Usar CJA com matrizes de objetos

Alguns schemas da plataforma podem ter matrizes de objetos. Um dos exemplos mais comuns seria um carrinho de compras, que contém vários produtos. Cada produto tem um nome, SKU, categoria, preço, quantidade e qualquer outra dimensão que você deseja rastrear. Todas essas facetas têm requisitos separados, mas todos devem se encaixar na mesma ocorrência.

Em versões anteriores do Adobe Analytics, esse feito foi realizado usando a `products` variável. Era uma string concatenada separada por ponto-e-vírgula (`;`) para separar facetas de um produto, enquanto vírgulas (`,`) delineavam produtos. Era a única variável com suporte limitado a &quot;arrays de objetos&quot;. Variáveis de vários valores, como listas vars, podem suportar o equivalente de arrays, mas não podem suportar &quot;arrays de objetos&quot;. O CJA amplia esse conceito ao suportar arbitrariamente hierarquias profundas em uma única linha de dados, um recurso indisponível em qualquer versão anterior do Adobe Analytics.

## Mesmo exemplo de ocorrência

A seguinte ocorrência é um objeto JSON que representa uma compra feita por um cliente de uma máquina de lavar e secador.

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

Ao criar uma visualização de dados, as seguintes dimensões e métricas estão disponíveis (com base no schema):

* **Dimensões:**
   * ID
   * produto : SKU
   * produto : name
   * produto : order_id
   * produto : garantia : cobertura
   * produto : garantia : comprimento
   * produto : garantia : name
   * produto : garantia : type
* **Métricas:**
   * produto : ordens
   * produto : unidades
   * produto : receita
   * produto : garantia
   * produto : garantia : receita

### Exemplos de ocorrências idênticas (comportamento do relatórios)

Usando apenas a ocorrência acima, as tabelas a seguir mostram os relatórios da Workspace com algumas combinações de dimensão e métrica.

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

Se você quiser relatar apenas a receita da garantia, seu projeto terá a seguinte aparência:

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

Como o secador não incluiu uma garantia, ela não está incluída na tabela.

Como é possível combinar qualquer dimensão com qualquer métrica, a tabela a seguir mostra como os dados seriam usados com valores de dimensão não especificados:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Um pedido de produto existe sem um nome de garantia vinculado a ele, portanto, o valor da dimensão atribui a &#39;Não especificado&#39;. A mesma situação também se aplica ao pedido de garantia do produto:

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
