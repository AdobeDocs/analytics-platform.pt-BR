---
description: Use o Número do resumo e as Visualizações de alteração para exibir pontos de dados importantes em um projeto.
title: Número do resumo e alteração do resumo
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 61c1fe48ebe8ebff5b7104cebae1ce7b62289b7d
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 94%

---

# Número do resumo e alteração do resumo

## Visualização do número de resumo {#summary-number}

Use a visualização Número do resumo para realçar um grande número que é importante em um projeto. Essa visualização se comporta das seguintes maneiras:

* Seleciona o total da coluna caso nenhuma célula esteja selecionada.
* Se alguma célula estiver selecionada, mostra o resumo dessa célula.
* Se mais de uma célula estiver selecionada, mostra a primeira célula selecionada.
* Se a coluna estiver selecionada, escolhe o primeiro valor de célula na coluna.

Clique na engrenagem **Configurações de visualização** no canto superior direito para definir as configurações de Número do resumo:

| Configuração | Definição |
|--- |--- |
| Porcentagens | Exiba porcentagens em vez de números brutos. |
| Legenda visível | Exiba informações sobre a métrica mostrada. |
| Abreviar valor | Escolha abreviar valores e mostrar até 3 casas decimais. |
| Resumir valor por | Opte por exibir o máximo, mínimo, médio, mediano ou soma para uma seleção de dados. |

{style="table-layout:auto"}

## Visualização da alteração do resumo {#summary-change}

Use a visualização Alteração do resumo para mostrar o delta (alteração) entre dois números.

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


Clique na engrenagem **Configurações de visualização** no canto superior direito para definir as configurações de Alteração de resumo:

| Configuração | Definição |
|--- |--- |
| Porcentagens | Exiba porcentagens em vez de números brutos. |
| Legenda visível | Exiba informações sobre a métrica mostrada. |
| Mostrar variação percentual | Mostra a variação percentual entre os 2 números. |
| Mostrar diferença bruta | Mostra a diferença bruta entre 2 números. Também é possível abreviar valores e mostrar até 3 casas decimais com essa opção. |
