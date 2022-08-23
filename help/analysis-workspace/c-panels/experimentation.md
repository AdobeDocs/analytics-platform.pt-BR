---
description: Saiba mais sobre como analisar os resultados de testes A/B no painel Experimentação do CJA.
title: Painel de experiência
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 15ef6bfc1d6600b3795310c208ad46c6f6b52254
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 5%

---

# Painel de experiência

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

O **[!UICONTROL Experimentação]** O painel permite que os analistas comparem diferentes variações de experiência do usuário, marketing ou mensagens para determinar qual é o melhor para impulsionar um resultado específico. Você pode avaliar o aumento e a confiança de qualquer experimento A/B de qualquer plataforma de experimentação - online, offline, de soluções de Adobe, Adobe Journey Optimizer e até mesmo dados BYO (traga seus próprios).

>[!IMPORTANT]
>
>Neste ponto, [Adobe Analytics para Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=pt-BR) (A4T) dados trazidos para o Adobe Experience Platform por meio do Conector de origem do Analytics **cannot** ser analisadas no [!UICONTROL Experimentação] painel. Esperamos uma resolução para esta questão em 2023.

## Controle de acesso

O painel Experimentação está disponível para uso por todos os usuários do Customer Journey Analytics (CJA). Não são necessários direitos de administrador ou outras permissões. No entanto, a configuração (etapas 1 e 2 abaixo) requer ações que somente os Administradores podem executar.

## Etapa 1: Criar conexão com conjuntos de dados de experimento

Depois que seus dados de experimento tiverem sido [ingerido](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=pt-BR) no Adobe Experience Platform, [criar uma conexão no CJA](/help/connections/create-connection.md) para um ou mais conjuntos de dados de experimento.

## Etapa 2: Adicionar rótulos de contexto em visualizações de dados

Nas configurações de exibições de dados do CJA, os administradores podem adicionar [rótulos de contexto](/help/data-views/component-settings/overview.md) para uma dimensão ou métrica e serviços CJA como [!UICONTROL Experimentação] O painel pode usar esses rótulos para suas finalidades. Dois rótulos predefinidos são usados para o painel Experimentação :

* [!UICONTROL Experimento]
* [!UICONTROL Variante]

Na visualização de dados que contém dados de experimentação, escolha duas dimensões, uma com os dados de experimentação e outra com os dados da variante. Em seguida, rotule essas dimensões com o **[!UICONTROL Experimento]** e **[!UICONTROL Variante]** rótulos.

![rótulo de contexto](assets/context-label.png)

Sem esses rótulos presentes, o painel Experimento não funciona, pois não haverá experimentos para trabalhar.

## Etapa 3: Configurar o painel Experimento

1. No CJA Workspace, arraste o painel Experimentação para um projeto.

![painel de experimento](assets/experiment.png)

>[!IMPORTANT]
>Se a configuração necessária nas visualizações de dados do CJA não tiver sido concluída, você receberá uma mensagem para esse efeito antes de continuar.

1. Defina as configurações de entrada do painel.

   | Configuração | Definição |
   | --- | --- |
   | **[!UICONTROL Experimento]** | Um conjunto de variações em uma experiência que foi exposta a usuários finais para determinar qual é melhor manter a perpetuidade. Um experimento é composto por duas ou mais variantes, uma delas considerada variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com a variável  **[!UICONTROL Experimento]** nas visualizações de dados e nos últimos 3 meses de dados experimentais. |
   | **[!UICONTROL Variante de controle]** | Uma de duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. Uma variante deve ser selecionada como controle e somente uma variante pode ser considerada como a variante de controle. Essa configuração é pré-preenchida com as dimensões que foram rotuladas com a variável  **[!UICONTROL Variante]** em visualizações de dados. Essa configuração extrai os dados de variante associados a esse experimento. |
   | **[!UICONTROL Métricas de sucesso]** | A métrica ou métricas com as quais um usuário está comparando variantes. A variante com o resultado mais desejável para a métrica de conversão (mais alta ou mais baixa) é declarada como a &quot;variante com melhor desempenho&quot; de um experimento. Você pode adicionar até 5 métricas. |
   | **[!UICONTROL Métrica de normalização]** | A base ([!UICONTROL Pessoas], [!UICONTROL Sessões]ou [!UICONTROL Eventos]) em que um teste será executado. Por exemplo, um teste pode comparar as taxas de conversão de várias variações, onde **[!UICONTROL Índice de conversão]** é calculada como **[!UICONTROL Conversões por sessão]** ou **[!UICONTROL Conversões por pessoa]**. |
   | **[!UICONTROL Intervalo de datas]** | O intervalo de datas é automaticamente definido, com base na primeira ocorrência recebida no CJA para o experimento selecionado. Você pode restringir ou expandir o intervalo de datas para um período mais específico, se necessário. |

1. Clique em **[!UICONTROL Criar]**.

## Etapa 4: Interpretar a saída do painel

