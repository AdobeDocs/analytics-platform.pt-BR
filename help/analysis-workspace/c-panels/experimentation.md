---
description: Saiba como analisar os resultados de testes A/B no painel de experimentação do CJA.
title: Painel de experimentação
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 967348b321525c50b292339de875fd4976d8b10a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Painel de experimentação

O painel **[!UICONTROL Experimentação]** permite que os analistas comparem diferentes variações de experiência do usuário, marketing ou mensagens para determinar qual é a melhor para gerar um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B de qualquer plataforma de experimentação — online, offline, de soluções da Adobe, do Adobe Journey Optimizer e até mesmo dados BYO (traga os seus próprios).

>[!IMPORTANT]
>
>No momento, os dados do [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) (A4T) trazidos para a Adobe Experience Platform por meio do Conector de origem do Analytics **não podem** ser analisados no painel [!UICONTROL Experimentação]. Esperamos uma solução para esta questão em 2023.

## Controle de acesso

O painel Experimentação está disponível para uso por todos os usuários do Customer Journey Analytics (CJA). Não são necessários direitos de administrador ou outras permissões. No entanto, a configuração (etapas 1 e 2 abaixo) requer ações que somente administradores podem executar.

## Etapa 1: criar conexão com conjuntos de dados de experimento

O esquema de dados recomendado é um no qual os dados experimentais estejam em uma [Matriz de objetos](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html?lang=pt-BR) que contém os dados de experimento e variante em duas dimensões separadas. Se você tiver seus dados de experimento em uma única dimensão com os dados de experimento e variante em uma string delimitada, poderá usar a configuração [substring](/help/data-views/component-settings/substring.md) das visualizações de dados para dividi-los em duas partes para uso no painel.

Depois que seus dados de experimento tiverem sido [ingeridos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) pela Adobe Experience Platform, [crie uma conexão no CJA](/help/connections/create-connection.md) para um ou mais conjuntos de dados de experimento.

## Etapa 2: adicionar rótulos de contexto em visualizações de dados

Nas configurações de visualizações de dados do CJA, os administradores podem adicionar [rótulos de contexto](/help/data-views/component-settings/overview.md) a uma dimensão ou métrica, e serviços do CJA, como o painel [!UICONTROL Experimentação], podem usar esses rótulos para suas finalidades. Dois rótulos predefinidos são usados para o painel Experimentação:

* [!UICONTROL Experimento de experimentação]
* [!UICONTROL Variante de experimentação]

Na visualização de dados que contém dados de experimentação, escolha duas dimensões: uma com os dados de experimentação e outra com os dados da variante. Em seguida, rotule essas dimensões com os rótulos **[!UICONTROL Experimento]** e **[!UICONTROL Variante]**.

![rótulo do contexto](assets/context-label.png)

Sem a presença desses rótulos, o painel Experimento não funciona, pois não haverá experimentos com os quais trabalhar.

## Etapa 3: configurar o painel Experimento

1. No Workspace do CJA, arraste o painel Experimentação para um projeto.

![painel de experimento](assets/experiment.png)

>[!IMPORTANT]
>Se a configuração necessária nas visualizações de dados do CJA não tiver sido concluída, essa mensagem será exibida antes que você possa continuar: “[!UICONTROL Configure as dimensões de experimento e variante nas visualizações de dados]”.

1. Defina as configurações de entrada do painel.

   | Configuração | Definição |
   | --- | --- |
   | **[!UICONTROL Experimento]** | Um conjunto de variações em uma experiência que foi exposto aos usuários finais a fim de determinar qual é a melhor opção a ser mantida como permanente. Um experimento é composto por duas ou mais variantes, sendo uma delas considerada a variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Experimento]** nas visualizações de dados e com os últimos 3 meses de dados experimentais. |
   | **[!UICONTROL Variante de controle]** | Uma de duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. Uma variante deve ser selecionada como controle, e somente uma variante pode ser considerada como a variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Variante]** nas visualizações de dados. Essa configuração extrai os dados de variantes associados a esse experimento. |
   | **[!UICONTROL Métricas de sucesso]** | A métrica, ou as métricas, com as quais um usuário está comparando variantes. A variante com o resultado mais desejável para a métrica de conversão (seja mais alta ou mais baixa) é declarada a “variante com melhor desempenho” de um experimento. Você pode adicionar até 5 métricas. |
   | **[!UICONTROL Métrica de normalização]** | A base ([!UICONTROL Pessoas], [!UICONTROL Sessões] ou [!UICONTROL Eventos]) em que um teste será executado. Por exemplo, um teste pode comparar as taxas de conversão de diversas variações, onde o **[!UICONTROL Índice de conversão]** é calculado como **[!UICONTROL Conversões por sessão]** ou **[!UICONTROL Conversões por pessoa]**. |
   | **[!UICONTROL Intervalo de datas]** | O intervalo de datas é automaticamente definido com base na primeira ocorrência recebida no CJA para o experimento selecionado. Você pode restringir ou expandir o intervalo de datas para um período mais específico, se necessário. |

