---
title: Configurações do componente de subsequência de caracteres
description: Use um subconjunto de uma string como itens de dimensão.
solution: Customer Journey Analytics
feature: Data Views
exl-id: a763027e-68f7-4f0a-8082-85db5283c8e3
source-git-commit: 0178babcd5ae87b491e849c7517eb5792fb14af1
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 7%

---

# [!UICONTROL Substring] configurações do componente

[!UICONTROL Substring] as configurações do componente permitem executar métodos de manipulação de sequência de caracteres para obter os itens de dimensão desejados nos relatórios.

[!UICONTROL Substring] está disponível somente em dimensões e é retroativo para os dados aos quais é aplicado. É uma transformação imediata de dados que ocorre antes da aplicação da filtragem ou de outras operações de análise.

![Configurações de subsequência de caracteres](../assets/substring-settings.png)

## Da Esquerda/Direita

Pegue uma parte de uma string com base em sua posição no início ou no fim de uma string. **[!UICONTROL Da Esquerda]** e **[!UICONTROL Da direita]** Os métodos fornecem dois detalhamentos: **[!UICONTROL De]** (em que a saída começa) e **[!UICONTROL Para]** (onde a saída termina).

* **[!UICONTROL Início da string]**: O início da string.
* **[!UICONTROL Fim da string]**: O fim da string.
* **[!UICONTROL Position]**: Um número estático de caracteres da esquerda ou direita, dependendo do método .
* **[!UICONTROL String]**: Corresponder a um caractere ou sequência de caracteres para indicar o início ou o fim de uma string. Essa lista suspensa também revela opções adicionais:
   * **[!UICONTROL Corresponder]**: A string a ser correspondente. Se a entrada não tiver correspondência com esse campo, [Nenhuma opção de valor](no-value-options.md) aplicar.
   * **[!UICONTROL Índice]**: O **[!UICONTROL Corresponder]** critérios podem ser apresentados várias vezes em uma string. Esse número inteiro determina qual correspondência deve ser iniciada ou finalizada a saída, dependendo do método . Por exemplo, um índice de `1` representa a primeira correspondência. Se o índice for superior ao número de correspondências disponíveis, [Nenhuma opção de valor](no-value-options.md) aplicar.
   * **[!UICONTROL Incluir cadeia de caracteres]**: Uma caixa de seleção que inclui a variável **[!UICONTROL Corresponder]** na saída, se ativada.
* **[!UICONTROL Length]**: Um número inteiro que especifica a contagem de caracteres a ser incluída após a posição inicial da saída. Disponível somente sob o **[!UICONTROL Para]** lista suspensa.

## Delimitador

Use esse método para campos que usam um delimitador para separar vários valores de string. Você pode extrair um elemento individual para usar como saída ou converter a string em um elemento de esquema da matriz de objetos.

* **[!UICONTROL Critério]**: Como você deseja tratar a lista delimitada de valores.
   * **[!UICONTROL Da Esquerda]**: Comece a partir do início da lista delimitada e conte para a frente.
   * **[!UICONTROL Da direita]**: Comece no final da lista delimitada e conte para trás.
   * **[!UICONTROL Converter em matriz]**: Tratar essa dimensão como se fosse um elemento de esquema da matriz de objetos.
* **[!UICONTROL Delimitador]**: O delimitador usado pelo campo.
* **[!UICONTROL Índice]**: Presente somente se o critério for Da esquerda/direita. O número do elemento como se ele estivesse em uma matriz. Por exemplo, se a entrada da string for `"Fox,Turtle,Rabbit,Wolf"` com um índice de 3, a saída é `"Rabbit"`. Se o índice for maior que o número de elementos delimitados, [Nenhuma opção de valor](no-value-options.md) aplicar.

## Análise de URL

Para uso com campos que contêm URLs. Usando o URL de exemplo `https://example.com/store/index.html?cid=campaign#cart`, as seguintes opções estão disponíveis:

* **[!UICONTROL Obter protocolo]**: Obtenha o protocolo do URL. Por exemplo, `"https://"`.
* **[!UICONTROL Obter host]**: Obtenha o host do URL. Por exemplo, `"example.com"`.
* **[!UICONTROL Obter caminho]**: Obtenha o caminho do URL. Por exemplo, `"store/index.html"`.
* **[!UICONTROL Obter valor da string de consulta]**: Obtenha o valor de uma única string de consulta. Coloque o parâmetro da string de consulta desejado na função **[!UICONTROL Chave de consulta]** campo. Se o URL acima for usado com a variável `"cid"` chave de consulta, a saída é `"campaign"`.
* **[!UICONTROL Obter valor de hash]**: Obtenha o valor de hash do URL. Por exemplo, `"cart"`.