O painel Experimentação retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho de seus experimentos. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou. A qualquer momento, você pode editar o painel clicando no lápis de edição na parte superior direita.

Você também recebe um resumo de texto que indica se o experimento é conclusivo ou não, e resume o resultado. A conclusão baseia-se na significância estatística. (Ver &quot;Metodologia estatística&quot; abaixo.) Você pode ver números de resumo para a variante com melhor desempenho com o maior incentivo e confiança.

>[!NOTE]
>
>O incentivo e a confiança também são [funções de métrica calculada avançadas](/help/components/calc-metrics/cm-adv-functions.md) no CJA, para que você possa criar suas próprias métricas de incentivo e confiança.

![resultado experimental](assets/exp-output1.png)

Para cada métrica de sucesso selecionada, uma tabela de forma livre e uma tendência de taxa de conversão serão mostradas:

![resultado experimental](assets/exp-output2.png)

O [!UICONTROL Linha] o gráfico fornece [!UICONTROL Controle] versus [!UICONTROL Variante de controle] desempenho:

![resultado experimental](assets/exp-output3.png)

>[!NOTE]
>
>No momento, esse painel não oferece suporte à análise de testes A/A.

## Metodologia estatística

Para proporcionar uma inferência estatística fácil de interpretar e segura, o Adobe adotou uma metodologia estatística baseada no [Sequências de confiança válidas a qualquer momento](https://doi.org/10.48550/arXiv.2103.06476).

Uma Sequência de confiança é um análogo &quot;sequencial&quot; de um Intervalo de confiança. Para entender o que é uma sequência de confiança, imagine repetir seus experimentos cem vezes e calcular uma estimativa da métrica média de negócios (por exemplo, taxa de abertura de um email) e sua sequência associada de 95% de confiança para *cada novo usuário* que entra no experimento. Uma Sequência de confiança de 95% incluirá o valor &quot;true&quot; da métrica de negócios em 95 dos 100 experimentos executados. (Um intervalo de confiança de 95% só pode ser calculado uma vez por experiência, a fim de dar a mesma garantia de cobertura de 95%; não com cada novo usuário). As Sequências de confiança permitem, portanto, monitorar continuamente as experiências, sem aumentar as taxas de erro Falso Positivo, ou seja, elas permitem &quot;espiar&quot; os resultados.

### Interpretação dos resultados

1. **O experimento é conclusivo**: Cada vez que você visualiza o relatório de experimentação, o Adobe analisa os dados acumulados no experimento até este ponto e declara um experimento como &quot;Conclusivo&quot; quando a confiança válida a qualquer momento ultrapassa um limite de 95% para *pelo menos um* das variantes (com uma correção de Bonferonina aplicada quando há mais de dois braços, para corrigir para testes de hipótese múltipla).

2. **Variante com melhor desempenho**: Quando um experimento é declarado conclusivo, a variante com a maior taxa de conversão é identificada como a &quot;variante com melhor desempenho&quot;. Observe que essa variante deve ser a variante de controle ou de linha de base, ou uma das variantes que cruzam o limite de confiança válido de 95% sempre que necessário (com correções de Bonferonni aplicadas).

3. **Índice de conversão**: A taxa de conversão mostrada é uma relação do valor da métrica de sucesso com o valor da métrica de normalização. Observe que, às vezes, isso pode ser maior que 1, se a métrica não for binária (1 ou 0 para cada unidade no experimento)

4. **Lift**: O resumo do relatório de experiência mostra o Aumento em relação à Linha de Base, que é uma medida da melhora da porcentagem na taxa de conversão de uma determinada variante em relação à linha de base. Definida com precisão, é a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base, expresso como uma porcentagem.

5. **Confiança**: A Confiança válida em qualquer momento que é mostrada é uma medida probabilística de quanta evidência há de que uma determinada variante é a mesma que a variante de controle. Uma confiança mais alta indica menos evidência para o pressuposto de que a variante de controle e não de controle tem desempenho igual. Mais precisamente, a confiança que é exibida é uma probabilidade (expressa como uma porcentagem) de que teríamos observado uma diferença menor nas taxas de conversão entre uma determinada variante e o controle, se na realidade não houver diferença nas taxas de conversão subjacentes verdadeiras. Em termos de *p*-values, a confiança exibida é 1 - *p*-valor.

Note-se, contudo, que uma descrição completa dos resultados deve considerar todos os elementos de prova disponíveis (por exemplo, concepção experimental, dimensões das amostras, taxas de conversão, confiança, etc.) e não apenas a declaração de conclusão ou não. Mesmo quando um resultado ainda não é &quot;conclusivo&quot;, ainda pode haver provas convincentes de que uma variante seja diferente de outra (por exemplo, intervalos de confiança são quase não sobrepostos). Idealmente, a tomada de decisões deve ser informada por todas as provas estatísticas, interpretadas num espectro contínuo.
