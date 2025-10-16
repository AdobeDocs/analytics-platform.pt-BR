---
description: Saiba como analisar os resultados dos testes A/B no painel Experimentação do Customer Journey Analytics.
title: Painel de experimentação
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: b013518d8f1782219dd2cf9e5b5a89b877e3b92d
workflow-type: tm+mt
source-wordcount: '2175'
ht-degree: 98%

---

# Painel de experimentação {#experimentation-panel}

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="Experimentação"
>abstract="Crie um painel para comparar diferentes variações de experiências de usuário, marketing ou mensagens. E para determinar qual variação é a melhor para gerar um resultado específico."

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="Experimentação"
>abstract="Compare diferentes variações de experiências de usuário, marketing ou mensagens para determinar qual é melhor para gerar um resultado específico. Especifique o experimento, a variante de controle para comparação, a métrica de sucesso e a métrica de normalização. Opcionalmente, defina um limite de confiança superior e inferior."


>[!BEGINSHADEBOX]

_Este artigo documenta o painel Experimentação no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_Consult oe [Painel do Analytics for Target](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) para obter informações sobre como analisar atividades e experiências do Adobe Target no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._

>[!ENDSHADEBOX]


O painel **[!UICONTROL Experimentação]** permite que analistas comparem diferentes experiências de usuários, marketing ou variações de mensagens para determinar qual é melhor para gerar um resultado específico. Você pode avaliar a elevação e a confiança de qualquer experimento A/B em qualquer plataforma de experimentação: online, offline, de soluções da Adobe como Target ou Journey Optimizer, e até mesmo dados BYO (traga seus próprios dados).

Leia mais sobre a [integração entre o Adobe Customer Journey Analytics e o Adobe Target](https://experienceleague.adobe.com/pt-br/docs/target/using/integrate/cja/target-reporting-in-cja).

## Controle de acesso {#access}

O painel Experimentação está disponível para uso por todos os usuários do Customer Journey Analytics. Não são necessários direitos de administrador ou outras permissões. No entanto, os pré-requisitos exigem ações que somente administradores podem executar.

## Funções em métricas calculadas

Duas funções avançadas estão disponíveis: Aumento e Confiança. Para obter mais informações, consulte [Referência - funções avançadas](/help/components/calc-metrics/cm-adv-functions.md).

## Pré-requisitos

Para usar o painel de experimentação, siga estes pré-requisitos:

### Criar conexão com conjuntos de dados de experimento

O esquema de dados recomendado é que os dados de experimentação estejam em uma [matriz de objetos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/array) que contenha os dados do experimento e da variante em duas dimensões separadas. Ambas as dimensões precisam estar em uma **única** matriz de objetos. Se você tiver seus dados de experimentação em uma única dimensão (com dados de experimento e variantes em uma string delimitada), você pode usar a configuração [substring](/help/data-views/component-settings/substring.md) nas exibições de dados para dividir a dimensão em duas para uso no painel.


Depois que seus dados de experimentação forem [assimilados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/ingestion/home) na Adobe Experience Platform, [crie uma conexão no Customer Journey Analytics](/help/connections/create-connection.md) com um ou mais conjuntos de dados de experimento.

### Adicionar rótulos de contexto em visualizações de dados

Nas configurações de exibições de dados do Customer Journey Analytics, os administradores podem adicionar [rótulos de contexto](/help/data-views/component-settings/overview.md) a uma dimensão ou métrica, e os serviços do Customer Journey Analytics, como o painel [!UICONTROL Experimentação], podem usar esses rótulos para seus propósitos. Dois rótulos predefinidos são usados para o painel Experimentação:

* [!UICONTROL Experimento de experimentação]
* [!UICONTROL Variante de experimentação]

Na exibição de dados que contém dados de experimentação, escolha duas dimensões, uma com os dados de experimentação e outra com os dados de variantes. Em seguida, rotule essas dimensões com os rótulos **[!UICONTROL Experimento de experimentação]** e **[!UICONTROL Variante de experimentação]**.

![Opções de rótulo de contexto para Experimentação e Variante de Experimentação.](assets/context-label.png)

Sem a presença desses rótulos, o painel Experimento não funciona, pois não haverá experimentos com os quais trabalhar.

## Usar

Para usar um painel de **[!UICONTROL Experimentação]**:

1. Crie um painel de **[!UICONTROL Experimentação]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).


