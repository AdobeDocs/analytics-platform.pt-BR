---
title: Funções avançadas
description: Para acessar essas funções, selecione Mostrar avançadas na lista suspensa Funções.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '3126'
ht-degree: 19%

---

# Funções avançadas

O [Construtor de métricas calculadas](cm-workflow/cm-build-metrics.md) permite aplicar funções matemáticas e estatísticas. Este artigo documenta a lista alfabética das funções avançadas e suas definições.

Para acessar essas funções, selecione a lista **[!UICONTROL Mostrar tudo]** abaixo de ![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL Funções]** no painel Componentes. Role para baixo para ver a lista de **[!UICONTROL Funções avançadas]**.

## Funções de tabela versus funções de linha

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

Quando aplicável e relevante, uma função é anotada com o tipo de função: [!BADGE Tabela]{type="Neutral"}[!BADGE Linha]{type="Neutral"}

## O que significa o parâmetro include-zeros?

Informa se os zeros devem ou não ser incluídos no cálculo. Às vezes zero significa *nada*, mas às vezes é importante.

Por exemplo, se você tiver uma métrica Receita e, em seguida, adicionar uma métrica Exibições de página ao relatório, haverá de repente mais linhas para a sua receita, que são todas zero. Você provavelmente não quer que essa métrica adicional afete qualquer **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e mais cálculos que você tenha na coluna de receita. Nesse caso, você verificaria o parâmetro `include-zeros`.

Um cenário alternativo é que você tem duas métricas de interesse e uma tem uma média ou um mínimo mais alto porque algumas linhas são zeros.  Nesse caso, você pode optar por não marcar o parâmetro para incluir zeros.


## E

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**


Conjunção. Diferente de zero é considerado verdadeiro e igual a zero é considerado falso. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| logical_test | Requer pelo menos um parâmetro, mas pode ter qualquer número de parâmetros. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE |

## Contagem distinta aproximada

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Retorna a contagem distinta aproximada de itens de dimensão para a dimensão selecionada.


| Argumento | Descrição |
|---|---|
| dimensão | A dimensão para a qual você deseja calcular a contagem distinta aproximada de itens |

### Exemplo

Um caso de uso comum para essa função é quando você deseja obter um número aproximado de clientes.




## Arco cosseno

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O cosseno do ângulo que você deseja de -1 a 1 |



## Arco seno

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SENO(métrica)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O seno do ângulo que você deseja de -1 a 1 |



## Arco tangente

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | A tangente do ângulo desejado de -1 a 1 |



## Cdf-T

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(métrica, número)]**


Retorna a probabilidade de uma variável aleatória com distribuição student-t com n graus de liberdade ter uma pontuação Z menor que col.


| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja a Função de distribuição cumulativa da distribuição t de estudante |
| number | Os graus de liberdade para a função de distribuição cumulativa da distribuição t de estudante |

### Exemplo

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(métrica, número)]**


Retorna a probabilidade de uma variável aleatória com uma distribuição normal ter uma pontuação Z menor que col.


| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja a função Distribuição cumulativa da Distribuição normal padrão |

### Exemplos

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Teto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL LIMITE(métrica)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | A métrica que você deseja arredondar |


## Confiança (inferior)

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANÇA(contêiner de normalização, métrica de sucesso, controle, limite de significância)]**

Calcule a confiança válida a qualquer momento **lower** usando o método WASKR conforme descrito em [Teoria de limite central uniforme no tempo e sequências de confiança assintótica](http://arxiv.org/pdf/2103.06476).

Confiança é uma medida probabilística sobre quanta evidência existe de que determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (Pessoas, Sessões ou Eventos) em que um teste é executado. |
| métrica de sucesso | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| controle | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| limite de significância | O limite nesta função é definido como um padrão de 95%. |

## Confiança (superior)

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIANÇA(contêiner de normalização, métrica de sucesso, controle, limite de significância)]**

Calcule a confiança válida a qualquer momento **upper** usando o método WASKR conforme descrito em [Teoria de limite central uniforme no tempo e sequências de confiança assintótica](http://arxiv.org/pdf/2103.06476).

Confiança é uma medida probabilística sobre quanta evidência existe de que determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (Pessoas, Sessões ou Eventos) em que um teste é executado. |
| métrica de sucesso | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| controle | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| limite de significância | O limite nesta função é definido como um padrão de 95%. |


## Cosseno

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COSSENO(métrica)]**

