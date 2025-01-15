---
description: Use as visualizações Número do resumo e Alteração do resumo para exibir pontos de dados importantes em um projeto.
title: Número do resumo e alteração do resumo
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 48%

---

# Número do resumo e alteração do resumo

## Número do resumo {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Número do resumo"
>abstract="Crie uma visualização que mostre totais e subtotais."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artigo documenta o número do Resumo e a visualização de alteração do Resumo em **Customer Journey Analytics**. Consulte [Número do resumo e alteração do resumo](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) para a versão **Adobe Analytics**deste artigo.*

>[!ENDSHADEBOX]


Use a visualização ![Resumir](/help/assets/icons/123.svg) **[!UICONTROL Número do resumo]** para realçar um número grande que seja importante em um projeto. Essa visualização se comporta das seguintes maneiras, usando a fonte de dados associada:

* Seleciona o total da coluna caso nenhuma célula esteja selecionada.
* Se alguma célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

![Visualização do número do resumo](asses/../assets/summary-number.png)

Como parte das configurações de visualização, opções específicas de Número do resumo estão disponíveis.

| Opção | Definição |
|--- |--- |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor do número. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviação**</td><td>**Resultado**</td></tr><tr><td>$ 12.011.141,25</td><td>Não selecionado</td><td  align="right">$ 12.011.141,25</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `0`</td><td align="right">US$ 12 milhões</td></tr><tr><td>$ 12.011.141,25</td><td> Selecionado, definido como `1`</td><td  align="right">US$ 12,0 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `2`</td><td align="right">US$ 12,01 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `3`</td><td align="right">US$ 12,011 milhões</td></tr></table> |
| **[!UICONTROL Resumir valor por]** | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

## Alteração de resumo {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Alteração de resumo"
>abstract="Crie uma visualização que mostre o delta (alteração) entre dois números"

<!-- markdownlint-enable MD034 -->


Use a visualização ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Alteração do resumo]** para mostrar o delta (alteração) entre dois números. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

Essa visualização se comporta das seguintes maneiras:

* Se nenhuma célula estiver selecionada, compara os dois primeiros valores de célula na coluna.
* Se uma célula estiver selecionada, exibe 0, pois compara o valor da célula a ele mesmo.
* Se duas células estiverem selecionadas, a primeira célula selecionada é tomada como o numerador e a segunda como o denominador.
* Se mais de duas células estiverem selecionadas, considera apenas as duas primeiras para comparação.
* Se um intervalo de células estiver selecionado, compara a primeira com a última célula selecionada no intervalo.
* Se a coluna estiver selecionada, compara o primeiro valor a si mesmo, mostrando uma alteração de 0.


![Visualização de alteração de resumo mostrando o delta entre dois números.s](assets/summary-change.png)


Como parte das configurações de visualização, estão disponíveis **[!UICONTROL Opções de alteração do resumo]** específicas.

| Opção | Definição |
|--- |--- |
| **[!UICONTROL Mostrar alteração percentual]** | Mostrar a variação percentual entre os 2 números. |
| **[!UICONTROL Mostrar diferença bruta]** | Mostrar a diferença bruta entre os 2 números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor alterado. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviação**</td><td>**Resultado**</td></tr><tr><td>$ 12.011.141,25</td><td>Não selecionado</td><td  align="right">$ 12.011.141,25</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `0`</td><td align="right">US$ 12 milhões</td></tr><tr><td>$ 12.011.141,25</td><td> Selecionado, definido como `1`</td><td  align="right">US$ 12,0 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `2`</td><td align="right">US$ 12,01 milhões</td></tr><tr><td>$ 12.011.141,25</td><td>Selecionado, definido como `3`</td><td align="right">US$ 12,011 milhões</td></tr></table> |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
