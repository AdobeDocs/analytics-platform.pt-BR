---
description: As funções permitem filtrar/classificar seus dados e realizar análises estatísticas.
title: Usar funções
feature: Calculated Metrics
exl-id: 7a41aa4e-90c6-4242-a801-2eef6b524cfe
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '4051'
ht-degree: 97%

---

# Usar funções

As funções permitem filtrar, classificar os dados e fazer análises estatísticas simples e complexas.

Para obter uma lista de todas as funções, consulte [Funções básicas](/help/components/calc-metrics/cm-functions.md) e [Funções avançadas](/help/components/calc-metrics/cm-adv-functions.md).


>[!NOTE]
>
>Sempre que [!DNL metric] for definida como um argumento em uma função, outras expressões de métricas também serão permitidas. Por exemplo, [!DNL MAXV(metrics)] também permite [!DNL MAXV(PageViews + Visits).]
>

>[!NOTE]
>
>Ao incluir funções na Definição do construtor de métricas calculadas, sempre aplique a função antes de arrastar métricas ou filtros.
>

## Funções de tabela versus Funções de linha

Uma função de tabela exibe um resultado igual para cada linha da tabela. Uma função de linha exibe um resultado diferente para cada linha da tabela.

## O que significa o parâmetro Incluir zeros?

Informa se os zeros devem ou não ser incluídos no cálculo. Muitas vezes, zero significa &quot;nada&quot;; mas em alguns casos, pode ser importante.

Por exemplo, se você possuir uma métrica de Receita e adicionar a métrica de Exibições de página ao relatório, aparecerão mais linhas com valores iguais a zero para sua receita. Você provavelmente não quer que isso afete nenhum cálculo de MÉDIA, MÍN, QUARTIL etc. que você possui na coluna de receita. Neste caso, você deve marcar o parâmetro Incluir zeros.

Por outro lado, se você possuir duas métricas de interesse, pode não ser correto dizer que uma tem uma média ou valor mínimo maior que a outra por causa dos zeros de algumas linhas. Neste caso, é melhor não marcar o parâmetro Incluir zeros.

<!-- This video is way too outdated and too much AA oriented to comfortably show as part of CJA functionality 

