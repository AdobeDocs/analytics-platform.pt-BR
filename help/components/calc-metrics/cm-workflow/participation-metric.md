---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 32%

---

# Criar uma métrica de &quot;Participação&quot;

As informações a seguir explicam como criar uma métrica que mostra quais páginas contribuíram para (ou participaram de) sessões que continham um pedido.

Esse tipo de informação pode ser útil para qualquer proprietário de conteúdo.

>[!NOTE]
>
>Você pode ativar as métricas de participação nas Ferramentas administrativas, mas somente para eventos personalizados 1 - 100.

1. Comece a criar uma métrica, conforme descrito em [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. No Criador de métricas calculadas, nomeie a métrica como &quot;Participação&quot; ou algo semelhante
1. Arraste o evento bem sucedido &quot;Pedido&quot; para a tela Definição.
1. Altere o [modelo de atribuição](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** na engrenagem **[!UICONTROL Configurações]**. Selecionar **[!UICONTROL Session]** pesquisa. A definição deve ficar parecida com isto:

   ![](assets/participation.png)

1. Selecionar [!UICONTROL **Salvar**] para salvar a métrica.
1. Use a métrica calculada em um relatório de **[!UICONTROL Páginas]**.

   ![](assets/participation-pages.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