1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

   >[!IMPORTANT]
   >
   >Se a configuração necessária nas exibições de dados do Customer Journey Analytics não tiver sido concluída, você receberá esta mensagem antes de prosseguir: [!UICONTROL Configure as dimensões do experimento e da variante nas exibições de dados].
   >

### Entrada do painel

Usar o painel de experimentação:

1. Defina as configurações de entrada do painel:

   ![O painel Experimentação foi arrastado para um projeto.](assets/experiment-input.png)

   | Configuração | Definição |
   | --- | --- |
   | **[!UICONTROL Intervalo de datas]** | O intervalo de datas do painel Experimentação é definido automaticamente com base no primeiro evento recebido no Customer Journey Analytics para o experimento selecionado. Você pode restringir ou expandir o intervalo de datas para um período mais específico, se necessário. |
   | **[!UICONTROL Experimento]** | Um conjunto de variações de uma experiência que foram expostas aos usuários finais para determinar qual é melhor manter perpetuamente. Um experimento é composto por duas ou mais variantes, sendo uma delas considerada a variante de controle. Esta configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Experimento]** nas exibições de dados e os últimos 6 meses de dados de experimentação. |
   | **[!UICONTROL Variante de controle]** | Uma de duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. Uma variante deve ser selecionada como controle, e somente uma variante pode ser considerada como a variante de controle. Esta configuração é pré-preenchida com as dimensões que foram rotuladas com o rótulo **[!UICONTROL Variante]** nas exibições de dados. Essa configuração extrai os dados de variantes associados a esse experimento. |
   | **[!UICONTROL Métricas de sucesso]** ➊ | A métrica, ou as métricas, com as quais um usuário está comparando variantes. A variante com o resultado mais desejável para a métrica de conversão (seja o mais alto ou o mais baixo) é declarada a *variante de melhor desempenho* de um experimento. Você pode adicionar até 5 métricas. |
   | **[!UICONTROL Normalizando métrica]** ➋ | A base (**[!UICONTROL Conta global]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Conta]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Grupo de compra]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Pessoas]**, **[!UICONTROL Sessões]** ou **[!UICONTROL Eventos]**) sobre a qual um teste é executado. Por exemplo, um teste pode comparar as taxas de conversão de diversas variações, e a **[!UICONTROL Taxa de conversão]** é calculada como visualizações de página. |
   | **[!UICONTROL Incluir limites superiores/inferiores de confiança]** | Habilite esta opção para mostrar limites superiores e inferiores para níveis de confiança. |


1. Selecione **[!UICONTROL Criar]**.

### Saída do painel

O painel Experimentação retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho de seus experimentos. Na parte superior do painel, são fornecidas visualizações de [alterações de resumo](../visualizations/summary-number-change.md) para lembrá-lo das configurações do painel selecionadas. A qualquer momento, você pode editar o painel selecionando o lápis de edição no canto superior direito.

