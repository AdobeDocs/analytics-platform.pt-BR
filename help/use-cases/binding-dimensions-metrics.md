---
title: Uso de dimensões e métricas de ligação no CJA
description: Atribua dimensões a arrays de objetos para análise de persistência complexa.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 419279f8e01bc81b17c372c6c53939b81ddbf4b7
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 36%

---

# Uso de dimensões e métricas de ligação no CJA

O Customer Journey Analytics oferece várias maneiras de persistir valores de dimensão além da ocorrência em que estão definidos. Um dos métodos de persistência que a Adobe oferece é conhecido como Ligação. Em versões anteriores do Adobe Analytics, esse conceito era conhecido como merchandising.

Embora você possa usar dimensões de ligação com dados de evento de nível superior, esse conceito é melhor usado ao trabalhar com [Arrays de objetos](object-arrays.md). Você pode atribuir uma dimensão a uma parte de um array de objetos sem aplicá-la a todos os atributos em um determinado evento. Por exemplo, você pode atribuir um termo de pesquisa a um produto no array de objetos do carrinho de compras sem vincular esse termo de pesquisa ao evento inteiro.

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

| product.color | receita |
| --- | --- |
| neon - laranja | 2099 |

Você pode acessar o Gerenciador de visualização de dados e vincular a cor do produto ao nome do produto:

![Dimensão de ligação](assets/binding-dimension.png)

Quando você define esse modelo de persistência, o CJA anota o nome do produto sempre que a cor do produto é definida. Quando ele reconhece o mesmo nome de produto em um evento subsequente para esse visitante, a cor de produto também é trazida. Os mesmos dados quando você vincula a cor do produto ao nome do produto são semelhantes ao seguinte:

| product.color | receita |
| --- | --- |
| branco | 1600 |
| neon - laranja | 499 |

## Exemplo 2: Usar métricas vinculativas para vincular termo de pesquisa a uma compra de produto

Um dos métodos de merchandising mais comuns no Adobe Analytics tem sido o de vincular um termo de pesquisa a um produto para que cada termo de pesquisa receba crédito pelo seu produto apropriado. Considere a seguinte jornada do cliente:

1. Um visitante chega ao seu site e procura por “luvas de boxe”. A métrica de pesquisas é incrementada em um e os três principais resultados de pesquisa são exibidos.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
           },
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Professional gloves",
           }
       ]
   }
   ```

2. Ele encontra um par de luvas que gosta e o adiciona ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           }
       ]
   }
   ```

3. O visitante então procura por “raquete de tênis”. A métrica de pesquisas é incrementada em um e os três principais resultados de pesquisa são exibidos.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Women's open racket",
           },
           {
               "name": "Extreme racket",
           }
       ]
   }
   ```

4. Ele encontra uma raquete que gosta e a adiciona ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           }
       ]
   }
   ```

5. O visitante faz uma terceira pesquisa, por “sapatos”. A métrica de pesquisas é incrementada em um e os três principais resultados de pesquisa são exibidos.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
           },
           {
               "name": "Tennis shoes",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

6. Ele encontra um par de sapatos que gosta e o adiciona ao carrinho.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
           },
           {
               "name": "Shock absorb racket",
           },
           {
               "name": "Skate shoes",
           }
       ]
   }
   ```

7. O visitante passa pelo processo de finalização e compra esses três itens.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "price": "79.99"
           }
       ]
   }
   ```

Se você usar um modelo de alocação que não inclua uma dimensão vinculativa com termo de pesquisa, todos os três produtos atribuirão receita a apenas um único termo de pesquisa. Por exemplo, se você usou a alocação Original com a dimensão do termo de pesquisa:

| search_term | receita |
| --- | --- |
| luvas de boxe | US$ 204,97 |

Se você usou a alocação Mais recente com a dimensão de termo de pesquisa, todos os três produtos ainda atribuirão receita a um único termo de pesquisa:

| search_term | receita |
| --- | --- |
| sapatos | US$ 204,97 |

Embora este exemplo inclua apenas um visitante, muitos visitantes que pesquisam por coisas diferentes podem atribuir erroneamente termos de pesquisa a produtos diferentes, tornando difícil determinar quais são os melhores resultados de pesquisa.

O CJA detecta automaticamente a relação entre a dimensão selecionada e a dimensão de vínculo. Se a dimensão de vínculo estiver em uma matriz de objetos enquanto a dimensão selecionada estiver em um nível superior, será necessária uma métrica de vínculo. Uma métrica de ligação atua como um acionador de uma dimensão de ligação, de modo que se vincula apenas aos eventos em que a métrica de ligação está presente.

Neste exemplo de implementação, a página de resultados da pesquisa sempre inclui uma dimensão de termo de pesquisa e uma métrica de pesquisas. Podemos vincular termos de pesquisa ao nome do produto sempre que a métrica de Pesquisas estiver presente.

