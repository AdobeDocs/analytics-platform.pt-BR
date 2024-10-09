---
title: Funções básicas
description: O Criador de métricas calculadas permite aplicar funções matemáticas e estatísticas para criar Métricas calculadas avançadas.
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Funções básicas


O [Construtor de métricas calculadas](cm-workflow/cm-build-metrics.md) permite aplicar funções matemáticas e estatísticas. Este artigo documenta a lista alfabética das funções e suas definições.

>[!NOTE]
>
>Sempre que [!DNL metric] for definida como um argumento em uma função, outras expressões de métricas também serão permitidas. Por exemplo, [COLUMN MAXIMUM(metrics)](#column-maximum) também permite [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum).



## Funções de tabela versus funções de linha

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

Quando aplicável e relevante, uma função é anotada com o tipo de função: [!BADGE Tabela]{type="Neutral"}[!BADGE Linha]{type="Neutral"}

## O que significa o parâmetro include-zeros?

Informa se os zeros devem ou não ser incluídos no cálculo. Às vezes zero significa *nada*, mas às vezes é importante.

Por exemplo, se você tiver uma métrica Receita e, em seguida, adicionar uma métrica Exibições de página ao relatório, haverá de repente mais linhas para a sua receita, que são todas zero. Você provavelmente não quer que essa métrica adicional afete qualquer **[MEAN](cm-functions.md#mean)**, **[ROW MINIMUM](cm-functions.md#row-min)**, **[QUARTILE](cm-functions.md#quartile)** e mais cálculos que você tenha na coluna de receita. Nesse caso, você verificaria o parâmetro `include-zeros`.

Um cenário alternativo é que você tem duas métricas de interesse e uma tem uma média ou um mínimo mais alto porque algumas linhas são zeros.  Nesse caso, você pode optar por não marcar o parâmetro para incluir zeros



## Valor absoluto

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL VALOR ABSOLUTO(métrica)]**

[!BADGE Linha]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular o valor absoluto. |


## Máximo da coluna

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COLUNA MÁXIMA(métrica, include_zeros)]**

Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. MAXV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Mínimo da coluna

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL COLUNA MÍNIMA(métrica, include_zeros)]**

Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. MINV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Soma da coluna

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL SOMA(métrica) DA COLUNA]**

Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão).

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |


## Contagem

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CONTAGEM(métrica)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica que você deseja contar. |


## Expoente

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTE(métrica)]**

[!BADGE Linha]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | O expoente aplicado à base e. |


## Média

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular a média. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Medianiz

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular a mediana. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Módulo

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

Retorna o restante após a divisão de x por y usando a divisão euclidiana.

| Argumento | Descrição |
|---|---|
| metric_X | A primeira métrica que você deseja dividir. |
| metric_Y | A segunda métrica que você deseja dividir. |

### Exemplos

O valor retornado tem o mesmo sinal que a entrada (ou é zero).

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

Para garantir que você sempre obtenha um número positivo, use

```
MODULO(MODULO(x,y)+y,y)
```

## Percentil

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | O valor do percentil no intervalo de 0 a 100, incluso. |
| k | A coluna de métrica que define a posição relativa. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |



## Operador de potência

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL OPERADOR DE ENERGIA(metric_X, metrix_Y)]**

Retorna x elevado à potência y.

| Argumento | Descrição |
|---|---|
| metric_X | A métrica que você gostaria de elevar para a potência metric_Y. |
| metric_Y | A potência para a qual você gostaria de elevar metric_X. |


## Quartil

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTIL(métrica, quartil, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) e [COLUMN MAXIMUM](#column-maximum) retornam o mesmo valor que [QUARTILE](#quartile) quando o quartil é igual a `0` (zero), `2` e `4`, respectivamente.

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular o valor do quartil. |
| quartil | Indica qual valor do quartil retornar. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Arredondar

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(métrica, número)]**

Arredondar sem um parâmetro *number* é o mesmo que arredondar com um parâmetro *number* de 0, ou seja, arredondar para o número inteiro mais próximo.  Com um parâmetro *number*, ROUND retorna os dígitos *number* à direita do decimal.  Se *number* for negativo, ele retornará 0 à esquerda do decimal.

| Argumento | Descrição |
|---|---|
| métrica | A métrica que deseja arredondar. |
| number | Quantos dígitos à direita do decimal devem ser retornados. (Se negativo, retorna zeros à esquerda do decimal). |

### Exemplos

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## Contagem de linhas

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL CONTAGEM DE LINHAS()]**

Retorna a contagem de linhas referente a uma determinada coluna (o número de elementos únicos reportados em uma dimensão). *Únicos excedidos* são contados como 1.


## Máx. da linha

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MAX(metric, include_zeros) de LINHA]**

Máximo de colunas de cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |

## Mín. da linha

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL MÍN. LINHA(métrica, include_zeros)]**

Mínimo de colunas de cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |



## Soma da linha

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL SOMA DA LINHA(métrica, include_zeros)]**

Soma das colunas de cada linha.

| Argumento | Descrição |
|---|---|
| métrica | Exige pelo menos uma métrica, mas pode usar qualquer número de métricas como parâmetros. |


## Raiz quadrada

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL RAIZ QUADRADA(métrica, include_zeros)]**

[!BADGE Linha]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular a raiz quadrada. |


## Desvio padrão

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL DESVIO PADRÃO(métrica, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| | A métrica para a qual você deseja calcular o desvio padrão. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


## Variação

![Efeito](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Tabela]{type="Neutral"}

| Argumento | Descrição |
|---|---|
| métrica | A métrica para a qual você deseja calcular a variação. |
| include_zeros | Se os valores zero devem ser incluídos nos cálculos. |


A equação de VARIANCE é:

![](assets/variance_eq.png){width="100"}

Onde *x* é a média da amostra, [MEAN(*metric*)](#mean) e *n* é o tamanho da amostra.


Para calcular uma variação, você observa uma coluna inteira de números. Nessa lista de números, calcule primeiro a média. Depois de obter a média, você percorre cada entrada e faz o seguinte:

1. Subtraia a média do número.

1. Eleve o resultado ao quadrado.

1. Adicione-o ao total.

Depois de iterar em toda a coluna, você tem um único total. Depois, divida o total pelo número de itens na coluna. Esse número é a variação da coluna. É um número único. No entanto, é exibido como uma coluna de números.

No exemplo da seguinte coluna de três itens:

| coluna |
|:---:|
| 1 |
| 2 |
| 3 |

A média dessa coluna é 2. A variação da coluna é ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3.




<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->