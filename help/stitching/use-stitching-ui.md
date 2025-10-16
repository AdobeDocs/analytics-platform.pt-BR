---
title: Usar compilação
description: Como usar a compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Usar compilação

Você pode ativar a compilação em um ou mais conjuntos de dados de evento configurados como parte da conexão. O número de conjuntos de dados de evento que você pode ativar para compilação é determinado pelo pacote do Customer Journey Analytics que você licenciou.

Você pode habilitar a compilação como parte das [configurações do conjunto de dados](/help/connections/create-connection.md#dataset-settings) para um conjunto de dados de evento ao [criar uma conexão](/help/connections/create-connection.md) ou ao [editar uma conexão](/help/connections/manage-connections.md#edit-a-connection).

Para habilitar a compilação, na seção de conjunto de dados do evento da caixa de diálogo **[!UICONTROL Adicionar conjuntos de dados]** ou **[!UICONTROL Editar conjunto de dados]**:

![Opções de identificação ao habilitar a identificação](assets/identity-stitching-ui.png)

1. Selecione **[!UICONTROL Habilitar identificação de identidade]**.

   Se você habilitar a compilação para um conjunto de dados de evento existente, a caixa de diálogo **[!UICONTROL Alterar ID de pessoa]** exibirá as implicações de uma alteração na ID de pessoa devido ao uso da compilação. Selecione **[!UICONTROL Continuar]** para continuar.

   A caixa de diálogo **[!UICONTROL Habilitar identificação de identidade]** resume as consequências da identificação. Selecione **[!UICONTROL Continuar]** para continuar.

1. Selecione uma ID persistente no menu suspenso **[!UICONTROL ID persistente]**.

   Se você selecionar **[!UICONTROL Mapa de identidade]** para a ID persistente, será necessário selecionar um namespace. Você tem duas opções:

   * Habilitar **[!UICONTROL Usar namespace de identidade primário]** para usar o namespace de identidade primário.
   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.

1. Selecione uma ID de pessoa no menu suspenso **[!UICONTROL ID de pessoa]**.

   Se você selecionar **[!UICONTROL Mapa de identidade]** para a ID de pessoa, será necessário selecionar um namespace. Você tem duas opções:

   * Habilitar **[!UICONTROL Usar namespace de identidade primário]** para usar o namespace de identidade primário.
   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.


   Se você selecionar **[!UICONTROL Gráfico de identidade]** para a ID de pessoa, será necessário selecionar um namespace.

   >[!NOTE]
   >
   >Você deve ter o direito de usar o gráfico de identidade.
   >

   Antes disso, uma caixa de diálogo **[!UICONTROL Alterar para gráfico de identidade]** é exibida para garantir que você [concluiu a configuração do gráfico de identidade para o conjunto de dados](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) antes de usar o gráfico de identidade para compilação. Selecione **[!UICONTROL Continuar]** para continuar.

   * Selecione um namespace no menu suspenso **[!UICONTROL Namespace]**.


1. Selecione uma janela de retrospectiva no menu suspenso **[!UICONTROL Janela de retrospectiva]**. As opções disponíveis dependem do pacote do Customer Journey Analytics ao qual você está habilitado.

Depois de salvar uma conexão que contém conjuntos de dados habilitados para a compilação de identidade, o processo de compilação de cada conjunto de dados começa quando a assimilação de dados desse conjunto de dados começa.