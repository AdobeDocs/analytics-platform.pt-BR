---
title: Configurações do componente de segmentação de valores
description: Combinar valores numéricos em uma dimensão.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 100%

---

# Configurações do componente de [!UICONTROL Segmentação de valores] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_valuebucketing"
>title="Classificação de valor"
>abstract="Valores de bloco em intervalos específicos. Estes intervalos aparecem como itens de dimensão nos relatórios."

<!-- markdownlint-enable MD034 -->


Ao criar ou editar uma visualização de dados, a segmentação de valores permite combinar valores numéricos com base em um intervalo. Essa função está disponível apenas para dimensões que utilizam dados de esquema do tipo Integer ou Double.

![Classificação de valor](../assets/value-bucketing.png)

A segmentação de valores é importante quando você deseja agrupar intervalos, em vez de tratar cada número único como um item de dimensão separado. Por exemplo, um segmento “Entre 5 e 10” será exibido como um item de linha “5 a 10” no Analysis Workspace.

Se você quiser a flexibilidade de criar relatórios tanto em dimensões segmentadas como não segmentadas, arraste duas cópias do componente para a lista de dimensões disponíveis. Ative a segmentação em uma dimensão e desative-a na outra.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Valor do bloco] | Uma caixa de seleção que permite ativar a segmentação. |
| [!UICONTROL Menos que] | O limite superior do segmento da primeira dimensão. |
| [!UICONTROL Incluindo] [!UICONTROL e menor que] | Limites de segmentos subsequentes. |
| [!UICONTROL Maior que ou igual a] | O limite inferior do segmento da última dimensão. |
| [!UICONTROL Adicionar bloco] | Permite adicionar outro intervalo à classificação de dimensão numérica. Você pode adicionar até 20 segmentos em uma única dimensão. |

{style="table-layout:auto"}
