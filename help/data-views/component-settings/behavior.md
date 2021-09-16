---
title: Configurações do componente de comportamento
description: Especifique como uma dimensão ou métrica se comporta nos relatórios.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 4%

---


# Configurações do componente de comportamento

As configurações de comportamento estão disponíveis em dimensões e métricas. As configurações disponíveis dependem do tipo de componente e do tipo de dados do esquema.

![Configurações de comportamento](../assets/behavior-settings.png)

## Configurações de comportamento de Dimension

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Minúsculas] | Elimina a duplicação de linhas que têm o mesmo valor, mas diferentes letras maiúsculas e minúsculas. Se ativada, todas as instâncias de uma dimensão com o mesmo valor são relatadas como minúsculas. Por exemplo, seus dados contêm os valores `"liverpool"`, `"Liverpool"` e `"LIVERPOOL"` em uma dimensão de string. Se [!UICONTROL Lower case] estiver ativado, todos os três valores são combinados em `"liverpool"`. Se estiver desativado, todos os três valores serão tratados como distintos. |

![Dimensão que diferencia maiúsculas de minúsculas](../assets/case-sens-workspace.png)

>[!NOTE]
>
>Se você ativar [!UICONTROL Lower case] em uma dimensão de conjunto de dados de pesquisa, vários valores de pesquisa poderão existir para o mesmo identificador. Se esse conflito ocorrer, o CJA usará o primeiro valor combinado ASCII (valores em maiúsculas precedem valores em minúsculas). O Adobe recomenda não usar conjuntos de dados de pesquisa que contenham o mesmo valor quando [!UICONTROL Lower case] estiver ativado.

## Configurações de comportamento da métrica

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Visível nos tipos de dados Integer e Double schema . Aumente a métrica pelo valor especificado. Por exemplo, aumenta uma métrica em 50 se o valor da coluna for `50`. |
| [!UICONTROL Contar instâncias] | Visível nos tipos de dados Integer e Double schema . Aumente a métrica uma vez, independentemente do valor. A presença de qualquer valor aumenta a métrica. Por exemplo, aumenta uma métrica em 1 se o valor da coluna for `50`. |
| [!UICONTROL Valores para contar] | Visível nos tipos de dados do schema booleano. Permite determinar se a métrica aumenta contando `true`, `false`, ou ambos. |

Você pode gerar uma métrica de &quot;Pedidos&quot; e &quot;Receita&quot; no Analysis Workspace usando a mesma coluna de conjunto de dados de evento com comportamentos diferentes. Arraste a coluna &quot;Receita&quot; do conjunto de dados para a exibição de dados duas vezes e defina uma como &quot;Valores de contagem&quot; e a outra como &quot;Instâncias de contagem&quot;. A métrica &quot;Pedidos&quot; conta instâncias, enquanto a métrica &quot;Receita&quot; conta valores.