1. Clique em **[!UICONTROL Criar]**.

## Etapa 4: visualizar a saída do painel

O painel Experimentação retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho de seus experimentos. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou. A qualquer momento, você pode editar o painel clicando no lápis de edição na parte superior direita.

Você também recebe um resumo de texto que indica se o experimento é conclusivo ou não e resume o resultado. A conclusão baseia-se na significância estatística. (Consulte “Metodologia estatística” abaixo.) Você pode ver números de resumo para a variante de melhor desempenho, com o maior aumento e confiança.

Para cada métrica de sucesso selecionada, uma tabela de forma livre e uma tendência de taxa de conversão serão mostradas.

![saída do experimento](assets/exp-output1.png)

O gráfico de [!UICONTROL Linha] fornece o desempenho do [!UICONTROL Controle] em comparação com a [!UICONTROL Variante de controle]:

![saída do gráfico de linhas](assets/exp-output2.png)

>[!NOTE]
>
>No momento, esse painel não é compatível com a análise de testes A/A.

## Etapa 5: interpretar os resultados

1. **O experimento é conclusivo**: cada vez que você visualiza o relatório de experimentação, a Adobe analisa os dados acumulados no experimento até o momento e declara um experimento como “Conclusivo” quando a confiança válida a qualquer momento ultrapassa um limite de 95% em *pelo menos uma* das variantes (com uma correção de Bonferonni aplicada quando há mais de dois braços a serem corrigidos para testes de hipótese múltipla).

2. **Variante com melhor desempenho**: quando um experimento é declarado conclusivo, a variante com a maior taxa de conversão é rotulada como a “variante com melhor desempenho”. Observe que essa variante deve ser a variante de controle ou de linha de base, ou uma das variantes que cruzam o limite de confiança válido a qualquer momento de 95% (com as correções de Bonferonni aplicadas).

3. **Índice de conversão**: o índice de conversão mostrado é uma relação do valor da métrica de sucesso com o valor da métrica de normalização. Observe que, às vezes, isso pode ser maior que 1 se a métrica não for binária (1 ou 0 para cada unidade no experimento)

4. **Aumento**: o resumo do relatório de Experimento mostra o aumento em relação à linha de base, que é uma medida da melhora da porcentagem no índice de conversão de uma determinada variante em relação à linha de base. Para definir com precisão, é a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base expresso como uma porcentagem.

5. **Confiança**: a confiança válida a qualquer momento que é mostrada é uma medida probabilística de quanta evidência existe de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual. Mais precisamente, a confiança exibida é uma probabilidade (expressa como uma porcentagem) que teríamos observado uma diferença menor nos índices de conversão entre uma determinada variante e o controle, se na realidade não houver diferença nos verdadeiros índices de conversão subjacentes. Em termos de valores-*p*, a confiança exibida é de 1 - valor-*p*.

>[!NOTE]
>
>Uma descrição completa dos resultados deve considerar todas as evidências disponíveis (ou seja, o design do experimento, tamanhos das amostras, taxas de conversão, confiança etc.) e não apenas se é conclusivo ou não. Mesmo que um resultado ainda não seja “conclusivo”, é possível que haja evidências convincentes de que uma variante seja diferente de outra (por exemplo, intervalos de confiança que quase não se sobrepõem). Idealmente, a tomada de decisões deve ser informada por todas as evidências estatísticas, interpretadas em um espectro contínuo.

## Metodologia estatística da Adobe

Para proporcionar uma inferência estatística fácil de interpretar e segura, a Adobe adotou uma metodologia estatística baseada em [Sequências de confiança válidas a qualquer momento](https://doi.org/10.48550/arXiv.2103.06476).

Uma sequência de confiança é um análogo “sequencial” de um intervalo de confiança. Para entender o que é uma sequência de confiança, imagine repetir seus experimentos cem vezes e calcular uma estimativa da métrica média de negócios (por exemplo, a taxa de abertura de um email) e sua sequência associada de 95% de confiança para *cada novo usuário* que entra no experimento.

Uma sequência de confiança de 95% incluirá o valor “true” da métrica de negócios em 95 dos 100 experimentos executados. (Um intervalo de confiança de 95% só pode ser calculado uma vez por experimento a fim de dar a mesma garantia de cobertura de 95%; não com cada novo usuário). As Sequências de confiança permitem, portanto, monitorar continuamente os experimentos sem aumentar as índice de erro falso positivo. Ou seja, elas permitem “espiar” os resultados.

## Novas funções em Métricas calculadas

Foram adicionadas duas novas funções avançadas: [!UICONTROL Lift] e [!UICONTROL Confiança]. Para obter mais informações, consulte [Referência - funções avançadas](/help/components/calc-metrics/cm-adv-functions.md).