![Métrica de ligação](assets/binding-metric.png)

Definir a dimensão do termo de pesquisa para esse modelo de persistência executa a seguinte lógica:

* Quando a dimensão do termo de pesquisa for definida, verifique a presença do nome do produto.
* Se o nome do produto não estiver lá, nada será feito.
* Se o nome do produto estiver lá, será verificada a presença da métrica de Pesquisas.
* Se a métrica de Pesquisas não estiver lá, nada será feito.
* Se a métrica Pesquisas estiver lá, vincule o termo de pesquisa a todos os nomes de produtos nesse evento. Ele se copia para o mesmo nível que o nome do produto para esse evento. Neste exemplo, ele é tratado como product.search_term.
* Se o mesmo nome de produto for visualizado em um evento subsequente, o termo de pesquisa vinculado também será transportado para esse evento.

No Analysis Workspace, o relatório resultante seria semelhante ao seguinte:

| search_term | receita |
| --- | --- |
| luvas de boxe | US$ 89,99 |
| raquete de tênis | US$ 34,99 |
| sapatos | US$ 79,99 |

## Exemplo 3: Vincular termo de pesquisa de vídeo ao perfil do usuário

Você pode vincular um termo de pesquisa a um perfil de usuário, de modo que a persistência entre perfis permaneça completamente separada. Por exemplo, sua organização executa um serviço de transmissão em que uma conta pode ter vários perfis. O visitante tem uma conta filho e uma conta adulta.

1. A conta entra sob a conta da criança e procura por um programa de TV. Observe que a variável `"AccountID"` é `2` para representar o perfil filho.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "Searches": "1",
       "search_term": "kids TV show"
   }
   ```

1. Eles encontram o programa &quot;Orangey&quot; e o tocam para que seus filhos possam vê-lo.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

1. Mais tarde naquela noite, o pai muda para seu perfil e procura por algum novo conteúdo adulto para assistir. Observe que a variável `"AccountID"` é `1` para representar o perfil de adulto. Ambos os perfis pertencem à mesma conta, representados pela mesma `"PersonID"`.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "1",
       "Searches": "1",
       "search_term": "inappropriate adult movie"
   }
   ```

1. Encontre o programa &quot;Game of Dethones&quot; e aproveite a noite assistindo.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "1",
       "ShowName": "Game of Dethrones",
       "VideoStarts": "1"
   }
   ```

1. No dia seguinte, eles continuaram o programa de TV &quot;Orangey&quot; para o filho. Eles não precisam pesquisar, pois já estão cientes do programa.

   ```json
   {
       "PersonID": "7078",
       "AccountID": "2",
       "ShowName": "Orangey",
       "VideoStarts": "1"
   }
   ```

Se você usar um modelo de alocação sem uma dimensão de vínculo, a variável `"inappropriate adult movie"` o termo de busca é atribuído à última exibição do programa de TV do garoto. No entanto, se você vincular `search_term` para `AccountID`, cada pesquisa de perfil seria isolada em seu próprio perfil, atribuída aos programas corretos que ela procura.

## Exemplo 4: Avaliar o comportamento de navegação e pesquisa em uma configuração de varejo

1. Um visitante faz uma pesquisa por `"camera"`. Observe que nenhum produto está definido nesta página.

   ```json
   {
       "search_term": "camera",
       "product_finding_method": "search"
   }
   ```

1. Eles clicam em uma câmera que gostam e a adicionam ao carrinho.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. O visitante então navega na categoria de cintos masculinos sem realizar uma pesquisa. Observe que nenhum produto está definido nesta página.

   ```json
   {
       "category": "Men's belts",
       "product_finding_method": "browse"
   }
   ```

1. Eles clicam na parte desejada e a adicionam ao carrinho.

   ```json
   {
       "Product": [
           {
               "name": "Ratchet belt"
           }
       ],
       "CartAdd": "1"
   }
   ```

1. Eles passam pelo processo de finalização e compram esses dois itens.

   ```json
   {
       "Product": [
           {
               "name": "DSLR Camera",
               "price": "399.99"
           },
           {
               "name": "Ratchet belt",
               "price": "19.99"
           }
       ],
       "Purchase": "1"
   }
   ```

Se a persistência for definida como alocação mais recente sem uma dimensão vinculativa, todos os $419,98 da receita serão atribuídos ao valor `browse` método de descoberta. Se a persistência for definida usando a alocação original sem uma dimensão compulsória, todos os $419,98 da receita serão atribuídos ao `search` método de descoberta.

No entanto, se você vincular `product_finding_method` para a métrica Adições ao carrinho, o relatório resultante atribui cada produto ao método de descoberta correto.

| Método de descoberta do produto | Receita |
| --- | --- |
| pesquisa | 399,99 |
| navegar | 19,99 |
