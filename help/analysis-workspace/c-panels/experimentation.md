---
description: Saiba como analisar os resultados de testes A/B no painel Experimentação de Customer Journey Analytics.
title: Painel de experimentação
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 58%

---

# Painel de experimentação

O painel **[!UICONTROL Experimentação]** permite que os analistas comparem diferentes variações de experiência do usuário, marketing ou mensagens para determinar qual é a melhor para gerar um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B de qualquer plataforma de experimentação — online, offline, de soluções da Adobe, do Adobe Journey Optimizer e até mesmo dados BYO (traga os seus próprios).

>[!IMPORTANT]
>
>Neste ponto, [Adobe Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) Dados do (A4T) *não é possível* ser analisadas no painel Experimentação.

## Controle de acesso {#access}

O painel Experimentação está disponível para uso por todos os usuários do Customer Journey Analytics. Não são necessários direitos de administrador ou outras permissões. No entanto, a configuração (etapas 1 e 2 abaixo) requer ações que somente administradores podem executar.

## Novas funções de métricas calculadas {#functions}

Foram adicionadas duas novas funções avançadas: [!UICONTROL Aumento] e [!UICONTROL Confiança]. Para obter mais informações, consulte [Referência - funções avançadas](/help/components/calc-metrics/cm-adv-functions.md).

## Etapa 1: criar conexão com conjuntos de dados de experimento {#connection}

O esquema de dados recomendado é um no qual os dados experimentais estejam em uma [Matriz de objetos](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html) que contém os dados de experimento e variante em duas dimensões separadas. Ambas as dimensões precisam estar em uma **solteiro** matriz de objetos. Se você tiver seus dados de experimento em uma única dimensão com os dados de experimento e variante em uma string delimitada, poderá usar a configuração [substring](/help/data-views/component-settings/substring.md) das visualizações de dados para dividi-los em duas partes para uso no painel.

Após os dados do experimento terem sido [assimilado](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) no Adobe Experience Platform, [criar uma conexão no Customer Journey Analytics](/help/connections/create-connection.md) para um ou mais conjuntos de dados de experimento.

## Etapa 2: adicionar rótulos de contexto em visualizações de dados {#contect-labels}

Nas configurações de visualizações de dados do Customer Journey Analytics, os administradores podem adicionar [rótulos de contexto](/help/data-views/component-settings/overview.md) para uma dimensão ou métrica e serviços de Customer Journey Analytics como [!UICONTROL Experimentação] podem usar esses rótulos para suas finalidades. Dois rótulos predefinidos são usados para o painel Experimentação:

* [!UICONTROL Experimento de experimentação]
* [!UICONTROL Variante de experimentação]

Na visualização de dados que contém dados de experimentação, escolha duas dimensões: uma com os dados de experimentação e outra com os dados da variante. Em seguida, rotule essas dimensões com os rótulos **[!UICONTROL Experimento]** e **[!UICONTROL Variante]**.

![Opções de rótulo de contexto para Variante de experimentação e experimentação.](assets/context-label.png)

Sem a presença desses rótulos, o painel Experimento não funciona, pois não haverá experimentos com os quais trabalhar.

## Etapa 3: configurar o painel Experimento {#configure}

1. No Espaço de trabalho do Customer Journey Analytics, arraste o painel Experimentação para um projeto.

![O painel Experimento foi arrastado para um projeto.](assets/experiment.png)

>[!IMPORTANT]
>Se a configuração necessária nas visualizações de dados do Customer Journey Analytics não tiver sido concluída, essa mensagem será exibida antes que você possa continuar: &quot;[!UICONTROL Configure as dimensões do experimento e da variante em Visualizações de dados]&quot;.

