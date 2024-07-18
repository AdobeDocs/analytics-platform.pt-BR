---
description: O Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: Métricas calculadas padrão
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 28%

---

# Métricas calculadas padrão

O Customer Journey Analytics fornece as seguintes métricas calculadas para cobrir os casos de uso mais comuns:

| Nome da métrica calculada | Descrição | Fórmula |
|---------|----------|---------|
| Taxa de início da sessão | A porcentagem de ocorrência de qualquer item de dimensão no primeiro evento de uma sessão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o `[Session Starts]` [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Tempo gasto por pessoa | A quantidade média de tempo que uma pessoa gastou em determinado item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o `[Time Spent (seconds)]` [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sessões por pessoa | O número médio de Sessões por Pessoa. | `[Sessions] / [Users]` |
| Tempo gasto por sessão | A quantidade média de tempo que uma pessoa gastou por sessão em qualquer item de dimensão.<p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o `[Time Spent (seconds)]` [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Taxa de término da sessão | A porcentagem de ocorrência de qualquer item de dimensão no último evento de uma sessão. <p>Esta métrica calculada é adicionada automaticamente ao Workspace quando você inclui o `[Session Ends]` [componente padrão](/help/data-views/component-reference.md) na sua [visualização de dados](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
