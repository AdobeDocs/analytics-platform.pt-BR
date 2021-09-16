---
title: Nenhuma configuração de componente de opções de valor
description: Determine como lidar com uma dimensão se ela estiver vazia.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 35%

---


# Nenhuma configuração de componente Opções de Valor

Nenhuma opção de valor permite determinar como o Analysis Workspace lida com situações em que um evento em um conjunto de dados contém uma métrica, mas a dimensão não continha um valor. Você pode escolher o nome desse item de dimensão, ocultá-lo totalmente ou até mesmo tratá-lo como um valor real.

![Sem opções de valor](../assets/no-value-options.png)

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Se for exibido, chame &quot;Sem valor&quot;] | Um campo de texto que permite renomear o item de dimensão **[!UICONTROL No value]** para outra coisa. |
| [!UICONTROL Não mostrar Nenhum valor por padrão] | Não mostra esse valor nos relatórios. As ocorrências de métrica não vinculadas a essa dimensão não são visíveis no relatório. |
| [!UICONTROL Mostrar Nenhum valor por padrão] | Mostra este valor no relatório. |
| [!UICONTROL Tratar Nenhum valor como um valor] | Substitui valores em branco nos dados pelo texto especificado em [!UICONTROL Se mostrado, chame &quot;Nenhum valor&quot;]. Por exemplo, se você tiver tipos de dispositivo móvel como a dimensão, poderá renomear o item **[!UICONTROL Nenhum valor]** para &quot;Desktop&quot;. Quando você altera esse campo para um valor personalizado, o valor personalizado é tratado como um valor de string legítimo. Portanto, se você inserir o valor &quot;Vermelho&quot; nesse campo, qualquer instância da sequência &quot;Vermelho&quot; que for mostrada nos próprios dados também será inserida sob o mesmo item da linha especificado. |
