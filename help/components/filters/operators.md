---
title: Operadores
description: Determine como um componente interage com um valor em um segmento.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# Operadores

O Construtor de segmentos permite que você compare e restrinja valores de componentes usando operadores selecionados. Existem duas categorias de operadores: [[!UICONTROL Padrão]](#standard-operators) e [[!UICONTROL de Contagem distinta]](#distinct-count-operators).

## Operadores padrão

| Operador | Descrição |
| --- | --- |
| **[!UICONTROL igual]** | Retorna itens que possuem o mesmo valor numérico ou de sequência. Se estiver usando caracteres curingas, use o operador corresponde. |
| **[!UICONTROL não é igual]** | Retorna todos os itens que não contêm a correspondência exata do valor inserido.  Se estiver usando caracteres curingas, use operador não correspondente. |
| **[!UICONTROL é igual a qualquer um de]** | Retorna quaisquer itens que contenham a correspondência dos valores de substring inseridos, delimitados por vírgula. |
| **[!UICONTROL contém]** | Retorna itens que se comparam às subsequências de caracteres dos valores inseridos. Por exemplo, se o valor de uma dimensão Nome de página contiver `Search`, esse operador corresponderá a qualquer página que tenha a subsequência de caracteres `Search` em seu nome, incluindo `Search Results`, `Search` e `Searching`. Esse operador diferencia maiúsculas e minúsculas. |
| **[!UICONTROL não contém]** | Todos os itens que correspondem ao valor inserido são excluídos dos resultados. Por exemplo, se o valor de uma dimensão Nome de página não contiver `Search`, esse operador excluirá qualquer página que tenha a subsequência de caracteres `Search` em seu nome, incluindo `Search Results`, `Search` e `Searching`. |
| **[!UICONTROL contém tudo]** | Retorna itens que incluem todas as subsequências de caracteres (separadas por um espaço) em qualquer ordem. Por exemplo, especificar `Search Results` como valor para este operador corresponderia a `Search Results` e `Results of Search`, mas não a `Search` ou `Results` independentemente. Esse operador suporta até 100 palavras delimitadas por espaços. |
| **[!UICONTROL não contém todos os]** | Todos os itens que correspondem a cada valor inserido são excluídos dos resultados. Por exemplo, especificar `Search Results` como valor para este operador excluiria `Search Results` e `Results of Search`, mas não `Search` ou `Results`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| **[!UICONTROL contém qualquer um dos]** | Retorna itens que contêm qualquer uma das subsequências de caracteres especificadas. Por exemplo, especificar `Search Results` como valor para este operador corresponderia a `Search Results`, `Results of Search`, `Search` e `Results`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| **[!UICONTROL não contém nenhum de]** | Todos os itens que correspondem a qualquer subsequência de caracteres são excluídos dos resultados. Por exemplo, especificar `Search Results` como valor para este operador excluiria `Search Results`, `Results of Search`, `Search` e `Results`. Esse operador suporta até 100 palavras delimitadas por espaços. |
| **[!UICONTROL iniciar com]** | Retorna itens que iniciam com o caractere ou as sequências de caracteres do valor especificado. |
| **[!UICONTROL não inicia com]** | Retorna todos os itens que não iniciam com os caracteres ou a sequência de caracteres do valor especificado. |
| **[!UICONTROL termina com]** | Retorna itens que terminam com o caractere ou as sequências de caracteres do valor especificado. |
| **[!UICONTROL não termina com]** | Retorna todos os itens que não terminam com os caracteres ou com a sequência de caracteres do valor especificado. |
| **[!UICONTROL corresponde]** | Retorna itens correspondentes com base no valor numérico ou de sequência. Suporta curingas usando um asterisco (`*`). Este operador diferencia maiúsculas de minúsculas. Por exemplo:<ul><li>`a*e` corresponde `ae`, `abcde`, `adobe` e `a whole sentence`.</li><li>`adob*` corresponde `adobe`, `adobe analytics` e `adobo recipe`</li><li>`*dobe` corresponde `dobe`, `adobe` e `cute little dobe`.</li></ul> |
| **[!UICONTROL não corresponde a]** | Todos os itens que correspondem à sequência de caracteres são excluídos. Suporta curingas usando um asterisco (`*`). |
| **[!UICONTROL existe]** | Retorna itens se o valor não for nulo. |
| **[!UICONTROL não existe]** | Retorna itens se o valor for nulo. |

## Operadores de contagem distinta

É possível segmentar em uma contagem distinta de itens em uma dimensão. Por exemplo, você pode criar segmentos para pessoas que visualizaram mais de 5 produtos distintos ou visitas nas quais mais de 5 páginas distintas foram visualizadas.

| Operador | Descrição |
| --- | --- |
| **[!UICONTROL igual]** | Retorna itens de dimensão cuja contagem específica é igual ao valor inserido. |
| **[!UICONTROL não é igual]** | Retorna itens de dimensão cuja contagem específica não é igual ao valor inserido. |
| **[!UICONTROL é maior que]** | Retorna itens de dimensão cuja contagem específica é superior ao valor inserido. |
| **[!UICONTROL é menor que]** | Retorna itens de dimensão cuja contagem específica é inferior ao valor inserido. |
| **[!UICONTROL é maior que ou igual a]** | Retorna itens de dimensão cuja contagem específica é superior ou igual ao valor inserido. |
| **[!UICONTROL é menor que ou igual a]** | Retorna itens de dimensão cuja contagem específica é inferior ou igual ao valor inserido. |