[!BADGE Linha]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja o cosseno |


## Raiz cúbica

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL RAIZ DO CUBO(métrica)]**


Retorna a raiz cúbica positiva de um número. A raiz cúbica de um número é o valor dele elevado à potência de 1/3.


| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular a raiz do cubo |



## Cumulativo

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Retorna a soma dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos ou x. Se n &lt; 0, soma os elementos anteriores.

| Argumento | Descrição |
| --- | --- |
| number | O último número N de linhas para o qual retornar a soma. Se N &lt;= 0, usar todas as linhas anteriores. |
| métrica | A métrica para a qual você deseja a Soma cumulativa. |

### Exemplos

| Data | Receita | CUMULATIVE(0, Receita) | CUMULATIVE(2, Receita) |
|------|------:|--------------:|--------------:|
| Maio | $ 500 | $ 500 | $ 500 |
| Junho | $ 200 | $ 700 | $ 700 |
| Julho | $400 | $ 1.100 | $600 |


## Cumulativo (Médio)

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MÉDIA CUMULATIVA(número, métrica)]**

Retorna a média dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos ou x. Se n &lt; 0, soma os elementos anteriores.

| Argumento | Descrição |
| --- | --- |
| number | O último número N de linhas para retornar a média. Se N &lt;= 0, usar todas as linhas anteriores. |
| métrica | A métrica para a qual você deseja a Média cumulativa. |

>[!NOTE]
>
>Essa função não funciona com métricas de taxa como receita por pessoa. A função calcula a média das taxas em vez de dividir a soma da receita dos últimos N e a soma das pessoas dos últimos N. <br/>Em vez disso, use [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Divide](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Igual

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL IGUAL()]**


Igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | |
| metric_Y | |

### Exemplo

`Metric 1 = Metric 2`



## Regressão exponencial: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO EXPONENCIAL: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |

## Regressão exponencial: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO EXPONENCIAL: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado independente. |
| metric_Y | Uma métrica que você designaria como um dado dependente. |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão exponencial: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO EXPONENCIAL: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão exponencial: inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO EXPONENCIAL: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Floor

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL LIMITE MÍNIMO(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica que deseja arredondar. |


## Maior que

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MAIOR QUE()]**


A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | |
| metric_Y | |

### Exemplo

`Metric 1 > Metric 2`

## Maior que ou igual

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MAIOR QUE OU IGUAL()]**


Maior que ou igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X |  |
| metric_Y |  |

### Exemplo

`Metric 1 >= Metric 2`



## Cosseno hiperbólico

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COSSENO HIPERBÓLICO(métrica)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja encontrar o cosseno hiperbólico |



## Seno hiperbólico

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL SENO HIPERBÓLICO(métrica)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja encontrar o seno hiperbólico |



## Tangente hiperbólica

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENTE(métrica) HIPERBÓLICA]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja encontrar a tangente hiperbólica |


## Se

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| logical_test | Obrigatório. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE |
| value_if_true | O valor que você deseja retornar se o argumento logical_test for considerado TRUE. (Caso não tenha sido incluído, o padrão para este argumento é 0.) |
| value_if_false | O valor que você quer que seja retornado se o argumento logical_test for avaliado como FALSE. (Caso não seja incluído, o padrão deste argumento será 0.) |


## Menor que

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MENOR QUE()]**


A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | |
| metric_Y | |


### Exemplo

`Metric 1 < Metric 2`

## Menor que ou igual

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MENOR QUE OU IGUAL()]**

Menor que ou igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | |
| metric_Y | |

### Exemplo

`Metric 1 <= Metric 2`



## Regressão linear: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO LINEAR: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão linear: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO LINEAR: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão linear: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO LINEAR: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão linear: Inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO LINEAR: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Logaritmo na base 10

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O número real positivo cujo logaritmo de base 10 você deseja |


## Regressão logarítmica: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE LOG: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão logarítmica: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE LOG: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão logarítmica: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE LOG: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão logarítmica: inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE LOG: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Logaritmo natural

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL LOG(métrica) NATURAL]**


Retorna o logaritmo natural de um número. Logaritmos naturais se baseiam na constante e (2,71828182845904). LN é o inverso da função EXP.


| Argumento | Descrição |
|---|---|
| métrica | O número real positivo cujo logaritmo natural você deseja |



## Não

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL NÃO(lógico)]**


