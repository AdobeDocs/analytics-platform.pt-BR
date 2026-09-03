---
description: A Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: Modelos de métricas calculadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 83%

---

# Modelos de métricas calculadas

O Customer Journey Analytics fornece os seguintes modelos de métricas calculadas para abordar os casos de uso mais comuns. Essas métricas calculadas definidas pela Adobe são identificadas por um pequeno logotipo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Para filtrar rapidamente essas métricas, selecione ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Modelo do Adobe]** no [Filtro de componentes](/help/components/overview.md#filter).

| Nome da métrica calculada | Fórmula de<br/>descrição |
|---------|----------|
| **[!UICONTROL Taxa de início da sessão]** | A porcentagem em que qualquer item de dimensão ocorreu no primeiro evento de uma sessão.<p>Essa métrica calculada é adicionada automaticamente ao Espaço de trabalho ao incluir o componente padrão [!UICONTROL Inícios de sessão] [](/help/data-views/component-reference.md) na [exibição de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Inícios de sessão** ![Divisão](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |
| **[!UICONTROL Tempo gasto por pessoa]** | A quantidade média de tempo que uma pessoa gastou em determinado item de dimensão.<p>Essa métrica calculada é adicionada automaticamente ao Espaço de trabalho ao incluir o componente padrão [!UICONTROL Tempo gasto (segundos)] [](/help/data-views/component-reference.md) na [exibição de dados](/help/data-views/create-dataview.md). O segmento Excluir último evento de sessão é aplicado à métrica Pessoas. O segmento exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário antes de um evento ou ação, como uma compra ou envio de formulário, ao mesmo tempo em que exclui a ação final em si.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Pessoas ) )** |
| **[!UICONTROL Sessões por pessoa]** | O número médio de sessões por pessoa.<p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessões** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Pessoas** **)** |
| **[!UICONTROL Tempo gasto por sessão]** | A quantidade média de tempo que uma pessoa gastou por sessão em qualquer item de dimensão.<p>Essa métrica calculada é adicionada automaticamente ao Espaço de trabalho ao incluir o componente padrão [!UICONTROL Tempo gasto (segundos)] [](/help/data-views/component-reference.md) na [exibição de dados](/help/data-views/create-dataview.md). O segmento Excluir último evento da sessão é aplicado à métrica Sessões. O segmento exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário antes de um evento ou ação, como uma compra ou envio de formulário, ao mesmo tempo em que exclui a ação final em si.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Sessões ) )** |
| **[!UICONTROL Taxa de término da sessão]** | A porcentagem em que qualquer item de dimensão ocorreu no último evento de uma sessão. <p>Essa métrica calculada é adicionada automaticamente ao Espaço de trabalho ao incluir o componente padrão [!UICONTROL Fim da sessão] [](/help/data-views/component-reference.md) na [exibição de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Fim da sessão** ![Divisão](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |
| **[!UICONTROL Sessões da Web]** | O número de sessões que ocorreram no site. |
| **[!UICONTROL Taxa de conclusão da pesquisa]** | A taxa em que as pessoas concluíram uma pesquisa após iniciá-la. |
| **[!UICONTROL Taxa de sessão multicanal]** | A proporção de sessões que incluíram vários canais (como tráfego na web e tráfego móvel), em comparação com às que incluíram apenas um canal. |
| **[!UICONTROL Taxa de pessoa multicanal]** | A proporção de pessoas que participaram de vários canais em comparação às que participaram apenas de um canal. |
| **[!UICONTROL Sessões de aplicativo móvel]** | O número de sessões que ocorreram no aplicativo móvel. |
| **[!UICONTROL Sessões de canal cruzado da Web+Aplicativo]** | O número de sessões que ocorreram e que incluíram tráfego na web e tráfego móvel. |
| **[!UICONTROL Custo de chamadas]** | O custo total de chamadas para a central de atendimento. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Duração média da chamada]** | A duração média das chamadas feitas para a central de atendimento. |
| **[!UICONTROL Custo médio por chamada]** | O custo médio de chamadas feitas para a central de atendimento. |
| **[!UICONTROL Pontuação média da pesquisa de chamadas]** | Pontuação média da pesquisa referente às chamadas feitas para a central de atendimento. |

{style="table-layout:auto"}
