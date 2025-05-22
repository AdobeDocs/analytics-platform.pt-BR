---
title: Funções avançadas
description: Para acessar essas funções, selecione Mostrar avançadas no menu suspenso Funções.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '5247'
ht-degree: 99%

---

# Funções avançadas

O [Construtor de métricas calculadas](cm-workflow/cm-build-metrics.md) permite aplicar funções matemáticas e estatísticas. Este artigo documenta uma lista em ordem alfabética das funções avançadas e suas definições.

Para acessar essas funções, selecione **[!UICONTROL Mostrar tudo]** abaixo da lista de ![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Funções]** no painel de componentes. Role para baixo para ver a lista de **[!UICONTROL Funções avançadas]**.

## Funções de tabela versus funções de linha

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

Quando aplicável e relevante, uma função é anotada com o tipo de função: [!BADGE Tabela]{type="Neutral"} ou [!BADGE Linha]{type="Neutral"}

## O que significa o parâmetro “incluir zeros”?

Informa se os zeros devem ou não ser incluídos no cálculo. Às vezes, zero significa *nada*, mas em alguns casos, pode ser importante.

Por exemplo, se você possuir uma métrica Receita e adicionar a métrica Visualizações de página ao relatório, aparecerão mais linhas com valores iguais a zero na sua receita. Você provavelmente não vai querer que essa métrica adicional afete qualquer **[MÉDIA](cm-functions.md#mean)**, **[MÍNIMO DA LINHA](cm-functions.md#row-min)**, **[QUARTIL](cm-functions.md#quartile)** e outros cálculos que você tenha na coluna receita. Neste caso, você deverá marcar o parâmetro `include-zeros`.

Um cenário alternativo é o que você tem duas métricas de interesse e uma tem uma média ou um mínimo mais alto porque algumas das linhas são zeros.  Nesse caso, você pode optar por não marcar o parâmetro para incluir zeros.


## E {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="E"
>abstract="Conjunção. Diferente de zero é considerado verdadeiro e igual a zero é considerado falso. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

Conjunção. Diferente de zero é considerado verdadeiro e igual a zero é considerado falso. A saída é 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| logical_test | Exige pelo menos um parâmetro, mas pode usar qualquer quantidade de parâmetros. Qualquer valor ou expressão que possa ser avaliada como VERDADEIRA ou FALSA |


## Contagem distinta aproximada {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="Contagem distinta aproximada"
>abstract="Retorna a contagem distinta aproximada de itens de dimensão para a dimensão selecionada."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Retorna a contagem distinta aproximada de itens de dimensão para a dimensão selecionada.


| Argumento | Descrição |
|---|---|
| dimensão | A dimensão cuja contagem aproximada de itens distintos você deseja calcular |

### Exemplo

Um caso de uso comum para essa função é quando você deseja obter uma quantidade aproximada de clientes.



## Arco cosseno {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="Arco cosseno"
>abstract="Retorna o arco cosseno ou o inverso do cosseno de uma métrica. O arco cosseno é o ângulo cujo cosseno é número. O ângulo retornado é dado em radianos no intervalo de 0 (zero) a pi. Se quiser converter o resultado de radianos em graus, multiplique-o por 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o arco cosseno, ou inverso do cosseno, de uma métrica. O arco cosseno é o ângulo cujo cosseno é número. O ângulo retornado é dado em radianos no intervalo de 0 (zero) a pi. Se quiser converter o resultado de radianos em graus, multiplique-o por 180/PI().


| Argumento | Descrição |
|---|---|
| metric | O cosseno do ângulo que você deseja de -1 a 1 |



## Arco seno {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="Arco seno"
>abstract="Retorna o arco seno ou o seno inverso de um número. O arco seno é o ângulo cujo seno é um número. O ângulo retornado é dado em radianos no intervalo -pi/2 a pi/2. Para expressar o arco seno em graus, multiplique o resultado por 180/PI()"

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o arco seno, ou seno inverso, de um número. O arco seno é o ângulo cujo seno é um número. O ângulo retornado é dado em radianos no intervalo -pi/2 a pi/2. Para expressar o arco seno em graus, multiplique o resultado por 180/PI().


| Argumento | Descrição |
|---|---|
| metric | O seno do ângulo que você deseja de -1 a 1 |



## Arco tangente {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="Arco tangente"
>abstract="Retorna o arco tangente ou tangente inversa de um número. O arco tangente é o ângulo cuja tangente é um número. O ângulo retornado é dado em radianos no intervalo -pi/2 a pi/2. Para expressar o arco tangente em graus, multiplique o resultado por 180/PI()."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o arco tangente, ou tangente inversa, de um número. O arco tangente é o ângulo cuja tangente é um número. O ângulo retornado é dado em radianos no intervalo -pi/2 a pi/2. Para expressar o arco tangente em graus, multiplique o resultado por 180/PI().


| Argumento | Descrição |
|---|---|
| metric | A tangente do ângulo que você deseja de -1 a 1 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="Retorna a probabilidade de uma variável aleatória com distribuição t de estudantes com n graus de liberdade ter uma pontuação z menor que col."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

Retorna a probabilidade de uma variável aleatória com distribuição t de estudantes com n graus de liberdade ter uma pontuação z menor que col.

| Argumento | Descrição |
|---|---|
| metric | A métrica para a qual você deseja a função de distribuição cumulativa da distribuição t de estudantes |
| número | Os graus de liberdade da função de distribuição cumulativa da distribuição t de estudantes |

### Exemplo

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="Retorna a probabilidade de uma variável aleatória com distribuição normal ter uma pontuação z menor que col."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

Retorna a probabilidade de uma variável aleatória com distribuição normal ter uma pontuação z menor que col.

| Argumento | Descrição |
|---|---|
| metric | A métrica para a qual você deseja a função de distribuição cumulativa da distribuição normal padrão |

### Exemplos

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## Teto {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="Teto"
>abstract="Retorna o menor número inteiro não inferior a um valor especificado. Por exemplo, se você quiser evitar relatar decimais de moeda para a receita e um produto tiver US$ 569,34, use a fórmula CEILING(Receita) para arredondar a receita para o valor mais próximo em dólar, ou US$ 570."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna o menor número inteiro que não seja menor que o valor fornecido. Por exemplo, se você quiser evitar relatar decimais de moeda para a receita e um produto tiver US$ 569,34, use a fórmula CEILING(Receita) para arredondar a receita para o valor mais próximo em dólar, ou US$ 570.

| Argumento | Descrição |
|---|---|
| metric | A métrica que você deseja arredondar |


## Confiança {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="Confiança"
>abstract="Calcule a confiança válida a qualquer momento usando o método WASKR, conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcule a confiança válida a qualquer momento usando o método WASKR, conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476).

Confiança é uma medida probabilística sobre quantos indícios existem de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (pessoas, sessões ou eventos) sobre a qual um teste será executado. |
| success-metric | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| control | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| significance-threshold | O limite nesta função é definido como 95% por padrão. |


## Confiança (Inferior) {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-lower"
>title="Confiança (Inferior)"
>abstract="Calcule a confiança **inferior** válida a qualquer momento usando o método WASKR, conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcule a confiança **inferior** válida a qualquer momento usando o método WASKR conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476).

Confiança é uma medida probabilística sobre quantos indícios existem de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (pessoas, sessões ou eventos) sobre a qual um teste será executado. |
| success-metric | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| control | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| significance-threshold | O limite nesta função é definido como 95% por padrão. |

## Confiança (Superior) {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-upper"
>title="Confiança (Superior)"
>abstract="Calcule a confiança **superior** válida a qualquer momento usando o método WASKR, conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calcule a confiança **superior** válida a qualquer momento usando o método WASKR conforme descrito em [Teorema central do limite uniforme no tempo e sequências de confiança assintótica](https://arxiv.org/pdf/2103.06476).

Confiança é uma medida probabilística sobre quantos indícios existem de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (pessoas, sessões ou eventos) sobre a qual um teste será executado. |
| success-metric | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| control | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| significance-threshold | O limite nesta função é definido como 95% por padrão. |


## Cosseno {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="Cosseno"
>abstract="Retorna o cosseno do ângulo fornecido. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna o cosseno do ângulo fornecido. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180.

| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja obter o cosseno |


## Raiz cúbica {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="Raiz cúbica"
>abstract="Retorna a raiz de cúbica positiva de um número. A raiz cúbica de um número é o valor desse número elevado à potência de 1/3."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Retorna a raiz de cúbica positiva de um número. A raiz cúbica de um número é o valor desse número elevado à potência de 1/3.


| Argumento | Descrição |
|---|---|
| metric | A métrica para a qual você deseja calcular a raiz cúbica |



## Cumulativo {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="Cumulativo"
>abstract="Retorna a soma dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos de x. Se n &lt; 0, soma os elementos anteriores."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Retorna a soma dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos de x. Se n &lt; 0, soma os elementos anteriores.

| Argumento | Descrição |
| --- | --- |
| número | O último número N de linhas para o qual retornar a soma. Se N &lt;= 0, usa todas as linhas anteriores.  |
| metric | A métrica cuja soma cumulativa você deseja obter. |

### Exemplos

| Data | Receita | CUMULATIVE(0, Receita) | CUMULATIVE(2, Receita) |
|------|------:|--------------:|--------------:|
| Maio | US$ 500 | US$ 500 | US$ 500 |
| Junho | US$ 200 | US$ 700 | US$ 700 |
| Julho | $400 | US$ 1.100 | $600 |


## Cumulativo (Média) {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="Cumulativo (Média)"
>abstract="Retorna a média dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos de x. Se n &lt; 0, soma os elementos precedentes."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Retorna a média dos últimos n elementos da coluna x. Se n > 0, soma os últimos n elementos de x. Se n &lt; 0, soma os elementos precedentes.

| Argumento | Descrição |
| --- | --- |
| número | O último número N de linhas para a qual retornar a média. Se N &lt;= 0, usa todas as linhas anteriores.  |
| metric | A métrica cuja média cumulativa você deseja obter. |

>[!NOTE]
>
>Essa função não funciona com métricas de taxa, como receita por pessoa. A função calcula a média das taxas em vez de dividir a soma da receita do último N e a soma das pessoas do último N. <br/>Em vez disso, use [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Divide](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Igual {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="Igual"
>abstract="Igual. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

Igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 = Metric 2`


## Regressão exponencial: coeficiente de correlação {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="Regressão exponencial: coeficiente de correlação"
>abstract="Regressão exponencial: Y = a exp(X) + b. Retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão exponencial: Y = a exp(X) + b. Retorna o coeficiente de correlação.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |

## Regressão exponencial: previsão de Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="Regressão exponencial: previsão de Y"
>abstract="Regressão exponencial: Y = a exp(X) + b. Retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"} Regressão exponencial: Y = a exp(X) + b. Retorna Y.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de designar como um dado independente. |
| metric_Y | Uma métrica que você designaria como um dado dependente. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão exponencial: intercepto {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="Regressão exponencial: intercepto"
>abstract="Regressão exponencial: Y = a exp(X) + b. Retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão exponencial: Y = a exp(X) + b. Retorna b.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão exponencial: inclinação {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="Regressão exponencial: inclinação"
>abstract="Regressão exponencial: Y = a exp(X) + b. Retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão exponencial: Y = a exp(X) + b. Retorna a.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Piso {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Piso"
>abstract="Retorna o maior número inteiro não superior a um valor especificado. Por exemplo, se você quiser evitar relatar decimais de moeda para a receita e um produto tiver US$ 569,34, use a fórmula FLOOR(Receita) para arredondar a receita para o valor mais próximo em dólar, ou US$ 569."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Retorna o maior número inteiro que não seja maior que um valor fornecido. Por exemplo, se você quiser evitar relatar decimais de moeda para a receita e um produto tiver US$ 569,34, use a fórmula FLOOR(Receita) para arredondar a receita para o valor mais próximo em dólar, ou US$ 569.

| Argumento | Descrição |
|---|---|
| metric | A métrica que deseja arredondar. |


## Maior que {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="Maior que"
>abstract="A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

A saída é 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| metric_X | A métrica básica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 > Metric 2`


## Superior ou igual a {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="Superior ou igual a"
>abstract="Maior ou igual a. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

Maior ou igual a. A saída é 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| metric_X | A métrica básica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 >= Metric 2`



## Cosseno hiperbólico {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="Cosseno hiperbólico"
>abstract="Retorna o cosseno hiperbólico de um número."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o cosseno hiperbólico de um número.


| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja descobrir o cosseno hiperbólico |



## Seno hiperbólico {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="Seno hiperbólico"
>abstract="Retorna o seno hiperbólico de um número."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna o seno hiperbólico de um número.

| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja descobrir o seno hiperbólico |


## Tangente hiperbólica {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="Tangente hiperbólica"
>abstract="Retorna a tangente hiperbólica de um número."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE Linha]{type="Neutral"} Retorna a tangente hiperbólica de um número.

| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja descobrir a tangente hiperbólica |


## Se {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="Se"
>abstract="Se o valor do parâmetro de condição for diferente de zero (verdadeiro), o resultado será o valor do parâmetro value_if_true. Caso contrário, é o valor do parâmetro value_if_false."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Linha]{type="Neutral"} Se o valor do parâmetro de condição for diferente de zero (verdadeiro), o resultado será o valor do parâmetro value_if_true. Caso contrário, é o valor do parâmetro value_if_false.


| Argumento | Descrição |
|---|---|
| logical_test | Obrigatório. Qualquer valor ou expressão que possa ser avaliada como VERDADEIRA ou FALSA |
| value_if_true | O valor que você deseja retornar, se o argumento logical_test for considerado VERDADEIRO. (Caso não tenha sido incluído, o padrão para este argumento é 0.) |
| value_if_false | O valor que você quer que seja retornado se o argumento logical_test for avaliado como FALSE. (Caso não seja incluído, o padrão deste argumento será 0.) |


## Menor que {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="Menor que"
>abstract="A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

A saída é 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 < Metric 2`


## Inferior ou igual a {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="Inferior ou igual a"
>abstract="Menor ou igual a. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Menor ou igual a. A saída é 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 <= Metric 2`



## Aumento {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="Aumento"
>abstract="O aumento da proporção em comparação ao valor de controle."

<!-- markdownlint-enable MD034 -->

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL LIFT(container de normalização, métrica de sucesso, controle)]**

O aumento da proporção em comparação ao valor de controle.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (pessoas, sessões ou eventos) sobre a qual um teste será executado. |
| success-metric | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| control | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |



## Regressão linear: coeficiente de correlação {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="Regressão linear: coeficiente de correlação"
>abstract="Regressão linear: Y = a X + b. Retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão linear: Y = a X + b. Retorna o coeficiente de correlação.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão linear: intercepto {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="Regressão linear: intercepto"
>abstract="Regressão linear: Y = a X + b. Retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão linear: Y = a X + b. Retorna b.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão linear: previsão de Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="Regressão linear: previsão de Y"
>abstract="Regressão linear: Y = a X + b. Retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Linha]{type="Neutral"} Regressão linear: Y = a X + b. Retorna Y.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão linear: inclinação {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="Regressão linear: inclinação"
>abstract="Regressão linear: Y = a X + b. Retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão linear: Y = a X + b. Retorna a.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Logaritmo na base 10 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="Logaritmo na base 10"
>abstract="Retorna o logaritmo de base 10 de um número."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o logaritmo de base 10 de um número.


| Argumento | Descrição |
|---|---|
| metric | O número real positivo para o qual você deseja obter o logaritmo de base 10 |


## Regressão logarítmica: coeficiente de correlação {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="Regressão logarítmica: coeficiente de correlação"
>abstract="Regressão logarítmica: Y = a ln(X) + b. Retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão logarítmica: Y = a ln(X) + b. Retorna o coeficiente de correlação.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão logarítmica: intercepto {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="Regressão logarítmica: intercepto"
>abstract="Regressão logarítmica: Y = a ln(X) + b. Retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão logarítmica: Y = a ln(X) + b. Retorna b.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão logarítmica: Y previsto {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="Regressão logarítmica: Y previsto"
>abstract="Regressão logarítmica: Y = a ln(X) + b. Retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Regressão logarítmica: Y = a ln(X) + b. Retorna Y.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão logarítmica: inclinação {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="Regressão logarítmica: inclinação"
>abstract="Regressão logarítmica: Y = a ln(X) + b. Retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão logarítmica: Y = a ln(X) + b. Retorna a.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Logaritmo natural {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="Logaritmo natural"
>abstract="Retorna o logaritmo natural de um número. Os logaritmos naturais são baseados na constante e (2,71828182845904). LN é o inverso da função EXP."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

Retorna o logaritmo natural de um número. Os logaritmos naturais são baseados na constante e (2,71828182845904). LN é o inverso da função EXP.

| Argumento | Descrição |
|---|---|
| metric | O número real positivo para o qual você deseja obter o logaritmo natural |



## Não {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="Não"
>abstract="Negação como booleano. A saída é ou 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

Negação como booleano. A saída é ou 0 (falso) ou 1 (verdadeiro).

| Argumento | Descrição |
|---|---|
| logical | Obrigatório. Um valor ou expressão que pode ser avaliada como VERDADEIRA ou FALSA |



## Não igual {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="Não igual"
>abstract="Não igual. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Não igual. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você deseja usar para comparar. |
| metric_Y | A métrica que você deseja usar para comparação. |

### Exemplo

`Metric 1 != Metric 2`


## Ou {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="Ou"
>abstract="Disjunção. Diferente de zero é considerado verdadeiro e igual a zero é considerado falso. A saída é 0 (falso) ou 1 (verdadeiro)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Linha]{type="Neutral"} Disjunção. Diferente de zero é considerado verdadeiro e igual a zero é considerado falso. A saída é 0 (falso) ou 1 (verdadeiro).


| Argumento | Descrição |
|---|---|
| logical_test | Precisa de pelo menos um parâmetro, mas pode usar qualquer quantidade de parâmetros. Qualquer valor ou expressão que possa ser avaliada como VERDADEIRA ou FALSA |


>[!NOTE]
>
>0 (zero) significa False, e qualquer outro valor é True.


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="Retorna Pi: 3,14159..."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Retorna Pi: 3,14159...


## Regressão de potência: coeficiente de correlação {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="Regressão de potência: coeficiente de correlação"
>abstract="Regressão de potência: Y = b X ^ a. Retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão de potência: Y = b X ^ a. Retorna o coeficiente de correlação.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão de potência: intercepto {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="Regressão de potência: intercepto"
>abstract="Regressão de potência: Y = b X ^ a. Retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Tabela]{type="Neutral"} Regressão de potência: Y = b X ^ a. Retorna b.


| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão de potência: previsão de Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="Regressão de potência: previsão de Y"
>abstract="Regressão de potência: Y = b X ^ a. Retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Regressão de potência: Y = b X ^ a. Retorna Y.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão de potência: inclinação {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="Regressão de potência: inclinação"
>abstract="Regressão de potência: Y = b X ^ a. Retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão de potência: Y = b X ^ a. Retorna a.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão quadrática: coeficiente de correlação {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="Regressão quadrática: coeficiente de correlação"
>abstract="Regressão quadrática: Y = (a + bX) ^ 2, retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão quadrática: Y = (a + bX) ^ 2. Retorna o coeficiente de correlação.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |

## Regressão quadrática: intercepto {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="Regressão quadrática: intercepto"
>abstract="Regressão quadrática: Y = (a + bX) ^ 2, retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão quadrática: Y = (a + bX) ^ 2. Retorna a.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão quadrática: previsão de Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="Regressão quadrática: previsão de Y"
>abstract="Regressão quadrática: Y = (a + bX) ^ 2, retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Regressão quadrática: Y = (a + bX) ^ 2. Retorna Y.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão quadrática: inclinação {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="Regressão quadrática: inclinação"
>abstract="Regressão quadrática: Y = (a + bX) ^ 2, retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão quadrática: Y = (a + bX) ^ 2. Retorna b.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Regressão recíproca: coeficiente de correlação {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="Regressão recíproca: coeficiente de correlação"
>abstract="Regressão recíproca: Y = a + b X ^ -1. Retorna o coeficiente de correlação."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão recíproca: Y = a + b X ^ -1. Retorna o coeficiente de correlação.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você gostaria de correlacionar à metric_Y |
| metric_Y | Uma métrica que você gostaria de correlacionar à metric_X |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão recíproca: intercepto {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="Regressão recíproca: intercepto"
>abstract="Regressão recíproca: Y = a + b X ^ -1. Retorna a."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão recíproca: Y = a + b X ^ -1. Retorna a.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão recíproca: previsão de Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="Regressão recíproca: previsão de Y"
>abstract="Regressão recíproca: Y = a + b X ^ -1. Retorna Y."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE Linha]{type="Neutral"} Regressão recíproca: Y = a + b X ^ -1. Retorna Y.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Regressão recíproca: inclinação {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="Regressão recíproca: inclinação"
>abstract="Regressão recíproca: Y = a + b X ^ -1. Retorna b."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE Tabela]{type="Neutral"} Regressão recíproca: Y = a + b X ^ -1. Retorna b.

| Argumento | Descrição |
|---|---|
| metric_X | Uma métrica que você designaria como o dado dependente |
| metric_Y | Uma métrica que você gostaria de designar como o dado independente |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |



## Variância de amostras

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="Variância de amostras"
>abstract="Calcula uma estimativa da variância da amostra usando a fórmula (soma(métrica^2) / (N - 1)) - (soma(métrica))^2/(N*(N-1)). em que N é a contagem do container de normalização. <br/>Isso é usado como parte de cálculos de confiança *válidos em qualquer momento*. Geralmente, esta função não é útil sozinha, mas pode ser usada para verificar cálculos ou executar cálculos de confiança *manualmente*."

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL VARIAÇÃO DE AMOSTRA(container de normalização, métrica de sucesso)]**

Calcula uma estimativa da variância da amostra.

| Argumento | Descrição |
| --- | --- |
| normalizing-container | A base (pessoas, sessões ou eventos) sobre a qual um teste será executado. |
| success-metric | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |

<!-- markdownlint-enable MD034 -->



## Seno {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="Seno"
>abstract="Retorna o seno do ângulo fornecido. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Linha]{type="Neutral"} Retorna o seno do ângulo fornecido. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180.


| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja obter o seno |




## Pontuação T {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="Pontuação T"
>abstract="O desvio da [MÉDIA](cm-functions.md#mean), dividido pelo desvio padrão. Alias da [Pontuação Z](#z-score)."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

O desvio da [MÉDIA](cm-functions.md#mean), dividido pelo desvio padrão. Alias da [Pontuação Z](#z-score).

| Argumento | Descrição |
|---|---|
| metric | A métrica para a qual você deseja obter a pontuação T |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |


## Teste t {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="Teste t"
>abstract="Realiza um teste t com cauda m e com pontuação t de x e n graus de liberdade."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

Realiza um teste t caudal m com pontuação t de x e n graus de liberdade.

| Argumento | Descrição |
|---|---|
| metric | A métrica na qual você deseja executar um teste T |
| degrees | Os graus de liberdade |
| tails | Comprimento da cauda a ser usada para realizar o teste T |

### Detalhes

A assinatura é T-TEST(metric, degrees, tails). Por baixo, ele simplesmente chama ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**. Esta função é semelhante à função **[Z-TEST](#z-test)**, que executa ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**.

- ***m*** é o número de caudas.
- ***n*** é o grau de liberdade e deve ser um número constante para todo o relatório, ou seja, não deve ser alterado linha por linha.
- ***X*** é a estatística do teste t e geralmente é uma fórmula (por exemplo, **[Z-SCORE](#z-score)**) com base em uma métrica, sendo avaliada em cada linha.

O valor de retorno é a probabilidade de exibição da estatística de teste x, dados os graus de liberdade e os números de caudas.

### Exemplos

1. Use a função para encontrar anomalias:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combine a função com **[IF](#if)** para ignorar taxas de rejeição muito altas ou baixas, e para contar sessões em todos os outros lugares:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## Tangente {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="Tangente"
>abstract="Retorna a tangente do ângulo especificado. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

Retorna a tangente do ângulo especificado. Se o ângulo estiver em graus, multiplique o ângulo por PI()/180.

| Argumento | Descrição |
|---|---|
| metric | O ângulo, em radianos, para o qual você deseja obter a tangente |



## Pontuação Z {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Pontuação Z"
>abstract="O desvio da média dividido pelo desvio padrão."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE Linha]{type="Neutral"} O desvio da média dividido pelo desvio padrão.

| Argumento | Descrição |
|---|---|
| metric | A métrica para a qual você deseja obter a pontuação Z |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos ou não |

Uma pontuação Z de 0 (zero) significa que a pontuação é igual à média. Uma pontuação Z pode ser positiva ou negativa, indicando se está acima ou abaixo da média e o número de desvios padrão.

A equação da pontuação Z é:

![](assets/z_score.png)

Onde ***[!DNL x]*** é a pontuação bruta, ***[!DNL μ]*** é a média da população e ***[!DNL σ]*** é o desvio padrão da população.

>[!NOTE]
>
>***[!DNL μ]*** (mu) e ***[!DNL σ]*** (sigma) são calculados automaticamente a partir da métrica.



## Teste z {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Teste z"
>abstract="Realiza um teste z com cauda n e com uma pontuação z de x."

<!-- markdownlint-enable MD034 -->

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

Realiza um teste z caudal n com uma pontuação z de x.

| Argumento | Descrição |
|---|---|
| metric | A métrica na qual você deseja executar o teste Z |
| tails | O comprimento da cauda a ser usada para executar o teste Z |

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