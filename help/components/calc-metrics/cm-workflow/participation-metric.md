---
description: Com o Criador de métrica calculada, qualquer pessoa pode criar uma métrica de participação.
title: Métrica de participação
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Métricas de participação

As Métricas de participação são usadas para quantificar como os valores individuais de uma dimensão (como Exibições de página) contribuem ou participam de sessões que contêm uma métrica específica (como Pedidos).

>[!NOTE]
>
>Os administradores podem criar métricas com modelos de atribuição não padrão, como Participação, como parte de uma [visualização de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/data-views). Consulte [Configurações do componente de atribuição](../../../data-views/component-settings/attribution.md) para obter mais detalhes.

As etapas abaixo mostram como qualquer usuário com [Permissão de criação de métrica calculada](/help/technotes//access-control.md#user-level-access) pode criar uma métrica de participação.

1. [Crie uma métrica calculada](cm-workflow.md) e, no [Construtor de métricas calculadas](cm-build-metrics.md), nomeie a métrica `Participation` ou algo semelhante.
1. Arraste uma métrica contendo um evento bem-sucedido, por exemplo [!DNL Orders], para a área [!UICONTROL **[!UICONTROL Definição]**].
1. Selecione ![engrenagem](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para a métrica.
1. Na janela pop-up exibida, selecione **[!UICONTROL Usar um modelo de atribuição não padrão]** para definir o [modelo de atribuição](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** e selecione **[!UICONTROL Sessão]** para o [!UICONTROL Contêiner]. Selecione **[!UICONTROL Aplicar]** para confirmar.


   ![Pop-up de modelo de atribuição de coluna mostrando a Participação selecionada como o modelo e a Sessão selecionada para a janela de pesquisa.](assets/participation-setup.png)

   **(Partipation|Session)** é adicionado ao nome do componente de métrica.



1. Selecione [!UICONTROL **Salvar**] para salvar a métrica.
1. Use a métrica calculada em seu relatório. Por exemplo, use a métrica [!DNL Orders (Session Participation)] calculada em um relatório para mostrar qual Camada de cliente contribuiu para (ou participou de) sessões que continham um pedido.

   ![Tabela de forma livre mostrando a camada e os pedidos do cliente.](assets/participation-pages-customer-tier.png)
