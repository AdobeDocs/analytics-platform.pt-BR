---
title: Configurações do componente de comportamento
description: Especifique como uma dimensão ou métrica se comporta nos relatórios.
exl-id: 170f445f-1eac-4b70-8956-1afb0cb2d611
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/ra-O8TGxS6ByFEClZR7FtOnJ70YwclBiVMh9vubmGxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 341
ht-degree: 100%

---

# Configurações do componente de comportamento {#behavior-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_behavior"
>title="Comportamento"
>abstract="Aplicável aos componentes de dimensão e métrica. Determine como os itens de linha desta métrica são agregados. Especifique se os valores da string desta dimensão devem estar em letras minúsculas."

<!-- markdownlint-enable MD034 -->


As configurações de comportamento estão disponíveis em dimensões e métricas. As configurações disponíveis dependem do tipo de componente e do tipo de dado do esquema.

![Configurações de comportamento](../assets/behavior-settings.png)

## Configurações de comportamento da dimensão

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Minúsculas] | Elimina a duplicação de linhas que têm o mesmo valor, mas com maiúsculas e minúsculas diferentes. Se habilitada, todas as instâncias de uma dimensão com o mesmo valor são relatadas como minúsculas. Por exemplo, os dados contêm os valores `"liverpool"`, `"Liverpool"` e `"LIVERPOOL"` em uma dimensão de sequência. Se [!UICONTROL Minúsculas] estiver habilitado, todos os três valores são combinados em `"liverpool"`. Se desativado, todos os três valores são tratados como distintos. |

{style="table-layout:auto"}

>[!NOTE]
>
>Se você habilitar [!UICONTROL Minúsculas] em uma dimensão de conjunto de dados de pesquisa, vários valores de pesquisa poderão existir para o mesmo identificador. Se esse conflito ocorrer, o Customer Journey Analytics usará o primeiro valor ASCII agrupado (valores em maiúsculas precedem valores em minúsculas). A Adobe recomenda não usar conjuntos de dados de pesquisa que contenham o mesmo valor quando [!UICONTROL Minúsculas] estiverem habilitadas.

![Dimensão que diferencia maiúsculas de minúsculas](../assets/case-sens-workspace.png)

## Configurações de comportamento da métrica

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Contar valores] | Visível nos tipos de dados Integer e Double do esquema. Aumenta a métrica de acordo com o valor especificado. Por exemplo, aumenta uma métrica em 50, se o valor da coluna for `50`. |
| [!UICONTROL Contar instâncias] | Visível nos tipos de dados Integer e Double do esquema. Aumenta a métrica em um ponto, independentemente do valor. A presença de qualquer valor aumenta a métrica. Por exemplo, aumenta uma métrica em 1 se o valor da coluna for `50`. |
| [!UICONTROL Valores para contar] | Visível em tipos de dados Boolean do esquema. Permite determinar se a métrica aumenta ao contar `true`, `false` ou ambos. |

{style="table-layout:auto"}

Você pode gerar métricas de “Pedidos” e “Receita” no Analysis Workspace usando a mesma coluna do conjunto de dados de evento, com comportamentos diferentes. Arraste a coluna do conjunto de dados “Receita” para a visualização de dados duas vezes, e configure uma para “Contar valores” e a outra para “Contar instâncias”. A métrica “Pedidos” conta instâncias, enquanto a métrica “Receita” conta valores.
