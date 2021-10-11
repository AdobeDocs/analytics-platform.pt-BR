---
title: Operadores de filtro
description: Determine como um componente interage com um valor em um filtro.
source-git-commit: 1334e1edb36583ba978936fecbff2657e63a94bf
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 20%

---

# Operadores de filtro

O Construtor de filtros permite comparar e restringir valores com operadores selecionados. Há duas categorias de operadores: [!UICONTROL Padrão] e [!UICONTROL Contagem distinta].

## Operadores padrão

| Operador | Descrição |
| igual | Retorna itens que correspondem exatamente a um valor numérico ou de string. Se estiver usando caracteres curingas, use operador &quot;corresponde&quot;. |
| não é igual | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Se estiver usando caracteres curingas, use operador &quot;não correspondente&quot;. |
| contém | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se a regra de uma dimensão de string contiver `"Search"`, ela corresponderá a qualquer página que tenha a subsequência `"Search"` nela, incluindo `"Search Results"`, `"Search"` e `"Searching"`. Esse operador diferencia maiúsculas e minúsculas. |
| não contém | Todos os itens que correspondem ao valor inserido são excluídos dos resultados. Por exemplo, se a regra de uma dimensão de string não contiver `"Search"`, ela excluirá qualquer página que tenha a substring `"Search"` nela, incluindo `"Search Results"`, `"Search"` e `"Searching"`. |
| contém todos os | Retorna itens que incluem todas as subsequências (separadas por um espaço) em qualquer ordem. Por exemplo, inserir `"Search Results"` com esse operador corresponderia `"Search Results"` e `"Results of Search"`, mas não `"Search"` ou `"Results"` independentemente. Esse operador suporta até 100 palavras delimitadas por espaços. |
| não contém todos os | Todos os itens que correspondem a cada valor inserido são excluídos dos resultados. Por exemplo, inserir `"Search Results"` com esse operador excluiria `"Search Results"` e `"Results of Search"`, mas não `"Search"` ou `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| contém qualquer um dos | Retorna itens que contêm qualquer uma das subsequências de caracteres especificadas. Por exemplo, inserir `"Search Results"` com esse operador corresponderia a `"Search Results"`, `"Results of Search"`, `"Search"` e `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| não contém nenhum de | Todos os itens que correspondem a qualquer subsequência de caracteres são excluídos dos resultados. Por exemplo, inserir `"Search Results"` excluiria `"Search Results"`, `"Results of Search"`, `"Search"` e `"Results"`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| começa com | Retorna itens que iniciam com o caractere ou as sequências de caracteres do valor inserido. |
| não inicia com | Retorna todos os itens que não iniciam com os caracteres ou as sequências de caracteres dos valores inseridos. |
| termina com | Retorna itens que terminam com o caractere ou as sequências de caracteres do valor inserido. |
| não termina com | Retorna todos os itens que não terminam com os caracteres ou as sequências de caracteres do valor inserido. |
| fósforos | Retorna itens que correspondem exatamente com base em um determinado valor numérico ou de string. Suporta curingas usando um asterisco (`*`). Esse operador diferencia maiúsculas de minúsculas. Por exemplo:<ul><li>`a*e` corresponde  `ae`,  `abcde`,  `adobe`, e  `a whole sentence`.</li><li>`adob*` corresponde  `adobe`,  `adobe analytics`e  `adobo recipe`</li><li>`*dobe` corresponde  `dobe`,  `adobe`, e  `cute little dobe`.</li></ul>|
| não corresponde | Todos os itens que correspondem à sequência de caracteres são excluídos. Suporta curingas usando um asterisco (`*`). |
| existe | Retorna itens se o valor não for nulo. |
| não existe | Retorna itens se o valor for nulo. |

## Operadores de contagem distinta

É possível segmentar em uma contagem distinta de itens em uma dimensão. Por exemplo, você pode criar filtros para visitantes que visualizaram mais de 5 produtos ou visitas distintas, onde mais de 5 páginas distintas foram visualizadas.

| Operador | Descrição |
| --- | --- |
| igual a | Retorna itens de dimensão cuja contagem específica é igual ao valor inserido. |
| não é igual | Retorna itens de dimensão cuja contagem específica não é igual ao valor inserido. |
| é maior que | Retorna itens de dimensão cuja contagem específica é superior ao valor inserido. |
| é menor que | Retorna itens de dimensão cuja contagem específica é inferior ao valor inserido. |
| é maior que ou igual a | Retorna itens de dimensão cuja contagem específica é superior ou igual ao valor inserido. |
| é menor que ou igual a | Retorna itens de dimensão cuja contagem específica é inferior ou igual ao valor inserido. |
