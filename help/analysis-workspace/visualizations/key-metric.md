---
description: Use a visualização do resumo da métrica principal para comparar o desempenho da métrica em duas linhas do tempo.
title: Resumo da métrica principal
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 41%

---

# Resumo da métrica principal {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="Resumo da métrica principal"
>abstract="Crie uma visualização que seja uma combinação dos gráficos de linha, alteração de resumo e número de resumo. Use essa visualização para comparar a tendência das métricas importantes entre dois períodos."

<!-- markdownlint-enable MD034 -->


A visualização do ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric summary]** permite ver a tendência de uma métrica importante em um único período. Ela também permite comparar o desempenho da métrica em dois intervalos de tempo. Ela oferece os benefícios de várias visualizações combinadas em uma única visualização:

* A visualização de **[!UICONTROL Linha]** mostra a tendência da métrica para os intervalos de datas principal e de comparação

* **[!UICONTROL Alteração percentual do resumo]** mostra o aumento ou a diminuição da métrica entre os intervalos de datas principal e de comparação

* Valor total atual ([!UICONTROL **número do resumo**]) para a métrica

Essa visualização aborda uma variedade de casos de uso comuns, incluindo:

* Um analista tentando entender como a criação de oportunidades parecia este mês em comparação com o mesmo período do ano passado.

* Um comerciante que explora como a geração de clientes potenciais para um tipo de cliente potencial específico mudou este mês em comparação com o mês anterior.

* Um executivo querendo entender como novas reservas mudaram este trimestre em comparação com o trimestre anterior.

## Usar

1. Adicionar uma visualização de ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL Key metric]**. Consulte [Adicionar uma visualização a um painel](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Configure a visualização selecionando uma **[!UICONTROL Métrica]**, um **[!UICONTROL Intervalo de datas principal]**, um **[!UICONTROL Intervalo de datas de comparação]** (opcional) e um **[!UICONTROL Filtro]** (opcional):

   ![Configuração da métrica principal mostrando as opções de métrica, intervalo de datas principal, intervalo de datas de comparação e segmento.](assets/key-metrics-config.png)

   | Opção | Descrição |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Selecione a métrica que deseja examinar. Todas as métricas são compatíveis. |
   | **[!UICONTROL Intervalo de datas principal]** | O intervalo de datas atual da tabela de forma livre. |
   | **[!UICONTROL Intervalo de datas de comparação]** | O intervalo de datas no qual você deseja comparar o intervalo de datas principal. |
   | **[!UICONTROL Filtro (opcional)]** | Qualquer filtro em que você esteja interessado especificamente neste resumo. |

   {style="table-layout:auto"}

1. Selecione **[!UICONTROL Criar]**.

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

A saída do resumo da métrica principal é semelhante a:

![Saída de métrica principal mostrando a métrica, a alteração de resumo, o número de resumo e os gráficos de linha.](assets/key-metrics.png)

* O gráfico de linhas **[!UICONTROL Período anterior]** (sempre exibido em cinza) corresponde ao **[!UICONTROL Intervalo de datas de comparação]** na etapa de configuração.

* Se um intervalo de datas de comparação não for especificado durante a configuração ou estiver oculto nas configurações de visualização, somente o gráfico de linhas do intervalo de datas principal será exibido. A alteração do resumo está oculta.

* A partir daqui, você pode passar o mouse sobre os gráficos de linha para ver as estatísticas de dias individuais:


## Configurar

Após criar a visualização, é possível editar a configuração original.

1. Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Configurar visualização]** na parte superior da visualização.

   Você é levado de volta à caixa de diálogo de configuração original.

1. Altere as configurações como preferir. Selecione **[!UICONTROL Redefinir]** para redefinir as configurações atuais. Selecione **[!UICONTROL Build]** para recriar a visualização.

## Configurações 

Como parte das configurações de visualização, configurações específicas do resumo da métrica principal estão disponíveis.

| Configuração | Descrição |
|---|---|
| **[!UICONTROL Tipo de exibição de resumo]** | Selecione entre **[!UICONTROL Enfatizar a alteração percentual]** ou **[!UICONTROL Enfatizar o valor numérico]**. |
| **[!UICONTROL Mostrar linhas de tendência]** | Mostrar linhas de tendência na visualização. |
| **[!UICONTROL Mostrar máximo e mínimo em linhas de tendência]** | Mostrar valor máximo e mínimo em linhas de tendência. |
| **[!UICONTROL Mostrar porcentagem de comparação e linha de tendência]** | Mostrar porcentagem de comparação com linha de tendência. Se não for selecionada, ambas ficam ocultas. |
| **[!UICONTROL Opções de valor numérico]** | **[!UICONTROL Mostrar número total]** ou **[!UICONTROL Mostrar diferença bruta]** para o valor numérico. |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor do número. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Abreviação**</td><td>**Resultado**</td></tr><tr><td>$ 12.011.141,25</td><td>Não selecionado</td><td  align="right">$ 12.011.141,25</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 1</td><td align="right">US$ 12 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 2</td><td  align="right">US$ 12,0 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como 2</td><td align="right">US$ 12,011 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionar, definir como 3</td><td align="right">US$ 12,011 milhões</td></tr></table> |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
