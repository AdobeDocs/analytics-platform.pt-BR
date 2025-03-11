---
title: Criar uma propriedade de tag e adicionar a extensão Web SDK
description: Saiba como criar uma propriedade de tag e adicionar a extensão Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 42%

---

# Adicionar a extensão do SDK da Web à tag {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="Adicionar a extensão do SDK da web da Platform à sua propriedade de tag"
>abstract="Adicione a extensão do SDK da web da Adobe Experience Platform à propriedade da tag. Adicionar a extensão do SDK da web à propriedade de tag é simples e leva apenas alguns minutos."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Você pode usar o recurso Tags na Adobe Experience Platform para implementar o código em seu site para coletar dados. Esta solução de gerenciamento de tags permite implantar o código do junto com outros requisitos de marcação. As tags oferecem integração perfeita com a Adobe Experience Platform usando a extensão do SDK da Web da Adobe Experience Platform.

As informações a seguir descrevem como adicionar a extensão Web SDK à sua tag. Para obter informações adicionais, consulte a [Configuração da extensão de tag do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) na documentação do Experience Platform. O Web SDK inclui o [!UICONTROL Serviço da Adobe Experience Cloud ID] nativamente, portanto, não é necessário adicionar a extensão do serviço de ID à sua marca.

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

{{upgrade-final-step}}
