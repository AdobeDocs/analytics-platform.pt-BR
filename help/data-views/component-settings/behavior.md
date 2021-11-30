---
title: Configurações do componente de comportamento
description: Especifique como uma dimensão ou métrica se comporta nos relatórios.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 100%

---

# Configurações do componente de comportamento

As configurações de comportamento estão disponíveis em dimensões e métricas. As configurações disponíveis dependem do tipo de componente e do tipo de dados do esquema.

![Configurações de comportamento](../assets/behavior-settings.png)

## Configurações de comportamento da dimensão

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Minúsculas] | Elimina a duplicação de linhas que têm o mesmo valor, mas com maiúsculas e minúsculas diferentes. Se ativada, todas as instâncias de uma dimensão com o mesmo valor são relatadas como minúsculas. Por exemplo, os dados contêm os valores `"liverpool"`, `"Liverpool"` e `"LIVERPOOL"` em uma dimensão de sequência. Se [!UICONTROL Minúsculas] estiver ativado, todos os três valores são combinados em `"liverpool"`. Se desativado, todos os três valores são tratados como distintos. |

![Dimensão que diferencia maiúsculas de minúsculas](../assets/case-sens-workspace.png)

>[!NOTE]
>
>Se você ativar [!UICONTROL Minúsculas] em uma dimensão de conjunto de dados de pesquisa, vários valores de pesquisa poderão existir para o mesmo identificador. Se esse conflito ocorrer, o CJA usará o primeiro valor ASCII ordenado (valores em maiúsculas precedem valores em minúsculas). A Adobe recomenda não usar conjuntos de dados de pesquisa que contenham o mesmo valor quando [!UICONTROL Minúsculas] estiverem ativadas.

## Configurações de comportamento da métrica

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Visível nos dados de esquema do tipo Integer e Double. Aumenta a métrica de acordo com o valor especificado. Por exemplo, aumenta uma métrica em 50, se o valor da coluna for `50`. |
| [!UICONTROL Contar instâncias] | Visível nos dados de esquema do tipo Integer e Double. Aumenta a métrica em um ponto, independentemente do valor. A presença de qualquer valor aumenta a métrica. Por exemplo, aumenta uma métrica em 1 se o valor da coluna for `50`. |
| [!UICONTROL Valores para contar] | Visível nos dados de esquema do tipo Booleano. Permite determinar se a métrica aumenta ao contar `true`, `false` ou ambos. |

Você pode gerar métricas de “Pedidos” e “Receita” no Analysis Workspace usando a mesma coluna do conjunto de dados de evento, com comportamentos diferentes. Arraste a coluna do conjunto de dados “Receita” para a visualização de dados duas vezes, e configure uma para “Contar valores” e a outra para “Contar instâncias”. A métrica “Pedidos” conta instâncias, enquanto a métrica “Receita” conta valores.
