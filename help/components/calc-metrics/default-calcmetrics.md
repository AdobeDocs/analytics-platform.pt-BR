---
description: O Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: Métricas calculadas padrão
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a507417c945f827ebb8bc92f7b5f54a9c4e6faa0
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 9%

---

# Métricas calculadas padrão

O Customer Journey Analytics fornece as seguintes métricas calculadas padrão para cobrir os casos de uso mais comuns. Essas métricas calculadas padrão definidas pelo Adobe são identificadas por um pequeno logotipo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Para filtrar rapidamente por essas métricas, selecione ![Rótulo](/help/assets/icons/Label.svg) **[!UICONTROL Modelo de Adobe]** no [Filtro de componentes](/help/components/overview.md#filter).

| Nome da métrica calculada | Descrição<br/>Fórmula |
|---------|----------|
| **[!UICONTROL Taxa de Início da Sessão]** | A porcentagem de ocorrência de qualquer item de dimensão no primeiro evento de uma sessão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Início de sessão] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Inícios de Sessão** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |
| **[!UICONTROL Tempo Gasto Por Pessoa]** | A quantidade média de tempo que uma pessoa gastou em determinado item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Tempo gasto (segundos)] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md). O filtro Excluir último evento da sessão é aplicado à métrica Pessoas. O filtro exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário que leva a um evento ou ação, como uma compra ou o envio de um formulário, enquanto exclui a própria ação final.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Pessoas )** |
| **[!UICONTROL Sessões por pessoa]** | O número médio de Sessões por Pessoa.<p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Sessões** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Pessoas** **)** |
| **[!UICONTROL Tempo gasto por sessão]** | A quantidade média de tempo que uma pessoa gastou por sessão em qualquer item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Tempo gasto (segundos)] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md). O filtro Excluir último evento da sessão é aplicado à métrica Sessões. O filtro exclui o último evento de cada sessão em um conjunto de dados. Essa exclusão pode ajudar você a analisar o comportamento do usuário que leva a um evento ou ação, como uma compra ou o envio de um formulário, enquanto exclui a própria ação final.</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Tempo gasto (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentação](/help/assets/icons/Segmentation.svg) **Excluir último evento da sessão(** ![Evento](/help/assets/icons/Event.svg) **Sessões )** |
| **[!UICONTROL Taxa de Término da Sessão]** | A porcentagem de ocorrência de qualquer item de dimensão no último evento de uma sessão. <p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o [!UICONTROL Fim de Sessão] [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p>Resumo: **(** ![Evento](/help/assets/icons/Event.svg) **Fim de Sessão** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sessões** **)** |

{style="table-layout:auto"}