Se a entrada não for um URL válido ou se o componente de URL desejado não estiver presente, [Nenhuma opção de valor](no-value-options.md) aplicar.

## Aparar

Cortar espaço em branco ou caracteres especiais da string.

* **[!UICONTROL Aparar espaços em branco]**: Uma caixa de seleção que remove todos os espaços em branco no início e no fim da cadeia de caracteres, se ativada.
* **[!UICONTROL Cortar caracteres especiais]**: Uma caixa de seleção que revela uma **[!UICONTROL Caracteres especiais]** campo de entrada, se ativado. Todos os caracteres neste campo são removidos da saída. Caracteres multibyte não são suportados.

## Regex

Aplique expressões regulares a uma dimensão para recuperar o valor desejado.

* **[!UICONTROL Regex]**: A fórmula da expressão regular.
* **[!UICONTROL Formato de saída]**: Um campo opcional que permite adicionar texto ou reordenar a saída do subgrupo regex. Se esse campo estiver em branco, a saída da string será a expressão regex avaliada.
* **[!UICONTROL Diferenciação de maiúsculas e minúsculas]**: Uma caixa de seleção que força a expressão regular a diferenciar maiúsculas de minúsculas, se estiver ativada.

O CJA usa um subconjunto da sintaxe de regex Perl. Se a entrada não corresponder à expressão regular e a variável **[!UICONTROL Formato de saída]** estiver em branco, [Nenhuma opção de valor](no-value-options.md) aplicar. As seguintes expressões são suportadas:

| Expressão | Descrição |
| --- | --- |
| `a` | Um caractere único `a`. |
| `a|b` | Um caractere único `a` ou `b`. |
| `[abc]` | Um caractere único `a`, `b`ou `c`. |
| `[^abc]` | Qualquer caractere único exceto `a`, `b`ou `c`. |
| `[a-z]` | Qualquer caractere único no intervalo de `a`-`z`. |
| `[a-zA-Z0-9]` | Qualquer caractere único no intervalo de `a`-`z`, `A`-`Z`ou dígitos `0`-`9`. |
| `^` | Corresponde ao início da linha. |
| `$` | Corresponde ao final da linha. |
| `\A` | Início da sequência. |
| `\z` | Final da sequência. |
| `.` | Corresponde a qualquer caractere. |
| `\s` | Qualquer caractere invisível. |
| `\S` | Sem caracteres diferentes de invisíveis. |
| `\d` | Qualquer dígito. |
| `\D` | Qualquer não dígito. |
| `\w` | Qualquer letra, número ou sublinhado. |
| `\W` | Qualquer caractere que não seja da palavra. |
| `\b` | Qualquer limite da palavra. |
| `\B` | Qualquer caractere que não seja um limite de palavra. |
| `\<` | Início da palavra. |
| `\>` | Fim da palavra. |
| `(...)` | Capturar tudo delimitado. |
| `(?:...)` | Captura sem marcação. Impede que a correspondência seja referenciada na cadeia de caracteres de saída. |
| `a?` | Zero ou um de `a`. |
| `a*` | Zero ou mais de `a`. |
| `a+` | Mais um de `a`. |
| `a{3}` | Exatamente 3 de `a`. |
| `a{3,}` | 3 ou mais de `a`. |
| `a{3,6}` | Entre 3 e 6 de `a`. |

Também há suporte para marcadores de posição de saída. É possível usar essas sequências na variável **[!UICONTROL Formato de saída]** qualquer número de vezes e em qualquer ordem para alcançar a saída da string desejada.

| Sequência de espaço reservado de saída | Descrição |
| --- | --- |
| `$&` | Gera o que correspondeu à expressão inteira. |
| `$n` | Gera o que correspondeu à subexpressão nth. Por exemplo, `$1` Gera a primeira subexpressão. |
| ``$` `` | Gera o texto entre o fim da última correspondência encontrada (ou o início do texto se nenhuma correspondência anterior foi encontrada) e o início da correspondência atual. |
| `$+` | Gera o que correspondeu à última subexpressão marcada na expressão regular. |
| `$$` | Gera o caractere de string `"$"`. |

## Vídeo sobre dimensões de vínculo

Este é um vídeo sobre dimensões de vínculo:

>[!VIDEO](https://video.tv.adobe.com/v/342694/?quality=12)
