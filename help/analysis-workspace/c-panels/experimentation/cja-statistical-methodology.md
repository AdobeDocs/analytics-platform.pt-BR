---
source-git-commit: 99b190e1afe7068d11fd9d53c5be72008958a9c2
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---
# Introdução à metodologia estatística no painel Experimentação do CJA

Este artigo descreve os cálculos estatísticos usados pelo painel Experimentação no CJA. O CJA usa métodos estatísticos avançados para calcular **confiança** isso é válido a qualquer momento, permitindo que você execute seus experimentos pelo tempo que desejar e monitore seus resultados continuamente.

Este artigo descreve como os testes A/B funcionam e fornece uma introdução intuitiva ao Adobe ***Sequências de confiança válidas a qualquer momento***. Para os utilizadores especialistas, os detalhes técnicos e as referências são incluídos no final.

## Teste A/B e Causalidade

Os testes A/B são frequentemente descritos como um &quot;padrão-ouro&quot; na avaliação do impacto causal de algum tipo de &quot;intervenção&quot;. Elas são testes aleatórios, o que no contexto de testes online significa que nós expomos alguns usuários selecionados aleatoriamente para uma variação específica de um site, mensagem ou email, e outro conjunto selecionado aleatoriamente de usuários para alguns outros **variante** ou **tratamento**. Após a exposição, medimos o resultado **métrica(s)** estamos interessados em (por exemplo, aberturas de emails, assinaturas ou compras).

Como ilustrado na imagem abaixo, o fato de termos atribuído aleatoriamente usuários a cada grupo de variantes significa que, em média, os grupos compartilharão as mesmas características. Assim, qualquer diferença nos resultados pode ser interpretada como sendo devida às diferenças entre as variantes recebidas, ou seja, podemos estabelecer uma **causa** ligação entre as nossas intervenções e os resultados em que estamos interessados. Isso permite que você tome decisões rigorosas, explicáveis e orientadas por dados na otimização de suas metas de negócios. Portanto, o teste A/B é uma parte fundamental do kit de ferramentas de qualquer profissional de personalização moderno.

<p style="text-align:center;"><img width="75%" src="img/causal-inference-cartoon.png" alt="causal-inf"></p>


Agora, uma questão importante é se quaisquer diferenças observadas são &quot;efeitos reais&quot;, ou surgem devido à aleatoriedade. Intuitivamente, se houver apenas uma pequena diferença nas métricas de resultados entre grupos, isso poderia ter sido observado por acaso, enquanto diferenças maiores são mais prováveis de serem &quot;reais&quot;. O termo técnico aqui é que nossas medições são *estimativas* dos valores reais da média para cada grupo de variantes. As técnicas de inferência estatística nos dão maneiras de quantificar a quantidade de incerteza em nossas estimativas - é aí que os conceitos de **valores p** e **Intervalos de confiança** Surgem, mas para entendê-los, devemos primeiro entender Erros Estatísticos.

## Testes estatísticos e controle de erros

Muitas metodologias de inferência estatística foram projetadas para controlar dois tipos de erros: **Falsos Positivos** (Erros do tipo I) e **Falsos Negativos** (Erros de tipo II). Elas estão ilustradas na tabela abaixo.


<p style="text-align:center;"><img width="50%" src="img/contingency_table_stats_errors.png" alt="ÍndiceTabela"></p>


Um Falso Positivo é uma rejeição incorreta da hipótese nula, quando na verdade é verdadeira. No contexto de testes A/B online, isso significa que nós (falsamente) concluímos que a métrica de negócios do resultado é diferente entre braços de variante, quando na verdade era a mesma. Antes de executar o experimento, geralmente escolhemos um limite *α*. Depois que o experimento tiver corrido, a *p*-value é calculado e rejeitamos null se *p &lt; α*. Um limite comumente usado é *α*= 0,05, o que significa que, a longo prazo, esperamos que 5 de cada 100 experimentos sejam falsos positivos.

Enquanto isso, um falso negativo significa que não rejeitamos a hipótese nula quando, de fato, ela é falsa. Para testes A/B, isso significa que não rejeitamos a hipótese nula (lembrete, a hipótese nula afirma que a métrica de negócios de resultado é a mesma entre braços de variante), quando de fato é diferente. Para controlar esse tipo de erro, geralmente precisamos ter usuários suficientes em nosso experimento para garantir uma certa **Potência**, definido como 1-*β* (isto é, um menos a probabilidade de um erro de tipo II).

A maioria das técnicas de inferência estatística exigirá que você corrija o tamanho da amostra antecipadamente, com base no tamanho do efeito que deseja determinar, bem como a tolerância a erros (*α* e *β*) com antecedência. No entanto, a metodologia Adobe foi projetada para permitir que você veja continuamente seus resultados, qualquer tamanho de amostra.



## Metodologia estatística: _Sequências de confiança válidas a qualquer momento_

