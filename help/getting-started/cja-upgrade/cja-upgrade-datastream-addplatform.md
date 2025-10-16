---
title: Criar um esquema para o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 100%

---

# Adicionar a Plataform como um serviço na sua sequência de dados {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Adicionar a Adobe Experience Platform como um serviço na sequência de dados"
>abstract="Uma sequência de dados precisa de um ou mais serviços para o qual enviar dados. Configure a Adobe Experience Platform como um serviço na sequência de dados.<br><br>Adicionar serviços a uma sequência de dados é um processo simples que leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Uma sequência de dados já deve existir antes que você conclua as etapas desta seção. Quando e como a sequência de dados foi criada depende da implementação do Adobe Analytics, da seguinte maneira:

* Se sua implementação do Adobe Analytics usa o SDK da web ou a extensão do SDK da web, a sequência de dados estava disponível para seu ambiente do Adobe Analytics, antes do processo de atualização.

* Para outras implementações do Adobe Analytics, criar uma sequência de dados faz parte do processo de atualização, conforme descrito em [Criar uma sequência de dados para usar com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Com a sequência de dados disponível, é necessário adicionar a Plataforma como serviço:

1. Na interface do usuário da Adobe Experience Platform, selecione **[!UICONTROL Sequências de dados]** em [!UICONTROL COLEÇÃO DE DADOS] no painel esquerdo.

1. Selecione a sequência de dados configurada anteriormente. <!--true?-->

1. Selecione **[!UICONTROL Adicionar serviço]**.

1. Na tela [!UICONTROL Adicionar serviço]:

   1. Selecione **[!UICONTROL Adobe Experience Platform]** na lista [!UICONTROL Serviço].

   1. Verifique se a opção **[!UICONTROL Habilitado]** está selecionada.

   1. Selecione o conjunto de dados na lista [!UICONTROL Conjunto de dados do evento].

      ![Serviço da AEP de sequência de dados](./assets/datastream-aep-service.png)

   1. Deixe as outras configurações e selecione **[!UICONTROL Salvar]** para salvar a sequência de dados.

   O conjunto de dados agora está configurado para encaminhar os dados coletados de seu site para seu conjunto de dados na Adobe Experience Platform.

   Consulte [Visão geral dos conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=pt-BR) para obter mais informações sobre como configurar um conjunto de dados e como lidar com dados confidenciais.

{{upgrade-final-step}}
