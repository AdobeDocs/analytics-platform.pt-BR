---
description: Saiba como criar métricas calculadas.
title: Criar métricas calculadas
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 2%

---

# Criar métricas calculadas

Por padrão, somente administradores podem criar métricas calculadas. Os usuários têm o direito de visualizar métricas calculadas de maneira semelhante à forma como os usuários visualizam outros componentes (como segmentos, anotações e muito mais).

No entanto, os administradores podem conceder a permissão **[!UICONTROL Criação de Métrica Calculada]** para **[!UICONTROL Ferramentas de Relatórios]** em **[!UICONTROL Editar permissões para o CJA Workspace Access]** para usuários através do [Admin Console](/help/technotes/access-control.md#user-level-access).


Você pode criar uma métrica calculada das seguintes maneiras:

![Maneiras de criar um filtro](assets/create-metric.png)

* **A**. Na interface principal, selecione **[!UICONTROL Componentes]** e selecione **[!UICONTROL Métricas calculadas]**. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] no gerenciador [[!UICONTROL Métricas calculadas]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. Em um projeto do Workspace, no painel esquerdo Componentes, selecione ![Adicionar](/help/assets/icons/Add.svg) em ![Evento](/help/assets/icons/Event.svg) **Métricas**.
* **C**. Em um projeto do Workspace, no menu de contexto no cabeçalho da coluna de métricas, selecione **[!UICONTROL Criar métrica a partir da seleção]**. No submenu, você pode selecionar uma função ou selecionar **[!UICONTROL Abrir no construtor de métrica calculada]**. <br/>Se você selecionar uma função, a métrica calculada será definida como uma métrica somente de projeto. Ao editar posteriormente esta métrica, por meio do pop-up [Informações do componente](/help/components/use-components-in-workspace.md#component-info), você verá uma notificação no [Construtor de métrica calculada](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. Em um projeto do Workspace, selecione **[!UICONTROL Componentes]** no menu e selecione **[!UICONTROL Criar métrica]**.
* **E**. Em um projeto do Workspace, use o atalho **[!UICONTROL shift+cmd+c]** (macOS) ou **[!UICONTROL shift+ctrl+c]** (Windows).

Para definir a nova métrica calculada, use o [Construtor de métrica calculada](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
