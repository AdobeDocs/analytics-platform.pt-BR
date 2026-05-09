---
title: Configurações do componente de segmentação de valores
description: Combinar valores numéricos em uma dimensão.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: ba9ae0e5084aaf1b14cff0ac89abd9b9f3569cc0
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 100%

---

# Configurações do componente de [!UICONTROL Segmentação de valores] {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="Classificação de valor"
>abstract="Valores de bloco em intervalos específicos. Estes intervalos aparecem como itens de dimensão nos relatórios."

<!-- markdownlint-enable MD034 -->


Ao criar ou editar uma visualização de dados, a segmentação de valores permite combinar valores numéricos com base em um intervalo. Essa função está disponível apenas para dimensões que utilizam tipos de dados Integer ou Double do esquema.

![Classificação de valor](../assets/value-bucketing.png)

A segmentação de valores é importante quando você deseja agrupar intervalos, em vez de tratar cada número único como um item de dimensão separado. Por exemplo, um segmento “Entre 5 e 10” será exibido como um item de linha “5 a 10” no Analysis Workspace.

Se você quiser a flexibilidade de criar relatórios tanto em dimensões segmentadas como não segmentadas, arraste duas cópias do componente para a lista de dimensões disponíveis. Habilite a segmentação em uma dimensão e desabilite-a na outra.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Valor do bloco] | Uma caixa de seleção que permite ativar a segmentação. |
| [!UICONTROL Menos que] | O limite superior do segmento da primeira dimensão. |
| [!UICONTROL Incluindo] [!UICONTROL e menor que] | Limites de segmentos subsequentes. |
| [!UICONTROL Maior que ou igual a] | O limite inferior do segmento da última dimensão. |
| [!UICONTROL Adicionar bloco] | Permite adicionar outro intervalo à classificação de dimensão numérica. Você pode adicionar até 20 segmentos em uma única dimensão. |

{style="table-layout:auto"}