1. Defina as configurações de entrada do painel.

   | Configuração | Definição |
   | --- | --- |
   | **[!UICONTROL Experimento]** | Um conjunto de variações em uma experiência que foi exposto aos usuários finais a fim de determinar qual é a melhor opção a ser mantida como permanente. Um experimento é composto por duas ou mais variantes, sendo uma delas considerada a variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Experimento]** nas visualizações de dados e com os últimos 3 meses de dados experimentais. |
   | **[!UICONTROL Variante de controle]** | Uma de duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. Uma variante deve ser selecionada como controle, e somente uma variante pode ser considerada como a variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Variante]** nas visualizações de dados. Essa configuração extrai os dados de variantes associados a esse experimento. |
   | **[!UICONTROL Métricas de sucesso]** | A métrica, ou as métricas, com as quais um usuário está comparando variantes. A variante com o resultado mais desejável para a métrica de conversão (seja mais alta ou mais baixa) é declarada a “variante com melhor desempenho” de um experimento. Você pode adicionar até 5 métricas. |
   | **[!UICONTROL Métrica de normalização]** | A base ([!UICONTROL Pessoas], [!UICONTROL Sessões] ou [!UICONTROL Eventos]) em que um teste será executado. Por exemplo, um teste pode comparar as taxas de conversão de diversas variações, onde o **[!UICONTROL Índice de conversão]** é calculado como **[!UICONTROL Conversões por sessão]** ou **[!UICONTROL Conversões por pessoa]**. |
   | **[!UICONTROL Intervalo de datas]** | O intervalo de datas é automaticamente definido com base no primeiro evento recebido em Customer Journey Analytics para o experimento selecionado. Você pode restringir ou expandir o intervalo de datas para um período mais específico, se necessário. |

1. Clique em **[!UICONTROL Criar]**.

## Etapa 4: visualizar a saída do painel {#view}

O painel Experimentação retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho de seus experimentos. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou. A qualquer momento, você pode editar o painel clicando no lápis de edição na parte superior direita.

Você também recebe um resumo de texto que indica se o experimento é conclusivo ou não e resume o resultado. A conclusão baseia-se na significância estatística. (Consulte “Metodologia estatística” abaixo.) Você pode ver números de resumo para a variante de melhor desempenho, com o maior aumento e confiança.

Para cada métrica de sucesso selecionada, uma tabela de forma livre e uma tendência de taxa de conversão serão mostradas.

![A saída da experimentação que mostra uma tabela de forma livre e uma tendência de taxa de conversão.](assets/exp-output1.png)

O gráfico de [!UICONTROL Linha] fornece o desempenho do [!UICONTROL Controle] em comparação com a [!UICONTROL Variante de controle]:

![A saída do gráfico de linhas que mostra o desempenho do Controle em comparação com a Variante de controle.](assets/exp-output2.png)

>[!NOTE]
>
>No momento, esse painel não é compatível com a análise de testes A/A.

## Etapa 5: interpretar os resultados {#interpret}

1. **O experimento é conclusivo**: Toda vez que você visualiza o relatório de experimentação, o Adobe analisa os dados acumulados no experimento até o momento e declara um experimento como &quot;Conclusivo&quot; quando a confiança válida a qualquer momento ultrapassa um limite de 95% para *pelo menos um* das variantes (com uma correção de Benjamini-Hochberg aplicada quando há mais de dois braços, para corrigir para testes de hipótese múltipla).

2. **Variante com melhor desempenho**: quando um experimento é declarado conclusivo, a variante com a maior taxa de conversão é rotulada como a “variante com melhor desempenho”. Observe que essa variante deve ser a variante de controle ou de linha de base, ou uma das variantes que cruzam o limite de confiança válido a qualquer momento de 95% (com as correções de Benjamini-Hochberg aplicadas).

3. **Índice de conversão**: o índice de conversão mostrado é uma relação do valor da métrica de sucesso com o valor da métrica de normalização. Observe que, às vezes, isso pode ser maior que 1 se a métrica não for binária (1 ou 0 para cada unidade no experimento)

4. **Aumento**: o resumo do relatório de Experimento mostra o aumento em relação à linha de base, que é uma medida da melhora da porcentagem no índice de conversão de uma determinada variante em relação à linha de base. Para definir com precisão, é a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base expresso como uma porcentagem.

5. **Confiança**: a confiança válida a qualquer momento que é mostrada é uma medida probabilística de quanta evidência existe de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual. Mais precisamente, a confiança exibida é uma probabilidade (expressa como uma porcentagem) que teríamos observado uma diferença menor nos índices de conversão entre uma determinada variante e o controle, se na realidade não houver diferença nos verdadeiros índices de conversão subjacentes. Em termos de valores-*p*, a confiança exibida é de 1 - valor-*p*.

