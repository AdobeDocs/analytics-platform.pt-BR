---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# Criar uma métrica “Participação”

Este artigo explica como criar uma métrica que mostra como os valores individuais de uma dimensão selecionada (como Exibições de página, Canal de marketing, Versão do aplicativo) contribuíram para (ou participaram de) sessões que continham um pedido.

Esse tipo de informação pode ser útil para qualquer proprietário de conteúdo.

>[!NOTE]
>
>Métricas com outros modelos de atribuição, como Participação, também podem ser criadas por administradores como parte de um [visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR). O exemplo abaixo mostra como eles podem ser criados por qualquer usuário com acesso ao construtor de métricas calculadas no Workspace.

1. Comece a criar uma métrica, conforme descrito em [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. No Criador de métricas calculadas, nomeie a métrica como &quot;Participação&quot; ou algo semelhante
1. Arraste o evento bem sucedido &quot;Pedido&quot; para a tela Definição.
1. Selecionar ![Engrenagem](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para o [!DNL Orders] métricas.
1. Na janela pop-up exibida, selecione **[!UICONTROL Usar um modelo de atribuição não padrão]** para definir o [modelo de atribuição](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** e selecione **[!UICONTROL Session]** para o [!UICONTROL Janela de pesquisa]. Selecionar **[!UICONTROL Aplicar]** para confirmar.

   Na caixa Definição, ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Pedidos** é atualizado para ![Evento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **Pedidos (Partição|Sessão)**.

   ![](assets/participation-setup.png)



1. Selecionar [!UICONTROL **Salvar**] para salvar a métrica.
1. Use a métrica calculada em seu relatório. Abaixo da métrica calculada, é usada em um relatório para mostrar qual camada do cliente contribuiu para (ou participou de) sessões que continham um pedido.

   ![](assets/participation-pages-customer-tier.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
