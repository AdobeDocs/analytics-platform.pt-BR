---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 26%

---

# Adicionar a Platform como um serviço à sua sequência de dados {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Adicionar o Adobe Experience Platform como um serviço à sequência de dados"
>abstract="Uma sequência de dados precisa de um ou mais serviços para enviar dados. Configure o Adobe Experience Platform como um serviço na sua sequência de dados.<br><br>Adicionar serviços a uma sequência de dados é um processo simples, que demora apenas alguns minutos para ser concluído."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Uma sequência de dados já deve existir antes que você conclua as etapas desta seção. Quando e como o fluxo de dados foi criado depende da implementação do Adobe Analytics, da seguinte maneira:

* Se sua implementação do Adobe Analytics usa a extensão Web SDK ou Web SDK, a sequência de dados estava disponível para seu ambiente do Adobe Analytics, antes do processo de atualização.

* Para outras implementações do Adobe Analytics, criar uma sequência de dados faz parte do processo de atualização, conforme descrito em [Criar uma sequência de dados para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Com o fluxo de dados disponível, é necessário adicionar o Platform as a service:

1. Na interface do usuário da Adobe Experience Platform, selecione **[!UICONTROL Sequências de dados]** em [!UICONTROL COLEÇÃO DE DADOS] no painel esquerdo.

1. Selecione o fluxo de dados configurado anteriormente. <!--true?-->

1. Selecione **[!UICONTROL Adicionar serviço]**.

1. Na tela [!UICONTROL Adicionar serviço]:

   1. Selecione **[!UICONTROL Adobe Experience Platform]** na lista [!UICONTROL Serviço].

   1. Verifique se a opção **[!UICONTROL Ativado]** está selecionada.

   1. Selecione o conjunto de dados na lista [!UICONTROL Conjunto de dados do evento].

      ![Serviço da AEP de sequência de dados](./assets/datastream-aep-service.png)

   1. Deixe as outras configurações e selecione **[!UICONTROL Salvar]** para salvar a sequência de dados.

   O conjunto de dados agora está configurado para encaminhar os dados coletados de seu site para seu conjunto de dados na Adobe Experience Platform.

   Consulte [Visão geral dos conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) para obter mais informações sobre como configurar um conjunto de dados e como lidar com dados confidenciais.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
