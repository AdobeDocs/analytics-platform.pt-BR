---
title: Uso de dimensões e métricas de vinculação no CJA
description: Atribua dimensões a arrays de objetos para análise de persistência complexa.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 2%

---

# Uso de dimensões e métricas de vinculação no CJA

O Customer Journey Analytics oferece várias maneiras de persistir valores de dimensão além da ocorrência em que estão definidos. Um dos métodos de persistência que o Adobe oferece é conhecido como Vínculo. Em versões anteriores do Adobe Analytics, esse conceito era conhecido como merchandising.

Embora você possa usar dimensões de vínculo com dados de evento de nível superior, esse conceito é melhor usado ao trabalhar com [Matrizes de objetos](object-arrays.md). Você pode atribuir uma dimensão a uma parte de uma matriz de objetos sem aplicá-la a todos os atributos em um determinado evento. Por exemplo, você pode atribuir um termo de pesquisa a um produto na matriz de objetos do carrinho de compras sem vincular esse termo de pesquisa ao evento inteiro.

## Exemplo 1: Usar dimensões de vínculo para atribuir atributos de produto adicionais a uma compra

É possível vincular itens de dimensão em uma matriz de objetos a outra dimensão. Quando o item de dimensão vinculado é exibido, o CJA recupera a dimensão vinculada e a inclui no evento para você. Considere a seguinte jornada do cliente:

1. Um visitante exibe a página de um produto em uma máquina de lavar.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. O visitante então visualiza uma página de produto em uma secadora.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. Em última análise, fazem uma compra. A cor de cada produto não foi incluída no evento de compra.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Se você quiser observar a receita por cor sem uma dimensão de vínculo, a dimensão `product.color` persiste e atribui incorretamente o crédito à cor do secador:

| product.color | Receita |
| --- | --- |
| neon - laranja | 2099 |

Você pode acessar o Gerenciador de visualização de dados e vincular a cor do produto ao nome do produto:

![Dimensão de ligação](assets/binding-dimension.png)

Ao definir esse modelo de persistência, o Adobe anota o nome do produto sempre que a cor do produto é definida. Quando ele reconhece o mesmo nome de produto em um evento subsequente para esse visitante, a cor de produto também é trazida. Os mesmos dados quando você vincula a cor do produto ao nome do produto são semelhantes ao seguinte:

| product.color | Receita |
| --- | --- |
| branco | 1600 |
| neon - laranja | 499 |

## Exemplo 2: Usar métricas vinculativas para vincular termo de pesquisa a uma compra de produto

Um dos métodos de comercialização mais comuns no Adobe Analytics foi vincular um termo de pesquisa a um produto para que cada termo de pesquisa receba crédito pelo produto apropriado. Considere a seguinte jornada do cliente:

1. Um visitante chega ao seu site e procura por &quot;luvas de boxe&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. Eles encontram um par de luvas de que gostam, e o adicionam ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. O visitante então procura por &quot;raquete de tênis&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. Eles encontram uma raquete que gostam e a adicionam ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. O visitante pesquisa por &quot;sapatos&quot; uma terceira vez.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Eles encontram um par de sapatos de que gostam e o adicionam ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. O visitante passa pelo processo de finalização e compra esses três itens.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

Se você usar um modelo de alocação tradicional com termo de pesquisa, os três produtos atribuirão receita a apenas um único termo de pesquisa. Por exemplo, se você usou a primeira alocação com a dimensão do termo de pesquisa:

| search_term | Receita |
| --- | --- |
| luvas de boxe | US$ 204,97 |

Se você tiver usado a última alocação com a dimensão do termo de pesquisa, os três produtos ainda atribuirão receita a um único termo de pesquisa:

| search_term | Receita |
| --- | --- |
| sapatos | US$ 204,97 |

Embora este exemplo inclua apenas um visitante, muitos visitantes que pesquisam por coisas diferentes podem atribuir termos de pesquisa a produtos diferentes, tornando difícil determinar quais são os melhores resultados de pesquisa.

Com uma dimensão de vínculo, o Adobe anota o item de dimensão ao qual está vinculado. Quando o mesmo valor de vínculo é visto em um evento subsequente, ele traz o item de dimensão para que você possa atribuir a métrica desejada a ele. Neste exemplo, podemos definir a dimensão de vínculo para search_term como nome do produto. Quando definimos essa dimensão no Gerenciador de visualizações de dados, também precisamos definir uma métrica de vínculo, pois a dimensão de vínculo está em uma matriz de objetos. Uma métrica de vínculo atua como um acionador de uma dimensão de vínculo, de modo que se vincula apenas aos eventos em que a métrica de vínculo está presente. Neste exemplo de implementação, a página de resultados da pesquisa sempre inclui uma dimensão de termo de pesquisa e uma métrica de pesquisas. Podemos vincular termos de pesquisa ao nome do produto sempre que a métrica Pesquisas estiver presente.

![Métrica de vínculo](assets/binding-metric.png)

Definir a dimensão do termo de pesquisa para esse modelo de persistência executa a seguinte lógica:

* Quando search_term estiver em um evento, verifique a presença do nome do produto.
* Se o nome do produto não estiver lá, não faça nada.
* Se o nome do produto estiver lá, verifique a presença da métrica Pesquisas.
* Se a métrica Pesquisas não estiver lá, não faça nada.
* Se a métrica Pesquisas estiver lá, vincule o termo de pesquisa a todos os nomes de produtos. Funciona como se estivesse no mesmo nível que o nome do produto para esse evento. Neste exemplo, ele é tratado como product.search_term.
* Se o mesmo nome de produto for visualizado em um evento subsequente, o termo de pesquisa vinculado também existe lá.

No Analysis Workspace, o relatório resultante seria semelhante ao seguinte:

| search_term | Receita |
| --- | --- |
| luvas de boxe | 89,99 $ |
| raquete de tênis | US$ 34,99 |
| sapatos | 79,99 $ |
