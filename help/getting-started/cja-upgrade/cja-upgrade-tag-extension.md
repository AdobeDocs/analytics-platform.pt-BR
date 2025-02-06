---
title: Criar uma propriedade de tag e adicionar a extensão Web SDK
description: Saiba como criar uma propriedade de tag e adicionar a extensão Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 23%

---

# Adicionar a extensão do SDK da Web à tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Adicionar a extensão Platform Web SDK à propriedade da tag"
>abstract="Adicione a extensão Adobe Experience Platform Web SDK à propriedade da tag. A adição da extensão Web SDK à propriedade de tag é simplificada, levando apenas alguns minutos para ser concluída."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga as etapas desta página somente após concluir todas as etapas de atualização anteriores. Você pode seguir as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou seguir as etapas de atualização que foram geradas dinamicamente para a sua organização com o [questionário de atualização do Adobe Analytics para o Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Após concluir as etapas desta página, continue seguindo as etapas de atualização recomendadas ou as etapas de atualização geradas dinamicamente.

Você pode usar o recurso Tags na Adobe Experience Platform para implementar o código em seu site para coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

As informações a seguir descrevem como adicionar a extensão Web SDK à sua tag. Para obter informações complementares, consulte a [Configurar a extensão de tag do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação do Experience Platform. O Web SDK inclui o [!UICONTROL Serviço da Adobe Experience Cloud ID] nativamente, portanto, não é necessário adicionar a extensão do serviço de ID à sua marca.

Depois de [criar uma tag](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), você deve configurá-la com a extensão Adobe Experience Platform Web SDK. Isso garante que você possa enviar dados para a Adobe Experience Platform (por meio da sequência de dados).

Para adicionar a extensão Web SDK à tag:

1. Faça logon em experience.adobe.com usando suas credenciais da Adobe ID.

1. No Adobe Experience Platform, vá para **[!UICONTROL Coleção de Dados]** > **[!UICONTROL Marcas]**.

1. Selecione a tag criada recentemente na lista de [!UICONTROL Propriedades da tag] para abri-la.

1. Selecione **[!UICONTROL Extensões]** no painel esquerdo.

1. Selecione **[!UICONTROL Catálogo]** na barra superior.

1. Procure ou role até a **[!UICONTROL extensão do Adobe Experience Platform Web SDK]** e selecione **[!UICONTROL Instalar]** para instalá-la.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Selecione a sandbox e a sequência de dados criadas anteriormente para o [!UICONTROL Ambiente de produção], o [!UICONTROL Ambiente de preparo] (opcional) e o [!UICONTROL Ambiente de desenvolvimento].

   ![Configuração da extensão do SDK da Web da AEP](assets/aepwebsk-extension-datastreams.png)

1. Selecione **[!UICONTROL Salvar]**.

1. Continue seguindo as [etapas de atualização recomendadas](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) ou as [etapas de atualização geradas dinamicamente](https://gigazelle.github.io/cja-ttv/).