Para proporcionar uma inferência estatística fácil de interpretar e segura, o Adobe adotou uma metodologia estatística baseada no [_Sequências de confiança válidas a qualquer momento_](https://doi.org/10.48550/arXiv.2103.06476).

Uma Sequência de confiança é um análogo &quot;sequencial&quot; de um Intervalo de confiança. Para entender o que é uma sequência de confiança, imagine repetir seus experimentos cem vezes e calcular uma estimativa da métrica média de negócios (por exemplo, taxa de abertura de um email) e sua sequência associada de 95% de confiança para *cada novo usuário* que entra no experimento. Uma Sequência de confiança de 95% incluirá o valor &quot;true&quot; da métrica de negócios em 95 dos 100 experimentos executados. (Um intervalo de confiança de 95% só pode ser calculado uma vez por experiência, a fim de dar a mesma garantia de cobertura de 95%; não com cada novo usuário). As Sequências de confiança permitem, portanto, monitorar continuamente as experiências, sem aumentar as taxas de erro Falso Positivo, ou seja, elas permitem &quot;espiar&quot; os resultados.

A diferença entre as sequências de confiança e os intervalos de confiança para um único experimento é mostrada na animação abaixo:

<p style="text-align:center;"><img width="75%" src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


Observamos que as sequências de confiança mudam o foco dos testes A/B para *estimativa* em vez de testar hipóteses, ou seja, focar na estimativa precisa da diferença entre os meios, em vez de rejeitar ou não uma hipótese nula com base em um limite de significância estatística.

No entanto, de maneira semelhante à relação entre valores de $p$ (ou Confiança) e Intervalos de Confiança, também há uma relação entre Sequências de Confiança e a qualquer hora valores de $p$ (ou a qualquer hora de Confiança válida). Dada a familiaridade de quantidades como a Confiança, o CJA fornece a confiança válida em qualquer momento em seus relatórios.

As bases teóricas da Sequência de Confiança vêm do estudo de sequências de variáveis aleatórias conhecidas como martingales. Alguns resultados principais estão incluídos para leitores especialistas abaixo, mas as vantagens para os profissionais são claras:


> As sequências de confiança podem ser interpretadas como analogias sequenciais &quot;seguras&quot; dos intervalos de confiança: você pode observar e interpretar dados em seu teste A/B a qualquer momento que desejar e interromper com segurança ou continuar experimentos. A Confiança válida em qualquer momento (ou *p*-value) também é seguro interpretar.

É importante notar que, dado que a metodologia estatística é &quot;válida em qualquer altura&quot;, será mais conservadora do que uma metodologia de horizonte fixo aplicada com a mesma dimensão de amostra. Isso significa que o &quot;anytime valid&quot; *p*-os valores serão geralmente maiores que o horizonte fixo correspondente *p*-values (ou seja, a confiança válida sempre que for menor)

## Interpretação dos resultados

1. **O experimento é conclusivo**: Cada vez que você visualiza o relatório de experimentação, o Adobe analisa os dados acumulados no experimento até este ponto e declara um experimento como &quot;Conclusivo&quot; quando a confiança válida a qualquer momento ultrapassa um limite de 95% para *pelo menos um* das variantes (com uma correção de Bonferonina aplicada quando há mais de dois braços, para corrigir para testes de hipótese múltipla).

2. **Variante com melhor desempenho**: Quando um experimento é declarado conclusivo, a variante com a maior taxa de conversão é identificada como a &quot;variante com melhor desempenho&quot;. Observe que essa variante deve ser a variante de controle ou de linha de base, ou uma das variantes que cruzam o limite de confiança válido de 95% sempre que necessário (com correções de Bonferonni aplicadas).

3. **Índice de conversão**: A taxa de conversão mostrada é uma relação do valor da métrica de sucesso com o valor da métrica de normalização. Observe que, às vezes, isso pode ser maior que 1, se a métrica não for binária (1 ou 0 para cada unidade no experimento)

4. **Lift**: O resumo do relatório de experiência mostra o Aumento em relação à Linha de Base, que é uma medida da melhora da porcentagem na taxa de conversão de uma determinada variante em relação à linha de base. Definida com precisão, é a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base, expresso como uma porcentagem.

5. **Confiança**: A Confiança válida em qualquer momento que é mostrada é uma medida probabilística de quanta evidência há de que uma determinada variante é a mesma que a variante de controle. Uma confiança mais alta indica menos evidência para o pressuposto de que a variante de controle e não de controle tem desempenho igual. Mais precisamente, a confiança que é exibida é uma probabilidade (expressa como uma porcentagem) de que teríamos observado uma diferença menor nas taxas de conversão entre uma determinada variante e o controle, se na realidade não houver diferença nas taxas de conversão subjacentes verdadeiras. Em termos de *p*-values, a confiança exibida é 1 - *p*-valor.

Note-se, contudo, que uma descrição completa dos resultados deve considerar todos os elementos de prova disponíveis (por exemplo, concepção experimental, dimensões das amostras, taxas de conversão, confiança, etc.) e não apenas a declaração de conclusão ou não. Mesmo quando um resultado ainda não é &quot;conclusivo&quot;, ainda pode haver provas convincentes de que uma variante seja diferente de outra (por exemplo, intervalos de confiança são quase não sobrepostos). Idealmente, a tomada de decisões deve ser informada por todas as provas estatísticas, interpretadas num espectro contínuo.
