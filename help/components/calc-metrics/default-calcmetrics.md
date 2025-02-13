---
description: O Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: Modelos de métricas calculadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 6%

---

# Modelos de métricas calculadas

O Customer Journey Analytics fornece os seguintes modelos de métricas calculadas para abordar os casos de uso mais comuns. Essas métricas calculadas definidas pelo Adobe são identificadas por um pequeno logotipo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Para filtrar rapidamente por essas métricas, selecione ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Modelo do Adobe]** no [Filtro de componentes](/help/components/overview.md#filter).

| Nome da métrica calculada | Descrição<br/>Fórmula |
|---------|----------|
| **[!UICONTROL Taxa de início da sessão]** | A porcentagem de ocorrência de qualquer item de dimensão no primeiro evento de uma sessão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Início de sessão] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Início da sessão** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |
| **[!UICONTROL Tempo gasto por pessoa]** | A quantidade média de tempo que uma pessoa gastou em determinado item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Tempo gasto (segundos)] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md). O filtro Excluir último evento da sessão é aplicado à métrica Pessoas. O filtro exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário que leva a um evento ou ação, como uma compra ou o envio de um formulário, enquanto exclui a própria ação final.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Pessoas )** |
| **[!UICONTROL Sessões por pessoa]** | O número médio de Sessões por Pessoa.<p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessões** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Pessoas** **)** |
| **[!UICONTROL Tempo gasto por sessão]** | A quantidade média de tempo que uma pessoa gastou por sessão em qualquer item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Tempo gasto (segundos)] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md). O filtro Excluir último evento da sessão é aplicado à métrica Sessões. O filtro exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário que leva a um evento ou ação, como uma compra ou o envio de um formulário, enquanto exclui a própria ação final.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Sessões )** |
| **[!UICONTROL Taxa de término da sessão]** | A porcentagem de ocorrência de qualquer item de dimensão no último evento de uma sessão. <p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Fim de Sessão] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessão termina** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |
| **[!UICONTROL Sessões da Web]** | O número de sessões que ocorreram no site. |
| **[!UICONTROL Taxa de conclusão da pesquisa]** | A taxa em que as pessoas concluíram uma pesquisa após iniciá-la. |
| **[!UICONTROL Taxa de sessões multicanal]** | A proporção de sessões que ocorreram e que incluíram vários canais (como tráfego da Web e tráfego móvel), em comparação àquelas que incluíram apenas um único canal. |
| **[!UICONTROL Taxa de pessoas multicanais]** | A proporção de pessoas que participaram de vários canais, em comparação àquelas que participaram apenas de um único canal. |
| **[!UICONTROL Sessões de aplicativos móveis]** | O número de sessões que ocorreram no aplicativo móvel. |
| **[!UICONTROL Sessões entre canais da Web+aplicativo]** | O número de sessões que ocorreram e que incluíram tráfego da Web e tráfego móvel. |
| **[!UICONTROL Custo das chamadas]** | O custo total de chamadas para a central de atendimento. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Duração média da chamada]** | A duração média das chamadas feitas para a central de atendimento. |
| **[!UICONTROL Custo médio por chamada]** | O custo médio de chamadas feitas para a central de atendimento. |
| **[!UICONTROL Pontuação média da pesquisa de chamadas]** | A pontuação média da pesquisa em relação às chamadas feitas para a central de atendimento. |

{style="table-layout:auto"}