Watch this [video](https://youtu.be/SSyWvomnewI) to understand the use of functions.

-->

+++ Funções básicas


## Valor absoluto (Linha)

Retorna o valor absoluto de um número. O valor absoluto de um número é o número com um valor positivo.

```
ABS(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter o valor absoluto. |

## Máximo da coluna

Retorna o maior valor em um conjunto de elementos de dimensão para uma coluna de métrica. MAXV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

```
MAXV(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | Uma métrica que você gostaria de avaliar. |

## Mínimo da coluna

Retorna o menor valor em um conjunto de elementos de dimensão para uma coluna de métrica. MINV avalia verticalmente em uma única coluna (métrica) nos elementos da dimensão.

```
MINV(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | Uma métrica que você gostaria de avaliar. |

## Soma da coluna

Adiciona todos os valores numéricos de uma métrica em uma coluna (nos elementos de uma dimensão).

```
SUM(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter o valor total ou soma. |

## Contagem (Tabela)

Retorna o número, ou contagem, de valores diferentes de zero de uma métrica em uma coluna (o número de elementos únicos informados em uma dimensão).

```
COUNT(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica que deseja contar. |

## Expoente (Linha)

Retorna *e* elevado à potência de um número especificado. A constante *e* é igual a 2,71828182845904, a base do logaritmo natural. EXP é o inverso de LN, o logaritmo natural de um número.

```
EXP(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O exponente aplicado à base *e*. |

## Exponenciação

Operador de potência


pow(x,y) = x<sup>y</sup> = x *x* x*... (y vezes)


## Média (Tabela)

Retorna a média aritmética, ou média, de uma métrica em uma coluna.

```
MEAN(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a média. |

## Mediana (Tabela)

Retorna a mediana de uma métrica em uma coluna. A mediana é o número presente no meio de um conjunto de números, ou seja, metade dos números apresentam valores maiores ou iguais à mediana e metade são menores ou iguais à mediana.

```
MEDIAN(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a mediana. |

## Módulo

O restante de col1/col2, usado a divisão euclidiana.

Retorna o resto da divisão de x por y.

```
x = floor(x/y) + modulo(x,y)
```

O valor retornado tem o mesmo sinal que a entrada (ou é zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Para obter sempre um número positivo, use

```
modulo(modulo(x,y)+y,y)
```

## Percentil (Tabela)

Retorna o milésimo percentil dos valores de uma métrica. É possível usar esta função para estabelecer um limite de aceitação. Por exemplo, é possível analisar elementos de dimensão com pontuação acima do percentil 90.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> A coluna de métrica que define a posição relativa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> O valor do percentil no intervalo de 0 a 100, incluso. </td> 
  </tr> 
 </tbody> 
</table>

## Quartil (Tabela)

Retorna o quartil de valores de uma métrica. Por exemplo, os quartis podem ser usados para encontrar a porcentagem de 25% dos produtos com maior receita. MINV, MEDIAN, e MAXV retornam o mesmo valor que QUARTILE quando o quartil é igual a 0 (zero), 2 e 4, respectivamente.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argumento </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> A métrica para a qual você deseja obter o valor do quartil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quartil </p> </td> 
   <td colname="col2"> Indica o *valor a retornar. </td> 
  </tr> 
 </tbody> 
</table>

&#42;Se *quart* = 0, QUARTILE retorna o valor mínimo. Se *quart* = 1, QUARTILE retorna o primeiro quartil (percentil 25). Se *quart* = 2, QUARTILE retorna o primeiro quartil (percentil 50). Se *quart* = 3, QUARTILE retorna o primeiro quartil (percentil 75). Se *quart* = 4, QUARTILE retorna o valor máximo.

## Arredondar

Retorna o número inteiro mais próximo para um determinado valor. Por exemplo, caso você não queira relatar os decimais na receita e um produto apresentar um valor de US$569,34, use a fórmula Round(*Revenue*) para arredondar a receita para o número inteiro mais próximo; neste caso, US$569. Um produto de US$569,51 será arredondado para o valor inteiro mais próximo, ou seja, US$570.

```
ROUND(metric)
```

| Argumento | Descrição |
|---|---|
| *número* | A métrica que deseja arredondar. |

Arredondar sem um parâmetro de dígitos é igual a arredondar com um parâmetro de dígitos de 0; ou seja, arredondar para o número inteiro mais próximo. Com um parâmetro de dígitos, ele retorna o mesmo número de dígitos à direita da casa decimal. Se os dígitos forem negativos, retornará zeros à esquerda da casa decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Contagem de linhas

Retorna a contagem de linhas de uma determinada coluna (o número de elementos únicos relatados em uma dimensão). Os valores &quot;únicos excedidos&quot; são contados como 1.

## Máx. da linha

O número máximo de colunas em cada linha.

## Mín. da linha

O número mínimo de colunas em cada linha.

## Soma da linha

A soma das colunas em cada linha.

## Raiz quadrada (Linha)

Retorna a raiz quadrada positiva de um número. A raiz quadrada de um número é o valor do número elevado à potência de 1/2.

```
SQRT(metric)
```

| Argumento | Descrição |
|---|---|
| *número* | A métrica para a qual você deseja obter a raiz quadrada. |

## Desvio padrão (Tabela)

Retorna o desvio padrão, ou a raiz quadrada da variação, baseada em uma amostra da população de dados.

A equação de STDEV é:

![](../assets/std_dev.png)

onde x é a média da amostra (*métrica*), e *n* é o tamanho da amostra.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argumento</b> </td> 
   <td> <b> Descrição</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> A métrica para a qual você deseja obter o desvio padrão. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variação (Tabela)

Retorna a variação baseada em uma amostra da população de dados.

A equação de VARIANCE é:

![](../assets/variance_eq.png)

onde x é a média da amostra, MEAN(*metric*), e *n* é o tamanho da amostra.

```
VARIANCE(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a variação. |

Para calcular uma variação, considere uma coluna inteira de números. Nessa lista de números, calcule primeiro a média. Após obter a média, faça o seguinte em cada entrada:

1. Subtraia a média do número.

2. Eleve o resultado ao quadrado.

3. Adicione-o ao total.

Quando você iterar na coluna inteira, terá um total único. Depois, divida o total pelo número de itens na coluna. Esse número é a variação da coluna. É um número único. No entanto, é exibido como uma coluna de números.

No caso de uma coluna de três itens:

1

2

3

A média dessa coluna é 2. A variação da coluna será ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

+++

+++ Funções avançadas


## AND

Retorna o valor do seu argumento. Use NOT para garantir que um valor não seja igual a um determinado valor.

>[!NOTE]
>
>0 (zero) significa False, e qualquer outro valor é True.

```
AND(logical_test1,[logical_test2],...)
```

| Argumento | Descrição |
|---|---|
| *logical_test1* | Obrigatório. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE. |
| *logical_test2* | Opcional. Condições adicionais que você deseja avaliar como TRUE ou FALSE |

## Contagem distinta aproximada (dimensão)

Retorna a contagem distinta aproximada de itens de dimensão em referência à dimensão selecionada. A função usa o método HyperLogLog (HLL) de aproximação de contagens distintas. Está configurada para garantir que o valor fique entre 5% do valor inteiro em 95% das vezes.

```
Approximate Count Distinct (dimension)
```

| Argumento |  |
|---|---|
| *dimension* | A dimensão cuja contagem distinta de itens você deseja obter. |

### Caso de uso de exemplo

A Contagem distinta aproximada (eVar de ID de cliente) é um caso de uso comum para essa função.

Definição de uma nova métrica calculada &quot;Número aproximado de clientes&quot;:

![Definição de nova dimensão distinta de região aproximada mostrando a ID do Cliente (eVar 1)](../assets/approx-count-distinct.png)

A métrica “Número aproximado de clientes” deve ser usada em relatórios da seguinte maneira:

![Tabela de forma livre mostrando Visitantes únicos e Clientes aproximados ](../assets/approx-customers.png)

### Comparação de funções de contagem

Approximate Count Distinct() é uma melhoria das funções Count() e RowCount(), pois a métrica criada pode ser usada em qualquer relatório dimensional para renderizar uma contagem aproximada de itens de uma dimensão separada. Por exemplo, a contagem de IDs de clientes usadas em um relatório de Tipo de dispositivo móvel.

Essa função será menos precisa que Count() e RowCount(), porque usa o método HLL, em comparação a Count() e RowCount(), que são contagens exatas.

## Arco cosseno (Linha)

Retorna o arco cosseno, ou o cosseno inverso, de uma métrica. O arco seno é o ângulo cujo cosseno é um número. O ângulo retornado é fornecido em radianos, no intervalo de 0 (zero) a pi. Caso queira converter o resultado de radianos para graus, multiplique por 180/PI( ).

```
ACOS(metric)
```

| Argumento |  |
|---|---|
| *metric* | O cosseno do ângulo que você deseja de -1 a 1. |

## Arco seno (Linha)

Retorna o arco seno, ou seno inverso, de um número. O arco seno é o ângulo cujo seno é um número. O ângulo é fornecido em radianos, no intervalo de -pi/2 a pi/2. Para expressar o arco seno em graus, multiplique o resultado por 180/PI( ).

```
ASIN(metric)
```

| Argumento |  |
|---|---|
| *metric* | O cosseno do ângulo que você deseja de -1 a 1. |

## Arco tangente (Linha)

Retorna o arco tangente, ou a tangente inversa, de um número. O arco tangente é o ângulo cuja tangente é um número. O ângulo é fornecido em radianos, no intervalo de -pi/2 a pi/2. Para expressar o arco tangente em graus, multiplique o resultado por 180/PI( ).

```
ATAN(metric)
```

| Argumento |  |
|---|---|
| *metric* | O cosseno do ângulo que você deseja de -1 a 1. |

## Regressão exponencial: valor previsto de Y (Linha)

Calcula os valores previstos de y (metric_Y), levando em conta os valores de x conhecidos (metric_X) e usando o método dos quadrados mínimos para calcular a linha de melhor ajuste baseada em.

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Cdf-T

Retorna o percentual dos valores em uma distribuição t de student com n graus de liberdade, que conta com uma pontuação Z menor que x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Retorna o percentual dos valores em uma distribuição normal que conta com uma pontuação Z menor que x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## Limite máximo (Linha)

Retorna o menor número inteiro não inferior a um valor especificado. Por exemplo, caso você não queira relatar os decimais na receita e um produto apresentar um valor de US$569,34, use a fórmula CEILING(*Revenue*) para arredondar a receita para cima; neste caso, US$570.

```
CEILING(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica que deseja arredondar. |

## Confiança

[!UICONTROL Confiança] é uma medida probabilística sobre quanta evidência existe de que determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual.

```
fx Confidence (normalizing-container, success-metric, control, significance-threshold)
```

| Argumento | Descrição |
| --- | --- |
| Normalização do container | A base (Pessoas, Sessões ou Eventos) em que um teste será executado. |
| Métrica de Sucesso | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| Controle | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |
| Limite de significância | O limite nesta função é definido como um padrão de 95%. |

{style="table-layout:auto"}

## Cosseno (Linha)

Retorna o cosseno do ângulo especificado. Se o ângulo estiver em graus, multiplique-o por PI( )/180.

```
COS(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja obter o cosseno. |

## Raiz cúbica

Retorna a raiz cúbica positiva de um número. A raiz cúbica de um número é o valor dele elevado à potência de 1/3.

```
CBRT(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica para a qual você deseja obter a raiz cúbica. |

## Cumulativo

Retorna a soma de x para as últimas N linhas (conforme ordenado pela dimensão, usando valores de hash para campos baseados em sequências).

Se N &lt;= 0, usa todas as linhas anteriores. Já que é ordenado pela dimensão, é útil somente em dimensões com ordem natural como datas ou comprimento do caminho.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## Média acumulada

Retorna a média das últimas N linhas.

Se N &lt;= 0, usa todas as linhas anteriores. Já que é ordenado pela dimensão, é útil somente em dimensões com ordem natural como datas ou comprimento do caminho.

>[!NOTE]
>
>Isso não funciona conforme o esperado com métricas de taxa como receita/pessoa: calcula a média das taxas em vez de dividir a soma da receita dos últimos N e a soma das pessoas dos últimos N. Em vez disso, use

```
cumul(revenue)/cumul(person)
```

## Igual

Retorna itens que possuem o mesmo valor numérico ou de sequência.

## Regressão exponencial_ Coeficiente de correlação (Tabela)

Retorna o coeficiente de correlação *r* entre duas colunas de métrica (*metric_A* e *metric_B*) para a equação de regressão.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você gostaria de correlacionar a *metric_Y*. |
| *metric_Y* | Uma métrica que você gostaria de correlacionar a *metric_X*. |

## Regressão exponencial: intercepto (Tabela)

Retorna o intercepto *b* entre duas colunas de métrica (*metric_X* e *metric_Y*) para

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão exponencial: inclinação (Tabela)

Retorna a inclinação *a* entre duas colunas de métrica (*metric_X* e *metric_Y*) para

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Limite mínimo (Linha)

Retorna o maior número inteiro não superior a um valor especificado. Por exemplo, caso você não queira relatar os decimais na receita e um produto apresentar um valor de US$569,34, use a fórmula FLOOR(*Revenue*) para arredondar a receita para baixo; neste caso, US$569.

```
FLOOR(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | A métrica que deseja arredondar. |

## Maior que

Retorna itens cuja contagem numérica é superior ao valor inserido.

## Maior que ou igual

Retorna itens cuja contagem numérica é superior ou igual ao valor inserido.

## Cosseno hiperbólico (Linha)

Retorna o cosseno hiperbólico de um número.

```
COSH(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja descobrir o cosseno hiperbólico. |

## Seno hiperbólico (Linha)

Retorna o seno hiperbólico de um número.

```
SINH(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja descobrir o seno hiperbólico. |

## Tangente hiperbólica (Linha)

Retorna a tangente hiperbólica de um número.

```
TANH(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja descobrir a tangente hiperbólica. |

## IF (Linha)

A função IF retorna um valor se uma condição especificada for considerada TRUE, e outro valor se a condição for considerada FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argumento | Descrição |
|---|---|
| *logical_test* | Obrigatório. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE. |
| *[value_if_true]* | O valor que você deseja retornar se o argumento *logical_test* for considerado TRUE. (Caso não tenha sido incluído, o padrão para este argumento é 0.) |
| *[value_if_false]* | O valor que você deseja retornar se o argumento *logical_test* for considerado FALSE. (Caso não tenha sido incluído, o padrão para este argumento é 0.) |

## Menor que

Retorna itens cuja contagem numérica é inferior ao valor inserido.

## Menor que ou igual

Retorna itens cuja contagem numérica é inferior ou igual ao valor inserido.

## Aumento

Retorna o aumento que uma variante específica tinha em conversões sobre uma variante de controle. É a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base expresso como uma porcentagem.

```
fx Lift (normalizing-container, success-metric, control)
```

| Argumento | Descrição |
| --- | --- |
| Normalização do container | A base (Pessoas, Sessões ou Eventos) em que um teste será executado. |
| Métrica de Sucesso | A métrica, ou as métricas, com as quais um usuário está comparando variantes. |
| Controle | A variante com a qual todas as outras variantes do experimento estão sendo comparadas. Insira o nome do item de dimensão da variante de controle. |

{style="table-layout:auto"}

## Regressão linear: Coeficiente de correlação

Y = a X + b. Retorna o coeficiente de correlação.

## Regressão linear: Intercepto

Y = a X + b. Retorna b.

## Regressão linear: Valor previsto de Y

Y = a X + b. Retorna Y.

## Regressão linear: Inclinação

Y = a X + b. Retorna a.

## Logaritmo na base 10 (Linha)

Retorna o logaritmo de base 10 de um número.

```
LOG10(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O número real positivo para o qual você deseja obter o logaritmo de base 10. |

## Regressão logarítmica: coeficiente de correlação (Tabela)

Retorna o coeficiente de correlação *r* entre duas colunas de métrica (*metric_X* e *metric_Y*) para a equação de regressão [!DNL Y = a ln(X) + b]. É calculada usando a equação de CORREL.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você gostaria de correlacionar a *metric_Y*. |
| *metric_Y* | Uma métrica que você gostaria de correlacionar a *metric_X*. |

## Regressão logarítmica: intercepto (Tabela)

Retorna o intercepto *b* como a regressão dos quadrados mínimos entre duas colunas de métrica (*metric_X* e *metric_Y*) para a equação de regressão [!DNL Y = a ln(X) + b]. É calculada usando a equação de INTERCEPT.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão logarítmica: valor previsto de Y (Linha)

Calcula os valores previstos de [!DNL y] (metric_Y), tendo em conta os valores de [!DNL x] conhecidos (metric_X) e usando o método dos quadrados mínimos para calcular a linha de melhor ajuste, com base em [!DNL Y = a ln(X) + b]. É calculada usando a equação de ESTIMATE.

Em análises de regressão, esta função calcula os valores previstos de [!DNL y] (*metric_Y*), conhecidos os valores de [!DNL x] (*metric_X*) e usando o logaritmo para calcular a linha de melhor ajuste para a equação de regressão [!DNL Y = a ln(X) + b]. O valor de [!DNL a] corresponde a cada valor de x, e [!DNL b] refere-se a um valor constante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão logarítmica: inclinação (Tabela)

Retorna a inclinação *a* entre duas colunas de métrica (*metric_X* e *metric_Y*) para a equação de regressão [!DNL Y = a ln(X) + b]. É calculada usando a equação de SLOPE.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argumento | Descrição |
|---|---|
| *metric_A* | Uma métrica que você designaria como um dado dependente. |
| *metric_B* | Uma métrica que você gostaria de designar como um dado independente. |

## Logaritmo natural

Retorna o logaritmo natural de um número. Logaritmos naturais se baseiam na constante *e* (2,71828182845904). LN é o inverso da função EXP.

```
LN(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O número real positivo para o qual você deseja obter o logaritmo natural. |

## NOT

Retorna 1 se o número for 0, ou retorna 0 se for qualquer outro número.

```
NOT(logical)
```

| Argumento | Descrição |
|---|---|
| *logical* | Obrigatório. Um valor ou expressão que pode ser avaliado como TRUE ou FALSE. |

A utilização do NOT exige conhecer se as expressões (&lt;, >, =, &lt;> etc.) retornam os valores 0 ou 1.

## Diferente de

Retorna todos os itens que não contêm a correspondência exata do valor inserido.

## Ou (Linha)

Retorna TRUE se qualquer argumento for TRUE, ou FALSE se todos os argumentos forem FALSE.

>[!NOTE]
>
>0 (zero) significa False, e qualquer outro valor é True.

```
OR(logical_test1,[logical_test2],...)
```

| Argumento | Descrição |
|---|---|
| *logical_test1* | Obrigatório. Qualquer valor ou expressão que possa ser avaliado como TRUE ou FALSE. |
| *logical_test2* | Opcional. Condições adicionais que você deseja avaliar como TRUE ou FALSE |

## Pi

Retorna a constante PI, 3,14159265358979, com precisão de 15 dígitos.

```
PI()
```

A função [!DNL PI] não tem argumentos.

## Regressão de potência: coeficiente de correlação (Tabela)

Retorna o coeficiente de correlação *r* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você gostaria de correlacionar a *metric_Y*. |
| *metric_Y* | Uma métrica que você gostaria de correlacionar a *metric_X*. |

## Regressão de potência: intercepto (Tabela)

Retorna o intercepto *b* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão de potência: valor previsto de Y (Linha)

Calcula os valores previstos de [!DNL y] ([!DNL metric_Y]), tendo em conta os valores de [!DNL x] conhecidos ([!DNL metric_X]) e usando o método dos &quot;quadrados mínimos&quot; para calcular linha de melhor ajuste para [!DNL Y = b*X] a.

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão de potência: inclinação (Tabela)

Retorna a inclinação *a* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão quadrática: coeficiente de correlação (Tabela)

Retorna o coeficiente de correlação *r* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você gostaria de correlacionar a *metric_Y*. |
| *metric_Y* | Uma métrica que você gostaria de correlacionar a *metric_X*. |

## Regressão quadrática: intercepto (Tabela)

Retorna o intercepto *b* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão quadrática: valor previsto de Y (Linha)

Calcula os valores previstos de [!DNL y] (metric_Y), tendo em conta os valores de [!DNL x] conhecidos (metric_X) e usando o método dos quadrados mínimos para calcular a linha de melhor ajuste com [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argumento | Descrição |
|---|---|
| *metric_A* | Uma métrica que você designaria como um dado dependente. |
| *metric_B* | Uma métrica que você designaria como um dado dependente. |

## Regressão quadrática: inclinação (Tabela)

Retorna a inclinação *a* entre duas colunas de métrica (*metric_X* e metric_Y) para [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão recíproca: coeficiente de correlação (Tabela)

Retorna o coeficiente de correlação *r* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você gostaria de correlacionar a *metric_Y*. |
| *metric_Y* | Uma métrica que você gostaria de correlacionar a *metric_X*. |

## Regressão recíproca: intercepto (Tabela)

Retorna o intercepto *b* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão recíproca: valor previsto de Y (Linha)

Calcula os valores previstos de [!DNL y] (metric_Y), tendo em conta os valores de [!DNL x] conhecidos (metric_X) e usando o método dos quadrados mínimos para calcular a linha de melhor ajuste usando [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Regressão recíproca: inclinação (Tabela)

Retorna a inclinação *a* entre duas colunas de métrica (*metric_X* e *metric_Y*) para [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argumento | Descrição |
|---|---|
| *metric_X* | Uma métrica que você designaria como um dado dependente. |
| *metric_Y* | Uma métrica que você gostaria de designar como um dado independente. |

## Seno (Linha)

Retorna o seno do ângulo especificado. Se o ângulo estiver em graus, multiplique-o por PI( )/180.

```
SIN(metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja obter o seno. |

## Pontuação T

Alias da pontuação Z; mais especificamente, é o desvio da média dividido pelo desvio padrão

## Teste t

Realiza um teste t m-caudal com pontuação T de col e n graus de liberdade.

A assinatura é `t_test( x, n, m )`. Por baixo, simplesmente chama `m*cdf_t(-abs(x),n)`. (É semelhante à função z-test que executa `m*cdf_z(-abs(x))`.

Aqui, `m` é o número de caudas, e `n` corresponde aos graus de liberdade. Estes devem ser os números (constantes para todo o relatório, isto é, sem alteração em uma base de linha por linha).

`X` é a estatística t-test, será sempre uma fórmula (por exemplo, zscore) com base em uma métrica e será avaliada em cada linha.

O valor de retorno é a probabilidade de exibição da estatística de teste x, dados os graus de liberdade e os números de caudas.

**Exemplos:**

1. Use-o para encontrar outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine-o com `if` para ignorar taxas de devolução muito altas ou baixas e para contar visitas em outro local:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangente

Retorna a tangente do ângulo especificado. Se o ângulo estiver em graus, multiplique-o por PI( )/180.

```
TAN (metric)
```

| Argumento | Descrição |
|---|---|
| *metric* | O ângulo, em radianos, para o qual você deseja obter a tangente. |

## Pontuação Z (Linha)

Retorna a pontuação Z, ou pontuação normal, com base em uma distribuição normal. A pontuação Z é o número de desvios padrão de uma observação a partir da média. Uma pontuação Z de 0 (zero) significa que a pontuação é igual à média. Uma pontuação Z pode ser positiva ou negativa, indicando se está acima ou abaixo da média e o número de desvios padrão.

A equação da pontuação Z é:

![](../assets/z_score.png)

onde [!DNL x] é a pontuação bruta, [!DNL μ] é a média da população e [!DNL σ] é o desvio padrão da população.

>[!NOTE]
>
>[!DNL μ] (mu) e [!DNL σ] (sigma) são automaticamente calculados a partir da métrica.

Pontuação Z (métrica)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argumento </th>
   <th colname="col2" class="entry"> Descrição </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Retorna o valor do seu primeiro argumento diferente de zero. </p> </td>
  </tr>
 </tbody>
</table>

## Teste z

Realiza teste z n-caudal com pontuação Z de A.

Retorna a probabilidade de a linha atual ser vista por acaso na coluna.

>[!NOTE]
>
>O teste z assume que os valores são distribuídos normalmente.

+++

