---
description: Com o Criador de métricas calculadas, qualquer um pode criar uma métrica de participação.
title: Métrica de participação
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 6%

---

# Criar uma métrica de participação

Este artigo explica como criar uma métrica de participação. Uma métrica de participação mostra como os valores individuais de uma dimensão (como Exibições de página, Canal de marketing) contribuem para ou participam de sessões que contêm uma métrica específica (por exemplo, Pedidos).

Esse tipo de informação pode ser útil para qualquer proprietário de conteúdo.

>[!NOTE]
>
>Métricas com outros modelos de atribuição, como Participação, também podem ser criadas por administradores como parte de um [visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=pt-BR). Consulte [Configurações do componente de Atribuição](../../../data-views/component-settings/attribution.md) para obter mais detalhes.<br/>O exemplo abaixo mostra como uma métrica de participação pode ser criada por qualquer usuário com acesso ao construtor de métricas calculadas no Workspace.


1. Comece a criar uma métrica, conforme descrito em [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. No Criador de métricas calculadas, nomeie a métrica `Participation` ou algo parecido.
1. Arraste uma métrica contendo um evento bem-sucedido, por exemplo [!DNL Orders], no [!UICONTROL Definição] tela.
1. Selecionar ![Engrenagem](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) para a métrica.
1. Na janela pop-up exibida, selecione **[!UICONTROL Usar um modelo de atribuição não padrão]** para definir o [modelo de atribuição](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) desse evento para **[!UICONTROL Participação]** e selecione **[!UICONTROL Session]** para o [!UICONTROL Janela de pesquisa]. Selecionar **[!UICONTROL Aplicar]** para confirmar.

   Na caixa Definição, a métrica selecionada é atualizada anexando  **(Partição|Sessão)** ao seu nome.

   ![Pop-up modelo de atribuição de coluna mostrando Participação selecionada como o modelo e Sessão selecionada para a janela de pesquisa.](assets/participation-setup.png)



1. Selecionar [!UICONTROL **Salvar**] para salvar a métrica.
1. Use a métrica calculada em seu relatório. Por exemplo, use o valor calculado [!DNL Orders (Session Participation)] (conforme definido na etapa 5) de um relatório para mostrar qual Camada do cliente contribuiu para (ou participou de) sessões que continham um pedido.

   ![Tabela de forma livre que mostra a camada do cliente e os pedidos.](assets/participation-pages-customer-tier.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