Você também recebe um resumo de texto que indica se o experimento é conclusivo ou não e resume o resultado. A conclusão se baseia na significância estatística (consulte [Metodologia estatística](#adobes-statistical-methodology)). Você pode ver números resumidos para a variante de melhor desempenho com maior elevação e confiança.

Para cada métrica de sucesso selecionada, uma visualização de [tabela de forma livre](../visualizations/freeform-table/freeform-table.md) e uma visualização da [linha](../visualizations/line.md) da taxa de conversão são mostradas.

![A saída da Experimentação mostra uma tabela de forma livre e uma tendência de taxa de conversão.](assets/experiment-output.png)


>[!NOTE]
>
>No momento, esse painel não é compatível com a análise de testes A/A.

#### Interpretar os resultados

1. **O experimento é conclusivo**: cada vez que você exibe o relatório de experimentação, os dados acumulados no experimento até o momento são analisados. A análise declara que um experimento é conclusivo quando a confiança válida a *qualquer momento* cruza um limite de 95% para *pelo menos* uma das variantes. Com mais de dois braços, uma correção de Benjamini-Hochberg é aplicada para corrigir testes de hipótese múltipla.

2. **Variante com melhor desempenho**: quando um experimento é declarado conclusivo, a variante com a maior taxa de conversão é rotulada como a variante com melhor desempenho. Observe que esta variante deve ser a variante de controle ou de linha de base, ou uma das variantes que cruza o limite de confiança válido de 95% *a qualquer momento* (com correções de Benjamini-Hochberg aplicadas).

3. **Taxa de conversão**: a taxa de conversão mostrada é uma relação do valor da métrica de sucesso ➊ com o valor da métrica de normalização ➋. Observe que esse valor pode ser maior que 1, se a métrica não for binária (1 ou 0 para cada unidade no experimento)

4. **Aumento**: o resumo do relatório do experimento mostra o aumento sobre a linha de base, que é uma medida da porcentagem de melhoria na taxa de conversão de uma determinada variante em relação à linha de base. Para definir com precisão, é a diferença no desempenho entre uma determinada variante e a linha de base, dividida pelo desempenho da linha de base expresso como uma porcentagem.

5. **Confiança**: a confiança válida a qualquer momento que é mostrada é uma medida probabilística de quanta evidência há de que uma determinada variante é a mesma que a variante de controle. Uma confiança maior indica menos evidência para o pressuposto de que as variantes de controle e de não controle têm desempenho igual. A confiança é uma probabilidade (expressa como uma porcentagem) que você teria observado uma diferença menor nas taxas de conversão entre uma determinada variante e o controle. Embora, na realidade, não haja diferença entre as verdadeiras taxas de conversão subjacentes. Em termos de valores-*p*, a confiança exibida é de 1 - valor-*p*.

>[!NOTE]
>
>Uma descrição completa dos resultados deve considerar todas as evidências disponíveis (por exemplo, design do experimento, tamanhos de amostra, taxas de conversão, confiança e outros), e não apenas a declaração de conclusivo ou não. Mesmo quando um resultado ainda não é conclusivo, pode haver evidências convincentes de que uma variante é diferente de outra (por exemplo, os intervalos de confiança são quase não sobrepostos). Idealmente, todas as evidências estatísticas, interpretadas em um espectro contínuo, devem informar a tomada de decisões.

## Metodologia estatística da Adobe {#statistics}

Para proporcionar uma inferência estatística fácil de interpretar e segura, a Adobe adotou uma metodologia estatística baseada em [Sequências de confiança válidas a qualquer momento](https://arxiv.org/abs/2103.06476).

Uma sequência de confiança é um análogo *sequencial* de um intervalo de confiança. Para entender o que é uma sequência de confiança, imagine que você repita seus experimentos cem vezes. E calcule uma estimativa da métrica média de negócios (por exemplo, a taxa de abertura de um email) e sua sequência de confiança de 95% associada para *cada novo usuário* que entra no experimento.

Uma sequência de confiança de 95% inclui o valor “verdadeiro” da métrica de negócios em 95 dos 100 experimentos que você executou. (Um intervalo de confiança de 95% só pôde ser calculado uma vez por experimento para dar a mesma garantia de cobertura de 95%; não com cada novo usuário). As sequências de confiança permitem, portanto, monitorar experimentos continuamente, sem aumentar as taxas de erro de falsos positivos, ou seja, permitem “espiar” os resultados.

## Interpretar dimensões não aleatórias {#non-randomized}

O Customer Journey Analytics permite que analistas selecionem qualquer dimensão como experimento. Mas como você interpreta uma análise em que a dimensão escolhida como experimento não é aquela para a qual as pessoas são randomizadas?

Por exemplo, considere um anúncio que uma pessoa vê. Você pode estar interessado em medir a mudança em alguma métrica (por exemplo, receita média) se decidir mostrar às pessoas o *anúncio B* em vez do *anúncio A*. O efeito causal de exibir o anúncio B, em vez do anúncio A, é de importância central para chegar à decisão de marketing. Esse efeito causal pode ser medido como a receita média de toda a população, se você substituísse o status quo de exibir o anúncio A pela estratégia alternativa de exibir o anúncio B.

O teste A/B é o padrão ouro no setor para medir objetivamente os efeitos dessas intervenções. A razão crítica pela qual um teste A/B dá origem a uma estimativa causal é devido à randomização de pessoas para receber uma das variantes possíveis.

Agora, considere uma dimensão que não é alcançada pela randomização, por exemplo, o estado da pessoa nos EUA. As pessoas vêm principalmente de dois estados, Nova York e Califórnia. A receita média de vendas de uma marca de roupas de inverno pode ser diferente nos dois estados devido às diferenças climáticas regionais. Em tal situação, o clima pode ser o verdadeiro fator causal por trás das vendas de roupas de inverno, e não o fato de que os estados geográficos das pessoas são diferentes.

O painel de experimentação no Customer Journey Analytics permite que você analise dados como diferença média de receita por estados das pessoas. Nesta situação, a saída não tem uma interpretação causal. No entanto, essa análise ainda pode ser interessante. Fornece uma estimativa (junto com medidas de incerteza) da diferença na receita média por estado das pessoas.  Este valor também é conhecido como *Teste de hipótese estatística*. O resultado desta análise pode ser interessante, mas não necessariamente útil. Simplesmente porque você não randomizou e às vezes não pode randomizar pessoas para um dos valores possíveis da dimensão.

A ilustração a seguir contrasta essas situações:

![Um diagrama mostrando dados observacionais e o experimento randomizado.](assets/randomize.png)

Quando você quer medir o impacto da intervenção X no resultado Y, é possível que a causa real de ambos seja o fator de confusão C. Se os dados não forem obtidos pela randomização de pessoas em X, o impacto será mais difícil de medir, e a análise levará explicitamente em conta C. A randomização quebra a dependência de X em C, permitindo medir o efeito de X em Y sem ter que nos preocupar com outras variáveis.

## Usar métricas calculadas na experimentação {#use-in-experimentation}

>[!NOTE]
>
>Para organizações que usam o Customer Journey Analytics e o Adobe Journey Optimizer, as informações nesta seção também se aplicam aos recursos de experimentação do Journey Optimizer.

Nem todas as métricas calculadas são compatíveis com o painel Experimentação.

Métricas calculadas que incluem qualquer uma das seguintes métricas ou constantes não são compatíveis com o painel Experimentação:

* Métricas base de um [conjunto de dados resumidos](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/summary-data)
* Métricas base que são divididas entre si ou multiplicadas juntas (por exemplo, `Revenue`/`Orders`)
* Constantes que são adicionadas ou subtraídas de uma métrica base (por exemplo, `Revenue+50`)
* Qualquer uma das seguintes métricas base:
   * Pessoas

Métricas calculadas que não são compatíveis com o painel Experimentação têm o valor [!UICONTROL **Em todos os lugares no Customer Journey Analytics (excluindo experimentação)**] no campo [!UICONTROL **Compatibilidade do produto**] ao criar a métrica calculada. Para obter informações sobre como criar uma métrica calculada, consulte [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Usar métricas calculadas no painel Experimentação

Consulte esta publicação do blog para obter informações sobre [como usar métricas calculadas no painel Experimentação](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).

>[!MORELIKETHIS]
>[Domínio da experimentação do Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
