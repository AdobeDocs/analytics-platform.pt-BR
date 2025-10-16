---
description: Use as visualizações de número do resumo e alteração do resumo para exibir pontos de dados importantes em um projeto.
title: Número Do Resumo E Alteração Do Resumo
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 639c3d3c349615078c76f8806bcd5bb458b0f6f2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 69%

---

# Número do resumo e alteração

>[!BEGINSHADEBOX]

_Este artigo documenta as visualizações de número do resumo e alteração do resumo no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulte [Número do resumo e alteração do resumo](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change) para saber a versão do_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualização de número do resumo e alteração do resumo](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

## Número do resumo {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Número do resumo"
>abstract="Crie uma visualização que mostre totais e subtotais."

<!-- markdownlint-enable MD034 -->

Use a visualização de  ![Summarize](/help/assets/icons/123.svg) **[!UICONTROL Número do resumo]** para realçar um número grande que é importante em um projeto. Essa visualização comporta-se das seguintes maneiras, usando a fonte de dados associada:

* Seleciona o total da coluna se nenhuma célula for selecionada.
* Se uma única célula for selecionada, ela mostrará o resumo dessa célula.
* Se mais de uma célula for selecionada, ela mostrará a primeira célula selecionada.
* Se a coluna for selecionada, ela escolherá o primeiro valor de célula na coluna.

![Visualização de número do resumo](asses/../assets/summary-number.png)

Como parte das configurações de visualização, opções específicas de número do resumo estão disponíveis.

| Opção | Definição |
|--- |--- |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor do número. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviação**</td><td>**Resultado**</td></tr><tr><td>US$ 12.011.141,25</td><td>Não selecionado</td><td  align="right">US$ 12.011.141,25</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `0`</td><td align="right">US$ 12 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td> Selecionado e definido como `1`</td><td  align="right">US$ 12,0 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `2`</td><td align="right">US$ 12,01 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `3`</td><td align="right">US$ 12,011 milhões</td></tr></table> |
| **[!UICONTROL Resumir valor por]** | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

## Alteração de resumo {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Alteração de resumo"
>abstract="Crie uma visualização que mostre o delta (alteração) entre dois números"

<!-- markdownlint-enable MD034 -->


Use a visualização de ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Alteração do resumo]** para mostrar o delta (alteração) entre dois números. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=pt-BR) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=pt-BR) option.
-->

Essa visualização se comporta das seguintes maneiras:

* Se nenhuma célula for selecionada, ela comparará os dois primeiros valores da célula na coluna.
* Se uma célula for selecionada, ela mostrará 0, porque compara o valor da célula a si mesma.
* Se forem selecionadas duas células, toma-se a primeira célula selecionada como numerador e a segunda como denominador.
* Se mais de duas células forem selecionadas, ele só considerará as duas primeiras para comparação.
* Se um intervalo de células for selecionado, ele compara a primeira às últimas células selecionadas no intervalo.
* Se a coluna for selecionada, ela comparará o primeiro valor a si mesma, o que mostra uma alteração de 0.


![Visualização de alteração do resumo, mostrando o delta entre dois números.](assets/summary-change.png)


Como parte das configurações de visualização, existem **[!UICONTROL Opções de alteração do resumo]** específicas.

| Opção | Definição |
|--- |--- |
| **[!UICONTROL Mostrar variação percentual]** | Mostrar a variação percentual entre os dois números. |
| **[!UICONTROL Mostrar diferença bruta]** | Mostrar a diferença bruta entre os dois números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
| **[!UICONTROL Abreviar valor]** | Selecione **[!UICONTROL Abreviar valor]** para abreviar de forma inteligente o valor alterado. Quando selecionado, insira um número para definir a quantidade de abreviação. Por exemplo:<br/><table><tr><td>**Valor original**</td><td>**Valor de abreviação**</td><td>**Resultado**</td></tr><tr><td>US$ 12.011.141,25</td><td>Não selecionado</td><td  align="right">US$ 12.011.141,25</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `0`</td><td align="right">US$ 12 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td> Selecionado e definido como `1`</td><td  align="right">US$ 12,0 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `2`</td><td align="right">US$ 12,01 milhões</td></tr><tr><td>US$ 12.011.141,25</td><td>Selecionado e definido como `3`</td><td align="right">US$ 12,011 milhões</td></tr></table> |

>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Configurações de visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu de contexto da visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
