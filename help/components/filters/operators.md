---
title: Operadores de filtro
description: Determinam como um componente interage com um valor em um filtro.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 93%

---

# Operadores de filtro

O construtor de filtros permite que você compare e restrinja valores com os operadores selecionados. Existem duas categorias de operadores: [!UICONTROL Padrão] e [!UICONTROL de Contagem distinta].

## Operadores padrão

| Operador | Descrição |
| --- | --- |
| igual a | Retorna itens que possuem o mesmo valor numérico ou de sequência. Se estiver usando caracteres curingas, use o operador &quot;corresponde&quot;. |
| não é igual | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Se estiver usando caracteres curingas, use o operador &quot;não correspondente&quot;. |
| equivale a qualquer | Retorna quaisquer itens que contenham a correspondência dos valores de substring inseridos, delimitados por vírgula. |
| contém | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se a regra de uma dimensão de sequência de caracteres contiver `"Search"`, ela corresponderá a qualquer página que tenha a subsequência de caracteres `"Search"` nela, incluindo `"Search Results"`, `"Search"` e `"Searching"`. Esse operador diferencia maiúsculas e minúsculas. |
| não contém | Todos os itens que correspondem ao valor inserido são excluídos dos resultados. Por exemplo, se a regra de uma dimensão de sequência de caracteres não contiver `"Search"`, então qualquer página que tenha a subsequência de caracteres `"Search"` nela é excluída, incluindo `"Search Results"`, `"Search"` e `"Searching"`. |
| contém tudo | Retorna itens que incluem todas as subsequências de caracteres (separadas por um espaço) em qualquer ordem. Por exemplo, inserir `"Search Results"` com este operador corresponderia a `"Search Results"` e `"Results of Search"`, mas não a `"Search"` ou `"Results"` independentemente. Esse operador suporta até 100 palavras delimitadas por espaços. |
| não contém todos os | Todos os itens que correspondem a cada valor inserido são excluídos dos resultados. Por exemplo, inserir `"Search Results"` com este operador excluiria `"Search Results"` e `"Results of Search"`, mas não `"Search"` ou `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| contém qualquer um dos | Retorna itens que contêm qualquer uma das subsequências de caracteres especificadas. Por exemplo, inserir `"Search Results"` com este operador corresponderia a `"Search Results"`, `"Results of Search"`, `"Search"` e `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| não contém nenhum de | Todos os itens que correspondem a qualquer subsequência de caracteres são excluídos dos resultados. Por exemplo, inserir `"Search Results"` excluiria `"Search Results"`, `"Results of Search"`, `"Search"` e `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| começa com | Retorna itens que iniciam com o caractere ou sequência de caracteres do valor inserido. |
| não inicia com | Retorna todos os itens que não iniciam com os caracteres ou as sequências de caracteres dos valores inseridos. |
| termina com | Retorna itens que terminam com o caractere ou as sequências de caracteres do valor inserido. |
| não termina com | Retorna todos os itens que não terminam com os caracteres ou a sequência de caracteres do valor inserido. |
| corresponde | Retorna itens correspondentes com base no valor numérico ou de sequência. Suporta curingas usando um asterisco (`*`). Este operador diferencia maiúsculas de minúsculas. Por exemplo:<ul><li>`a*e` corresponde `ae`, `abcde`, `adobe` e `a whole sentence`.</li><li>`adob*` corresponde `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corresponde `dobe`, `adobe` e `cute little dobe`.</li></ul> |
| não corresponde | Todos os itens que correspondem à sequência de caracteres são excluídos. Suporta curingas usando um asterisco (`*`). |
| existe | Retorna itens se o valor não for nulo. |
| não existe | Retorna itens se o valor for nulo. |

## Operadores de contagem distinta

Você pode filtrar por uma contagem distinta de itens em uma dimensão. Por exemplo, você pode criar filtros para pessoas que visualizaram mais de 5 produtos distintos ou visitas nas quais mais de 5 páginas distintas foram visualizadas.

| Operador | Descrição |
| --- | --- |
| igual a | Retorna itens de dimensão cuja contagem específica é igual ao valor inserido. |
| não é igual | Retorna itens de dimensão cuja contagem específica não é igual ao valor inserido. |
| é maior que | Retorna itens de dimensão cuja contagem específica é superior ao valor inserido. |
| é menor que | Retorna itens de dimensão cuja contagem específica é inferior ao valor inserido. |
| é maior que ou igual a | Retorna itens de dimensão cuja contagem específica é superior ou igual ao valor inserido. |
| é menor que ou igual a | Retorna itens de dimensão cuja contagem específica é inferior ou igual ao valor inserido. |