>[!NOTE]
>
>Uma descrição completa dos resultados deve considerar todas as evidências disponíveis (ou seja, o design do experimento, tamanhos das amostras, taxas de conversão, confiança etc.) e não apenas se é conclusivo ou não. Mesmo que um resultado ainda não seja “conclusivo”, é possível que haja evidências convincentes de que uma variante seja diferente de outra (por exemplo, intervalos de confiança que quase não se sobrepõem). Idealmente, a tomada de decisões deve ser informada por todas as evidências estatísticas, interpretadas em um espectro contínuo.

## Metodologia estatística da Adobe {#statistics}

Para proporcionar uma inferência estatística fácil de interpretar e segura, a Adobe adotou uma metodologia estatística baseada em [Sequências de confiança válidas a qualquer momento](https://doi.org/10.48550/arXiv.2103.06476).

Uma sequência de confiança é um análogo “sequencial” de um intervalo de confiança. Para entender o que é uma sequência de confiança, imagine repetir seus experimentos cem vezes e calcular uma estimativa da métrica média de negócios (por exemplo, a taxa de abertura de um email) e sua sequência associada de 95% de confiança para *cada novo usuário* que entra no experimento.

Uma sequência de confiança de 95% incluirá o valor “true” da métrica de negócios em 95 dos 100 experimentos executados. (Um intervalo de confiança de 95% só pode ser calculado uma vez por experimento a fim de dar a mesma garantia de cobertura de 95%; não com cada novo usuário). As Sequências de confiança permitem, portanto, monitorar continuamente os experimentos sem aumentar as índice de erro falso positivo. Ou seja, elas permitem “espiar” os resultados.

## Interpretar dimensões não aleatórias {#non-randomized}

O Customer Journey Analytics permite que os analistas selecionem qualquer dimensão como o &quot;experimento&quot;. Mas como você interpreta uma análise em que a dimensão escolhida como experimento não é aquela para a qual as pessoas são aleatórias?

Por exemplo, considere um anúncio que uma pessoa vê. Você pode estar interessado em medir a alteração em alguma métrica (por exemplo, receita média) se decidir mostrar às pessoas &quot;anúncio B&quot; em vez de &quot;anúncio A&quot;. O efeito causal de apresentar o anúncio B em vez do anúncio A é de importância fundamental para chegar à decisão de comercialização. Esse efeito causal pode ser medido como a receita média sobre toda a população, se substituirmos o status quo de exibição do anúncio A pela estratégia alternativa de exibição do anúncio B.

O teste A/B é o padrão ouro no setor para medir objetivamente os efeitos de tais intervenções. A razão crítica pela qual um teste A/B dá origem a uma estimativa causal é devido à aleatoriedade das pessoas para receberem uma das variantes possíveis.

Agora, considere uma dimensão que não é alcançada por aleatoriedade, por exemplo, o estado da pessoa nos EUA. Digamos que nossas pessoas vêm principalmente de dois estados, Nova York e Califórnia. A receita média das vendas de uma marca de roupas de inverno pode ser diferente nos dois estados devido às diferenças no clima regional. Em tal situação, o clima pode ser o verdadeiro fator causal por trás das vendas de roupas de inverno, e não o fato de os estados geográficos das pessoas serem diferentes.

O painel de experimentação em Customer Journey Analytics permite analisar dados como a diferença média de receita por estados das pessoas. Em tal situação, o resultado não tem uma interpretação causal. No entanto, essa análise pode ainda ser de interesse. Fornece uma estimativa (juntamente com medidas de incerteza) da diferença na receita média por estados das pessoas. Isso também é conhecido como &quot;Teste de Hipótese Estatística&quot;. O resultado dessa análise pode ser interessante, mas não necessariamente acionável, já que não e, às vezes, não podemos aleatoriamente tornar as pessoas em um dos valores possíveis da dimensão.

A ilustração a seguir contrasta essas situações:

![Um diagrama mostrando os dados observacionais e o experimento aleatório.](assets/randomize.png)

Quando você quiser medir o impacto da intervenção X no resultado Y, é possível que a causa real de ambos seja o fator de confusão C. Se os dados não são obtidos por pessoas randomizadas em X, o impacto é mais difícil de medir, e a análise irá explicar explicitamente C. A randomização quebra a dependência de X em C, permitindo-nos medir o efeito de X em Y sem ter que se preocupar com outras variáveis.

## Usar métricas calculadas no painel Experimentação

Consulte esta publicação do blog para obter mais informações sobre [uso de métricas derivadas no painel Experimentação](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
