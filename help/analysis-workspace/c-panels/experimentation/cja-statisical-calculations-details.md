---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# Cálculos estatísticos no painel Experimentação do CJA: Detalhes

Esta página documenta os cálculos estatísticos detalhados usados no Painel de Experimentação do CJA. Destina-se a usuários técnicos.


## Taxa de conversão

A taxa de conversão ou **média**, *μ<sub>ν</sub>* para cada variante *ν* em um Experimento é definido como uma proporção da soma da métrica ao número de unidades atribuídas a essa métrica, *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="métrica-média"></p>
Aqui,

- *Y<sub>iν</sub>* é o valor da métrica para cada unidade *i*, que foi atribuída a uma determinada variante *ν*.
- A soma sobre unidades *i* depende da escolha da métrica de normalização.
   - If *Pessoas* é a métrica de normalização, cada unidade é uma pessoa/perfil exclusivo.
   - If *Sessões* é a métrica de normalização, cada unidade é uma sessão exclusiva.
   - If *Eventos* é a métrica de normalização, cada unidade é um evento exclusivo.

Em geral, essa métrica de normalização deve ser considerada equivalente à sua unidade de independência, ou seja, se o comportamento de um usuário em uma sessão for independente do comportamento em outra sessão, as sessões serão uma métrica de normalização razoável.

Sempre que necessário, é usado o desvio padrão da amostra, com a expressão


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="métrica-média"></p>


## Aumento

O aumento entre uma variante  *ν* e a variante de controle  *ν<sub>0</sub>* é o &quot;delta&quot; relativo em taxas de conversão, definidas como
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="métrica-média"></p>
em que as taxas de conversão individuais são as definidas acima.


## Sequências de confiança

Embora não seja exibido no painel Experimentação CJA, a sequência de confiança de uma variante individual *ν* é fundamental para a metodologia estatística utilizada pelo Adobe, pelo que é definida aqui (reproduzida a partir de [Waudby-Smith et al.](https://doi.org/10.48550/arXiv.2103.06476)).

> Suponha que um esteja interessado em estimar um parâmetro de meta *ψ* (como a taxa de conversão de uma variante em um Experimento). Em seguida, a dicotomia entre uma sequência de Intervalos de Confiança de &quot;tempo fixo&quot; (ICs) e uma Sequência de Confiança (CS) uniforme em tempo útil pode ser resumida da seguinte forma:
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="métrica-média"></p>

Em palavras - para um Intervalo de confiança regular , a garantia probabilística de que o parâmetro target está dentro do intervalo de valores *Ċ<sub>t</sub>* é válido somente em um único valor fixo de *n* em que *n* é o número de amostras). Por outro lado, para uma Sequência de confiança, temos garantias de que em todas as ocasiões/em todos os valores do tamanho da amostra *t*, o valor &quot;true&quot; do parâmetro de interesse está dentro dos limites *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

Isso tem algumas implicações profundas que são muito importantes para testes online:
- O CS pode ser atualizado opcionalmente sempre que novos dados estiverem disponíveis.
- Os experimentos podem ser continuamente monitorados, interrompidos de forma adaptável ou continuados.
- O erro de tipo I é controlado em todos os momentos de interrupção, incluindo tempos dependentes de dados.

O Adobe usa Sequências de confiança assintótica, que para uma variante individual com estimativa média *μ* tem o formulário

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="métrica-média"></p>

Em que:
- *N* é o número de unidades para essa variante
- *σ* é uma amostra de estimativa do desvio padrão (definido anteriormente)
- *α* é o nível desejado de erro de tipo I (ou probabilidade de má cobertura)
- *z*<sup> 2</sup> é uma constante que ajusta o tamanho da amostra em que o CS é mais apertado. Adobe escolheu um valor universal de *z*<sup> 2</sup> = 10<sup>-2,8</sup>, que é adequado para os tipos de taxas de conversão observadas em experiências em linha.


## Confiança

A confiança utilizada pelo Adobe é uma confiança &quot;válida em qualquer altura&quot;, que é obtida invertendo a sequência de confiança para o efeito médio do tratamento.

Para ser preciso, notamos que numa amostra de dois *t* teste para a diferença entre médias entre duas variantes, há um mapeamento 1:1 entre a variável *p*-valor para esse teste e o intervalo de confiança para a diferença entre meios. Por analogia, um valor em qualquer hora *p*- o valor pode ser obtido invertendo a sequência de confiança (sempre que válida) para o avaliador do efeito médio de tratamento:
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="métrica-média"></p>

O avaliador que usamos é um avaliador de propensão inversa (IPW) ponderada. Considere *N = N<sub>0</sub>* + *N<sub>1</sub>* unidades, atribuições de variante para cada unidade $i$ rotuladas por *A<sub>i</sub>=0,1* se a unidade estiver atribuída à variante ν=0,1. Se os usuários forem atribuídos com probabilidade fixa (propensão) *ì<sub>0</sub>, (1-λ<sub>0</sub>)* e sua métrica de resultado é *Y<sub>i</sub>*, o avaliador de IPW é
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="métrica-média"></p>

Registrando que *f* é a função de influência, Waudby-Smith et al. mostrou que a Sequência de Confiança desse avaliador é:
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="métrica-média"></p>

Substituição da probabilidade da atribuição pelas suas estimativas empíricas: *ì<sub>0</sub> = N<sub>0</sub>/N*, o termo da variação pode ser expresso em termos de estimativas médias de cada amostra  *μ<sub>{0,1}</sub>* e estimativas de desvio-padrão,  *σ<sub>{0,1}</sub>* como:

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="métrica-média"></p>


Lembrar isso para um teste de hipótese regular com estatística de teste *z = (μ<sub>1</sub> - μ<sub>0</sub>)/ σ<sub>p</sub>*, há uma correspondência entre valores de $p$ e intervalos de confiança:

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="métrica-média"></p>

em que *Φ* é a distribuição cumulativa do normal padrão. Para qualquer hora válida *p*- valores, considerando a sequência de confiança para o efeito médio de tratamento definido acima, podemos inverter essa relação:
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="métrica-média"></p>

Finalmente, o **anytime valid *confiança*** é
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="métrica-média"></p>


## Declarando uma experiência como conclusiva

Para um Experimento com dois braços, o painel Experimentação do CJA exibe uma mensagem declarando que um Experimento é **conclusivo** quando a confiança válida em qualquer momento exceder 95% (ou seja, o valor em qualquer momento *p*-valor é inferior a 5%).

Quando estão presentes mais de duas variantes, é aplicada a correção de Bonferonina. Para um experimento com *K* terapêuticas e um único tratamento de base (controlo), existem *K-1* testes de hipótese independentes. A correção de Bonferonni significa que rejeitamos a hipótese nula de que o controle e uma determinada variante têm meios iguais, se a qualquer momento for válida *p*-value está abaixo de um limite de 0,05/(K-1).


## Braço de melhor desempenho

Quando um experimento é declarado conclusivo, aparece o braço com melhor desempenho. Este é o braço com o melhor desempenho (média ou taxa de conversão mais alta), entre o Conjunto que inclui o controle e todos os braços com um *p*-valor que está abaixo do limite de Bonferonni.