Negação como booleano. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| lógico | Obrigatório. Um valor ou expressão que pode ser avaliado como TRUE ou FALSE |



## Não Igual

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL NÃO IGUAL()]**


Não Igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | |
| metric_Y | |

### Exemplo

`Metric 1 != Metric 2`


## Ou

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL OU(logical_test)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| logical_test | Requer pelo menos um parâmetro, mas pode ter qualquer número de parâmetros. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE |


>[!NOTE]
>
>0 (zero) significa False, e qualquer outro valor é True.


## Pi

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Retorna Pi: 3,14159...


## Regressão de potência: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE POTÊNCIA: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão de potência: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE POTÊNCIA: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão de potência: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE POTÊNCIA: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão de potência: inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO DE POTÊNCIA: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão quadrática: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO QUADRÁTICA: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |

## Regressão quadrática: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO QUADRÁTICA: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão quadrática: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO QUADRÁTICA: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |

## Regressão quadrática: inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO QUADRÁTICA: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |



## Regressão recíproca: coeficiente de correlação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO RECÍPROCA: COEFICIENTE DE CORRELAÇÃO(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar com metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar com metric_X |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão recíproca: intercepto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO RECÍPROCA: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão recíproca: valor previsto de Y

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO RECÍPROCA: Y PREVISTO (metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Regressão recíproca: inclinação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL REGRESSÃO RECÍPROCA: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como um dado independente |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |




## Seno

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL SENO(métrica)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja o seno |




## Pontuação T

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**


O desvio de [MEAN](cm-functions.md#mean), dividido pelo desvio padrão. Alias da [Pontuação Z](#z-score).


| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja a Pontuação T |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |


## Teste t

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL T-TESTE(métrica, graus, caudas)]**


Executa um teste t m-caudal com pontuação t de x e n graus de liberdade.


| Argumento | Descrição |
|---|---|
| métrica | A métrica na qual você deseja executar um teste T |
| graus | Os graus de liberdade |
| caudas | Comprimento da cauda a utilizar para a realização do ensaio T |

### Detalhes

A assinatura é T-TEST(métrica, graus, caudas). Por baixo, ele simplesmente chama ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Esta função é semelhante à função **[Z-TEST](#z-test)**, que executa ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** é o número de caudas.
- ***n*** é o grau de liberdade e deve ser um número constante para todo o relatório, ou seja, não deve ser alterado linha por linha.
- ***x*** é a estatística de teste T e geralmente seria uma fórmula (por exemplo, **[PONTUAÇÃO Z](#z-score)**) com base em uma métrica e é avaliada em cada linha.

O valor de retorno é a probabilidade de exibição da estatística de teste x, dados os graus de liberdade e os números de caudas.

**Exemplos:**

1. Use a função para encontrar valores atípicos:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combine a função com **[IF](#if)** para ignorar taxas de devolução muito altas ou baixas e para contar sessões em outro local:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## Tangente

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**


Retorna a tangente do ângulo especificado. Se o ângulo estiver em graus, multiplique-o por PI( )/180.


| Argumento | Descrição |
|---|---|
| métrica | O ângulo em radianos para o qual você deseja a tangente |



## Pontuação Z

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL PONTUAÇÃO Z(métrica, include_zeros)]**


[!BADGE Linha]{type="Neutral"}


| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja a pontuação Z |
| include_zeros | Se os valores zero devem ser incluídos ou não nos cálculos |

Uma pontuação Z de 0 (zero) implica que a pontuação é a mesma que a média. Uma pontuação Z pode ser positiva ou negativa, indicando se está acima ou abaixo da média e o número de desvios padrão.

A equação da pontuação Z é:

![](assets/z_score.png)

Onde ***[!DNL x]*** é a pontuação bruta, ***[!DNL μ]*** é a média da população e ***[!DNL σ]*** é o desvio padrão da população.

>[!NOTE]
>
>***[!DNL μ]*** (mu) e ***[!DNL σ]*** (sigma) são automaticamente calculados a partir da métrica.



## Teste z

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**


Executa um teste z sem caudas com uma pontuação z de x.


| Argumento | Descrição |
|---|---|
| métrica | A métrica na qual você deseja executar o teste Z |
| caudas | O comprimento da cauda a ser usada para executar o teste Z |

>[!NOTE]
>
>O teste z assume que os valores são distribuídos normalmente.









<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->